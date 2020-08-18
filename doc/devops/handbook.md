# Devops

## DevOps Basics
**What Is DevOps?**
DevOps is the practice of operations and development engineers participating together through the entire service lifecycle; from the design and development process all the way to production support. DevOps is also characterized by operations staff making use of many of the same techniques as developers for their systems work. 


**2019 State of DevOps Report**
https://cloud.google.com/devops/state-of-devops/


DevOps Core Values: CAMS
CAMS - Culture, Automation, Measurement, Sharing
What DevOps Means To Me, by John Willis https://www.chef.io/blog/2010/07/16/what-devops-means-to-me/

DevOps Culture, by John Willis
http://itrevolution.com/devops-culture-part-1/

People over Process over Tools, by Damon Edwards http://dev2ops.org/2010/02/people-over-process-over-tools/

DevOps Core Values: The Three Ways
The Three Ways
1.	Systems Thinking
2.	Amplifying Feedback Loops
3.	A Culture of Continuous Experimentation and Learning

The Three Ways, by Gene Kim
http://itrevolution.com/the-three-ways-principles-underpinning-devops/

Key DevOps Methodologies
1.	People over Process over Tools
2.	Continuous Delivery
3.	Lean Management
4.	Visible Ops style Change Control
5.	Infrastructure as Code

People over Process over Tools, by Damon Edwards
http://dev2ops.org/2010/02/people-over-process-over-tools/

**Continuous Delivery, by Jez Humble and David Farley** https://www.amazon.com/Continuous-Delivery-Deployment-Automation-Addison-Wesley/dp/0321601912

The Amazing DevOps Transformation of the HP LaserJet Firmware Team (Gary Gruver), by Gene Kim
http://itrevolution.com/the-amazing-devops-transformation-of-the-hp-laserjet-firmware-team-gary-gruver/

Leading the Transformation, by Gary Gruver and Tommy Mouser
http://itrevolution.com/books/leading-the-transformation/

Practices for DevOps Success
*	Embedded Teams
*	Blameless Postmortems
*	Status Pages
*	Developers on Call
*	Incident Command System
*	Chaos Testing
*	Blue/Green Deployments
*	“The Cloud”

AWS Builders' Library ("How Amazon builds and operates software)
https://aws.amazon.com/builders-library

Incident Command for IT: What We Can Learn From The Fire Department, by Brent Chapman
https://www.usenix.org/legacy/event/lisa05/tech/chapman.pdf

Keys to SRE, by Ben Treynor
https://www.usenix.org/conference/srecon14/technical-sessions/presentation/keys-sre

Transparent Uptime, by Lenny Rachitsky
http://www.transparentuptime.com/

How Complex Systems Fail, by Dr. Richard Cook
http://web.mit.edu/2.75/resources/random/How%20Complex%20Systems%20Fail.pdf

Blameless Postmortems, by John Allspaw
https://codeascraft.com/2012/05/22/blameless-postmortems/

Dependency Injection, by Martin Fowler
http://martinfowler.com/articles/injection.html

Chaos Monkey Released Into The Wild, by Cory Bennett and Ariel Tseitlin
http://techblog.netflix.com/2012/07/chaos-monkey-released-into-wild.html

The Andon Cord, by John Willis
http://itrevolution.com/kata/


## DevOps: A Culture Problem

What Is DevOps, by Damon Edwards
http://dev2ops.org/2010/02/what-is-devops/

10+ Deploys Per Day: Dev and Ops Cooperation at Flickr, by John Allspaw and John Hammond
http://www.slideshare.net/jallspaw/10-deploys-per-day-dev-and-ops-cooperation-at-flickr

Blameless Postmortems contain:

1.	A description of the incident
2.	A description of the root cause
3.	How the incident was stabilized or fixed.
4.	A timeline of events including all actions taken to resolve the incident
5.	How the incident affected customers
6.	Remediations and corrective actions.

Transparent Uptime means:
1.	Admit Failure
2.	Sound Like A Human
3.	Have A Communication Channel
4.	Above All Else, Be Authentic

Blameless Postmortems, by John Allspaw
https://codeascraft.com/2012/05/22/blameless-postmortems/

A Guideline for Postmortem Communication, by Lenny Rachitsky
http://www.transparentuptime.com/2010/03/guideline-for-postmortem-communication.html

Crucial Conversations, by Kerry Patterson, Joseph Grenny, Ron McMillan, and Al Switzler
https://en.wikipedia.org/wiki/Crucial_Conversations:_Tools_for_Talking_When_Stakes_Are_High

