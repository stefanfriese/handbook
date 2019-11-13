# DevOps Exercises

# Exercise - Install Prometheus

Prometheus is a time-series database with a UI and sophisticated querying language (PromQL). Prometheus can scrape metrics, counters, gauges and histograms over HTTP using plaintext or a more efficient protocol.

## Prep - Infrastructure
Raise AWS EC2 instance:
* Ubuntu 18.04
* t2.micro
* tag: Name: Jenkins
* Security Group: open port 22, 9090, 9100, 3000

Note: Stop EC2 if Prometheus is not needed anymore
In the AWS Console go to the EC2 service and Stop (or terminate) instance

## Option 1 - Ansible
* ssh to EC2 Ubuntu machine
* Install Ansible
* Git clone ansible-prometheus
* Setup role
* Create main.yml playbook
* Create inventory file
* Run playbook
* Install node exporter and configure
* Check web interface

ssh on machine (as user ‘ubuntu’)
```shell
ssh -i <key_name>.pem ubuntu@<public_ip>
```

Note: If you need a root password, see: https://aws.amazon.com/premiumsupport/knowledge-center/set-change-root-linux/


Prep steps:
```shell
sudo apt update

sudo apt install ansible python-pip

pip install tox
```
Note: For Python3, use:
```shell
sudo apt install python3-pip

pip3 install tox
```

Get Ansible
```shell
git clone https://github.com/cloudalchemy/ansible-prometheus
```

Setup directory structure for Ansible:
```shell
cd ansible-prometheus

mkdir -p roles/cloudalchemy.prometheus

mv defaults/ handlers/ meta/ molecule/ tasks/ templates/ vars/ roles/cloudalchemy.prometheus/
```

Create Ansible Playbook (based on README.md)
See [main.yml](main.yml) in repository

Inventory for Ansible: inventory file in repository

Execute Ansible to install Prometheus:
```shell
ansible-playbook -i inventory main.yml
```

One of the most widely used Prometheus exporters is the NodeExporter. When NodeExporter is run on a host it will provide details on I/O, memory, disk and CPU pressure. You can run the NodeExporter as a Docker container, but it needs so many additional flags that the project recommends you run it directly on a host being monitored.

Install Prometheus node exporter (exporter for machine metrics):
```shell
cd ..; curl -LO https://github.com/prometheus/node_exporter/releases/download/v0.18.1/node_exporter-0.18.1.linux-amd64.tar.gz

tar xzf node_exporter-0.18.1.linux-amd64.tar.gz

cd node_exporter-0.18.1.linux-amd64

sudo mv node_exporter /usr/local/bin/

sudo vim /etc/systemd/system/node_exporter.service
```

node_exporter.service:
```
node_exporter.service:
[Unit]
Description=Node Exporter
Wants=network-online.target
After=network-online.target

[Service]
User=node_exporter
Group=node_exporter
Type=simple
ExecStart=/usr/local/bin/node_exporter

[Install]
WantedBy=multi-user.target
```
See also node_exporter.service file in repository.

```shell
Start node exporter:
sudo systemctl daemon-reload
sudo systemctl start node_exporter
sudo systemctl enable node_exporter
sudo systemctl status node_exporter
```

Status should show "Active: active (running)"

Verify that metrics are getting exported:
```shell
curl http://localhost:9100/metrics
```

Update Prometheus configuration:
```shell
sudo vim /etc/prometheus/prometheus.yml
```

prometheus.yml:
```
#
# Ansible managed
#
# http://prometheus.io/docs/operating/configuration/

global:
  evaluation_interval: 15s
  scrape_interval: 15s
  scrape_timeout: 10s

  external_labels:
    environment: ip-172-31-35-144.us-east-2.compute.internal




rule_files:
  - /etc/prometheus/rules/*.rules


scrape_configs:
  - job_name: prometheus
    metrics_path: /metrics
    static_configs:
    - targets:
      - ip-172-31-35-144.us-east-2.compute.internal:9090
      - localhost:9100
  - file_sd_configs:
    - files:
      - /etc/prometheus/file_sd/node.yml
    job_name: node
```

Note: You have to update the IPs in the yaml file.

Restart Prometheus:
```shell
sudo systemctl restart prometheus
sudo systemctl status prometheus
```

Check web interface:
```shell
Enter <public_ip:9090> in your browser.
```
Note: If you don't get the page, check in the aws console if port 9090 (and 9100) are open

Tip: look at <public_ip:9100>/metrics
There you can find events that you can add as graphs, e.g. “go_gc_duration_seconds”.

## Option 2 – Install Prometheus using Docker
Prometheus is written in Golang and can be consumed as single statically-compiled binary with no other dependencies. The project also packages up the binary with a sensible configuration in a Docker container.

Note that this guide is kept short! If you need more information, see: https://prometheus.io/docs/prometheus/latest/installation/.

Run Prometheus in Docker
Let's define a Docker Compose which will let us keep our command-lines simple and repeatable:
```
version: "3"
services:
  prometheus:
    image: quay.io/prometheus/prometheus:latest
    ports:
     - 9090:9090
```

Deploy the stack file:
Swarm mode is required to deploy stack files, so run docker swarm init if you haven't already.
```shell
$ docker swarm init
$ docker stack deploy monitoring --compose-file=./docker-compose.yml
```

Navigate to: http://localhost:9090/ to view the UI.

See also: https://medium.com/@soumyadipde/monitoring-in-docker-stacks-its-that-easy-with-prometheus-5d71c1042443


# Exercise - Grafana

Download Grafana, start and enable Grafana server:
```shell
curl -LO https://s3-us-west-2.amazonaws.com/grafana-releases/release/grafana_5.1.4_amd64.deb ;
sudo apt-get install -y adduser libfontconfig ;
sudo dpkg -i grafana_5.1.4_amd64.deb ;
sudo systemctl start grafana-server ;
sudo systemctl enable grafana-server
```
Note that you shall enable the server so that next time the system restarts, Grafana will be available.

Enter <public_ip:3000> in your browser.
As a first time user, enter ‘admin’, ‘admin’ to login.

Configure ‘Prometheus’ as data source.
Configuration > Data Sources > Add Data Source
* Type Prometheus
* URL: <public_ip>:9090
Save & Test, tab ‘Dashboards’

# GitOps

Training environment: https://www.katacoda.com/courses/kubernetes/playground

Trainings repo: https://github.com/continuouseverything/gitops101
