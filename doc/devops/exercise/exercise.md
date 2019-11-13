# DevOps Exercises

# GitOps

Trainings repo: https://github.com/continuouseverything/gitops101

Trainings environment: https://www.katacoda.com/courses/kubernetes/playground


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

## Ansible
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

Create Ansible Playbook - see [main.yml](main.yml) in repository:
```shell
vim main.yml
````

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
[Unit]
Description=Node Exporter
Wants=network-online.target
After=network-online.target

[Service]
Type=simple
ExecStart=/usr/local/bin/node_exporter

[Install]
WantedBy=multi-user.target
```
See also [node_exporter.service](node_exporter.service) file in repository.

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

Note that https://www.digitalocean.com/community/tutorials/how-to-install-prometheus-on-ubuntu-16-04 shows you further steps what can be configured!