Is Your Team Too Big? Too Small? What’s the Right Number?
http://knowledge.wharton.upenn.edu/article/is-your-team-too-big-too-small-whats-the-right-number-2/

Web Operations, by John Allspaw and Jesse Robbins
https://www.amazon.com/Web-Operations-Keeping-Data-Time/dp/1449377440

Effective DevOps, by Jennifer Davis and Katherine Daniels
http://shop.oreilly.com/product/0636920039846.do

Don’t Throw Things Over Walls
The Phoenix Project, by Gene Kim, Kevin Behr, George Spafford
https://en.wikipedia.org/wiki/The_Phoenix_Project_(novel)

DevOps Culture, by Martin Fowler
http://martinfowler.com/bliki/DevOpsCulture.html

Shadow IT
https://en.wikipedia.org/wiki/Shadow_IT

Conway’s Law
https://en.wikipedia.org/wiki/Conway%27s_law

Operations Maturity Model
https://pages.chef.io/operations-maturity-model

A Typology of Organisational Cultures, by Ron Westrum
http://www.ncbi.nlm.nih.gov/pmc/articles/PMC1765804/pdf/v013p0ii22.pdf

### Kaizen: Continuous Improvement

Kaizen - change for the better

Kaizen’s Guiding Principles
*	Good processes bring good results
*	Go see for yourself to grasp the current situation (gemba)
*	Speak with data, manage by facts
*	Take action to contain and correct root causes of problems
*	Work as a team
*	Kaizen is everybody’s business

Kaizen Glossary
https://us.kaizen.com/knowledge-center/glossary.html

When In Japan…, by Ryan Day
http://www.qualitydigest.com/inside/lean-article/100115-when-japan.html#

Kaizen
https://en.wikipedia.org/wiki/Kaizen

Toyota Kata
https://en.wikipedia.org/wiki/Toyota_Kata

5 Whys
https://en.wikipedia.org/wiki/5_Whys

## Infrastructure Automation

### Infrastructure As Code
Infrastructures.org http://www.infrastructures.org/

Architectures for open and scalable clouds, by Randy Bias
http://www.slideshare.net/randybias/architectures-for-open-and-scalable-clouds

**Infrastructure as Code, by Martin Fowler**
http://martinfowler.com/bliki/InfrastructureAsCode.html

Provisioning is the process of making a server ready for operation, including hardware, OS, system services, network connectivity.
Deployment is the process of automatically deploying and upgrading applications on a server.
Orchestration is the act of performing coordinated operations across multiple systems.
Configuration management is an overarching term dealing with change control of system configuration after initial provision, but is often also applied to maintaining and upgrading application and application dependencies. 
Imperative - also known as “procedural,” this is an approach where commands desired to produce a state are defined and executed. 
Declarative - also known as “functional,” this is an approach where you define a desired state and the tool converges the existing system on the model.
Idempotent - the ability to execute the CM procedure repeatedly and end up in the same state each time. 
Self service - is the ability for an end user to kick off one of these processes without having to go through other people.

Server Provisioning
https://en.wikipedia.org/wiki/Provisioning#Server_provisioning

Golden Image or Foil Ball, by Luke Kanies
http://madstop.com/post/85950592485/golden-image-or-foil-ball-repost

Canary Release, by Martin Fowler
http://martinfowler.com/bliki/CanaryRelease.html

Blue-Green Deployment, by Martin Fowler
http://martinfowler.com/bliki/BlueGreenDeployment.html

Immutable Deployment
AMI Creation with Aminator, by Michael Tripoli & Karate Vick
http://techblog.netflix.com/2013/03/ami-creation-with-aminator.html

Immutable Server, by Martin Fowler
http://martinfowler.com/bliki/ImmutableServer.html

Immutable Delivery, by John Willis
https://theagileadmin.com/2015/11/24/immutable-delivery/

CMDB
https://en.wikipedia.org/wiki/Configuration_management_database

The CMDB is Dead, Long Live the CMDB, by Rhonabwy
https://rhonabwy.com/2010/07/18/the-cmdb-is-dead-long-live-the-cmdb/

Hadoop and Zookeeper
http://hadoop.apache.org/

Kubernets vs AWS:
https://zwischenzugs.com/2019/03/25/aws-vs-k8s-is-the-new-windows-vs-linux/amp/


## Your Infrastructure Toolchain
Infastructure as Code (IaC) and Configuration Management (CM) Tools:
CloudFormation and Terraform are provisioning tools: They are designed to provision the server instances themselves, leaving the job of configuring those servers to other tools.

Ansible, Puppet, SaltStack, and Chef are considered to be configuration management (CM) tools and were created to install and manage software on existing server instances (e.g., installation of packages, starting of services, installing scripts or config files on the instance). They do the heavy lifting of making one or many instances perform their roles without the user needing to specify the exact commands. No more manual configuration or ad-hoc scripts are needed.

Chef and Ansible use a procedural style language where you write code that specifies, step-by-step, how to achieve the desired end state. CloudFormation, Terraform, SaltStack, and Puppet use a declarative style where you write code that specifies the desired end state.

**AWS Cloudformation**
https://aws.amazon.com/cloudformation/
*	Getting started with templates (yml, json): https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/gettingstarted.templatebasics.html

Hashicorp Terraform
https://www.terraform.io/
* define, provision, and manage infrastructure on-prem and in-cloud

Chef
https://www.chef.io/
* configuration management tool that uses a DSL for system configuration "recipes"
* Foodcritic (Lint tool for Chef cookbooks) - http://www.foodcritic.io/
* Chefspec - https://docs.chef.io/chefspec.html - framework that tests resources and recipes as part of a simulated Chef Infra Client run

Puppet
https://puppet.com/
* configuration management tool that uses a declarative language to describe the state of a system in terms of resources

Ansible
https://www.ansible.com/
Ansible is (e.g. compared to Chef) agent-less, it uses ssh to connect to server.
*	Getting started: https://docs.ansible.com/ansible/latest/user_guide/intro_getting_started.html
*	https://blog.ssdnodes.com/blog/step-by-step-ansible-guide/

Cfengine
https://cfengine.com/
* configuration management tool

kitchenCI
http://kitchen.ci/
Kitchen provides a test harness to execute infrastructure code

Ohai
https://docs.chef.io/ohai.html
Ohai is a tool that is used to collect system configuration data, which is provided to Chef Infra Client for use within cookbooks.

Zookeeper
https://zookeeper.apache.org/
ZooKeeper is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services, i.e. for distributed applications.

Consul
https://www.consul.io/
Consul is a service networking solution to connect and secure services across any runtime platform and public or private cloud.

## Container & Orchestration

What is a container https://www.docker.com/resources/what-container 

**Docker**
https://www.docker.com/
*	Docker Tutorial https://docs.docker.com/get-started/ 
*	Dockerize Python app: https://runnable.com/docker/python/dockerize-your-python-application (and https://docs.docker.com/get-started/part2/)
*	Amazon ECS https://aws.amazon.com/ecs/ - service to run Docker on AWS

**Kubernetes**
http://kubernetes.io/
*	Kubernetes Basics https://kubernetes.io/docs/tutorials/kubernetes-basics/ 
*	Kubernetes vs Docker: https://containerjournal.com/topics/container-ecosystems/kubernetes-vs-docker-a-primer/amp/
*	Linux Foundation Online Course https://training.linuxfoundation.org/training/introduction-to-kubernetes/
*	minikube https://kubernetes.io/docs/tutorials/kubernetes-basics/create-cluster/cluster-intro/
*	Open Shift https://www.openshift.com/ - Kubernetes platform
* Amazon EKS - https://aws.amazon.com/eks/ - Kubernetes on AWS
* Kubernetes Patterns - https://k8spatterns.io/

Further Resources about Container, Docker, Kubernetes:
Oliver Liebel Skalierbare, Container-Infrastrukturen: Das Handbuch für Administratoren und DevOps-Teams
https://www.amazon.de/Skalierbare-Container-Infrastrukturen-Administratoren-DevOps-Teams-Container-Orchestrierung/dp/3836243660/ref=pd_cp_14_1?_encoding=UTF8&psc=1&refRID=NCBMMP9MB0Q2S1320GRC

Sébastien Goasguen, Kubernetes Cookbook: Building Cloud Native Applications
https://www.amazon.de/Kubernetes-Cookbook-Building-Native-Applications/dp/1491979682/ref=sr_1_17?s=books-intlde&ie=UTF8&qid=1505217130&sr=1-17&keywords=web+application+architecture 

Russ McKendrick, Mastering Docker - Second Edition
https://www.amazon.de/Mastering-Docker-Second-Russ-McKendrick/dp/1787280241/ref=sr_1_19?s=books-intlde&ie=UTF8&qid=1505217371&sr=1-19&keywords=docker 

Randall Smith, Docker Orchestration
https://www.amazon.de/Docker-Orchestration-Randall-Smith/dp/1787122123/ref=sr_1_20?s=books-intlde&ie=UTF8&qid=1505217371&sr=1-20&keywords=docker 

Karl Matthias, Docker - Up and Running: Shipping Reliable Containers in Production
https://www.amazon.de/Docker-Shipping-Reliable-Containers-Production/dp/1491917571/ref=sr_1_1?s=books-intlde&ie=UTF8&qid=1505217289&sr=1-1&keywords=docker 

### Service Mesh

A service mesh is an infrastructure layer for handling service-to-service communication. It’s mainly used for cloud native applications.

API Gateways vs Mesh: https://medium.com/solo-io/api-gateways-are-going-through-an-identity-crisis-d1d833a313d7

Istio - https://istio.io/
Open platform to connect, manage, and secure microservices, integrate microservices, manage traffic flow across microservices, enforce policies and aggregate telemetry data. 

linkerd - https://linkerd.io/
linkerd is an out-of-process network stack for microservices. It functions as a transparent RPC proxy.

envoy - https://www.envoyproxy.io/

### Serverless

**AWS lambda** - https://aws.amazon.com/lambda/

chalice - https://github.com/aws/chalice
Python Serverless Microframework for AWS which acts as decorator for integrating with S3, SNS, SQS, and other AWS services.

SAM https://github.com/awslabs/serverless-application-model
AWS Serverless Application Model (SAM) is an open-source framework for building serverless applications

Optimizing Your Serverless Applications - AWS Online Tech Talks:
https://www.youtube.com/watch?v=DYQ8pXrktBM

## GitOps
GitOps https://www.weave.works/technologies/gitops/ - GitOps is a way to do Kubernetes cluster management and application delivery.  It works by using Git as a single source of truth for declarative infrastructure and applications.
* CNCF Flux: Flux is a tool that automatically ensures that the state of a cluster matches the config in git. It uses an operator in the cluster to trigger deployments inside Kubernetes, which means you don't need a separate Continuous Deployment tool.
* ArgoCD: https://argoproj.github.io/argo-cd/
* Gitkube: https://github.com/hasura/gitkube - Gitkube is a tool for building and deploying Docker images on Kubernetes using git push.
* Tekton: https://cloud.google.com/tekton/
* JenkinsX

## SRE
The SRE concept (Site Reliability Engineering) was created by Google. It's increasingly common in organizations seeking to advance adoption of DevOps and run highly reliable services. Key characteristics of SRE are:
*	Highly skilled engineering function with deep operations and delivery skill set 
*	Specialist knowledge area drives application and platform stability, reliability, scalability, performance, fault tolerance, disaster readiness, logging, monitoring and capacity planning practices
*	Defines, builds and evolves best practices, standards and tool sets to improve availability, performance and operational efficiency
*	Scalable and cost effective approach (focused on automation, enabling teams and creating tools) 
*	Proven function at companies such as Google, Twitter, Uber, LinkedIn, Facebook and others

SREs are typically a 50/50 blend of engineering and operations skill sets so can directly contribute to application code as well as understanding what it takes to design and run a high quality service at global scale.

Engineering Doesn't End With Deployment
Site Reliability Engineering, by Betsy Beyer, Chris Jones, Jennifer Petoff, Niall Richard Murphy
http://shop.oreilly.com/product/0636920041528.do

Incident Command for IT: What We Can Learn From The Fire Department, by Brent Chapman
https://www.usenix.org/legacy/event/lisa05/tech/chapman.pdf

Keys to SRE, by Ben Treynor
https://www.usenix.org/conference/srecon14/technical-sessions/presentation/keys-sre

Transparent Uptime, by Lenny Rachitsky
http://www.transparentuptime.com/

How Complex Systems Fail, by Dr. Richard Cook
http://web.mit.edu/2.75/resources/random/How%20Complex%20Systems%20Fail.pdf

Blameless Postmortems, by John Allspaw
https://codeascraft.com/2012/05/22/blameless-postmortems/

Dependency Injection, by Martin Fowler
http://martinfowler.com/articles/injection.html

Chaos Monkey Released Into The Wild, by Cory Bennett and Ariel Tseitlin
http://techblog.netflix.com/2012/07/chaos-monkey-released-into-wild.html

Design For Operation - Theory
Design Patterns, by Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides
https://www.amazon.com/Design-Patterns-Elements-Reusable-Object-Oriented/dp/0201633612

Release It!, by Michael Nygard
https://pragprog.com/book/mnee/release-it

Hystrix
https://github.com/Netflix/Hystrix

Martin Fowler’s Architecture Descriptions
http://martinfowler.com/bliki/

### Design For Operation - Practice
**12 factor app and reactive design**:
https://www.slideshare.net/dejanglozic/micro-services-reactive-manifesto-and-12factors

12-factor app – https://12factor.net/
A methodology for building modern, scalable, maintainable software-as-a-service apps

Reactive manifesto - https://www.reactivemanifesto.org/ 

Netflix’ Chaos Monkey
http://techblog.netflix.com/2012/07/chaos-monkey-released-into-wild.html 

Frequency Reduces Difficulty, by Martin Fowler
http://martinfowler.com/bliki/FrequencyReducesDifficulty.html 

AWS outage: How Netflix weathered the storm by preparing for the worst
http://www.techrepublic.com/article/aws-outage-how-netflix-weathered-the-storm-by-preparing-for-the-worst/ 

Code profiling
https://en.wikipedia.org/wiki/Profiling_(computer_programming)
https://en.wikipedia.org/wiki/List_of_performance_analysis_tools 

### Operate For Design - Metrics and Monitoring
The 6 Monitoring Areas
1.	Service Performance and Uptime
2.	Software Component Metrics
3.	System Metrics
4.	App Metrics
5.	Performance 
6.	Security

How Complex Systems Fail, by Dr. Richard Cook
http://web.mit.edu/2.75/resources/random/How%20Complex%20Systems%20Fail.pdf

A Lean Cloud Monitoring Checklist, by Ernest Mueller
http://slideplayer.com/slide/7650435/ 
Operate for Design: Logging
Logging and Log Management, by Anton Chuvakin, Kevin Schmidt, and Chris Phillips
http://shop.oreilly.com/product/9781597496353.do 
Your SRE Toolchain
Logging on kubernetes https://platform9.com/blog/logging-monitoring-of-kubernetes-applications-requirements-recommended-toolset/

Distributed Metrics & Monitoring: 
**Prometheus** https://prometheus.io/ 
*	Prometheus Adapter for Kubernetes: https://github.com/directxman12/k8s-prometheus-adapter

Distributed Tracing https://opentracing.io/ 

Distributed Logging, and more: https://www.elastic.co/products/ 

Datadog
https://www.datadoghq.com/

New Relic
https://newrelic.com/

AppDynamics
https://www.appdynamics.com/

Statsd
https://github.com/etsy/statsd

Ganglia
http://ganglia.info/

Graphite
https://graphiteapp.org/

Grafana
http://grafana.org/

InfluxDB
https://influxdata.com/

OpenTSDB
http://opentsdb.net/

Metrics
http://metrics.dropwizard.io/

Sysdig
https://sysdig.com/

Splunk
http://www.splunk.com/
Splunk is a very powerful log analytics engine but also expensive.

**ELK Stack**
https://www.elastic.co/webinars/introduction-elk-stack
„ELK“ represents:
*	Elasticsearch: Log aggregator
*	Logstash: Agent to send logs into Elasticsearch
*	Kibana: GUI web interface to search logs
Note that ELK requires memory, the standard config recommends 2GB.
To learn how to set up alerts and notifications with ELK stack, please refer to the following: https://www.elastic.co/what-is/elasticsearch-alerting
For information how to install, see: https://linuxconfig.org/install-elk-on-ubuntu-18-04-bionic-beaver-linux

PagerDuty
https://www.pagerduty.com/

VictorOps
https://victorops.com/

StatusPage
https://www.statuspage.io/

Rundeck
http://rundeck.org/ 

nip.io - wildcard DNS service that can map any IP address to a hostname
https://nip.io/


## Lean
7 Principles of Lean Software Development
* ELIMINATE WASTE
* AMPLIFY LEARNING
* DECIDE AS LATE AS POSSIBLE
* DELIVER AS FAST AS POSSIBLE
* EMPOWER THE TEAM
* BUILD INTEGRITY IN
* SEE THE WHOLE

The Seven Wastes (Muda) of Lean Software
Waste #1 - Partially Done Work
Waste #2 - Extra Features
Waste #3 - Relearning
Waste #4 - Handoffs
Waste #5 - Delays
Waste #6 - Task Switching
Waste #7 - Defects

Build-Measure-Learn
* BUILD – MINIMUM VIABLE PRODUCT
* MEASURE – THE OUTCOME AND INTERNAL METRICS
* LEARN – ABOUT YOUR PROBLEM AND YOUR SOLUTION
* REPEAT – GO DEEPER WHERE IT’S NEEDED

**Lean Software Development: An Agile Toolkit, by Mary and Tom Poppendieck**
https://www.amazon.com/Lean-Software-Development-Agile-Toolkit/dp/0321150783

**Lean Startup, by Eric Ries**
https://en.wikipedia.org/wiki/Lean_startup

Value Stream Mapping
https://en.wikipedia.org/wiki/Value_stream_mapping

DevOps Culture, by John Willis
http://itrevolution.com/devops-culture-part-1/

