# Continuous Integration & Continuous Delivery

## Important CI/CD Concepts

### Small + Fast = Better
Continuous Delivery has the following benefits:
1.	Time to market goes down
2.	Quality increases not decreases
3.	Limits your Work In Progress
4.	Shortens lead times for changes
5.	Improves Mean Time To Recover

**Continuous Delivery, by Jez Humble and David Farley** https://www.amazon.com/Continuous-Delivery-Deployment-Automation-Addison-Wesley/dp/0321601912

Deming's 14 Key Points - https://deming.org/explore/fourteen-points?apartner=aarp
*	Deming laid much of the groundwork for CI & CD, i.e. the Deming’s 14 key points and the Deming cycle, a continuous quality improvement model which consists of a logical sequence of four key stages: Plan, Do, Study, and Act.


Mary Poppendieck, Lean Software Development: An Agile Toolkit for Software Development Managers
https://www.amazon.com/Lean-Software-Development-Agile-Toolkit/dp/0321150783

Seven lean principles:
1) Eliminate waste
2) Amplify learning
3) Decide as late as possible
4) Deliver as fast as possible
5) Empower the team
6) Build integrity in
7) See the whole


The Three Ways: The Principles Underpinning DevOps by Gene Kim (2012) https://itrevolution.com/the-three-ways-principles-underpinning-devops/
* First Way: System Thinking (performance of the entire system instead of silos)
* Second Way: Amplify Feedback Loops (to ensure short right to left feedback within the pipeline)
* Third Way: Culture of Continual Experimentation and Learning (taking risks and learning from failure)


### Continuous Integration Practices
Continuous Integration (CI) is a development practice where developers integrate code into a shared repository frequently, preferably several times a day. Each integration can then be verified by an automated build and automated tests. Source: https://codeship.com/continuous-integration-essentials


To successfully perform Continuous Integration:
1. Builds should pass the coffee test (< 5 minutes)
2. Commit really small bits
3. Don’t leave the build broken
4. Use a trunk based development flow
5. Don't allow flaky tests, fix them!
6. The build should return a status, a log, and an artifact

### The Continuous Delivery Pipeline
(aka 'deployment pipeline')

Continuous delivery is a strategy wherein any code commit is tested automatically to ensure that it is in a releasable state if the automated tests are passing.
Continuous deployment is a strategy for software releases wherein any code commit that passes the automated testing is automatically released into the production environment, making changes that are visible to the software's users https://searchitoperations.techtarget.com/definition/continuous-deployment

To successfully perform Continuous Delivery:
1. Only build artifacts once
2. Artifacts should be immutable
3. Deployment should go to a copy of production before going into production
4. Stop deploys if it a previous step fails
5. Deployments should be idempotent

Value Stream Map (VSM) https://www.gocd.org/getting-started/part-3/

The VSM is the full end-to-end view across deployment pipelines (from commits to production)


## CI/CD Toolchain
### Version Control

Git - https://git-scm.com/

Github - https://github.com/

Gerrit - https://www.gerritcodereview.com/
*	Git / Gerrit Code Reviews

### CI/CD Systems

Jenkins - https://jenkins.io/
*	Jenkins is the most widely adopted CI system; many plugins are available.
* Rafal Leszko, Continuous Delivery with Docker and Jenkins
https://www.amazon.de/Continuous-Delivery-Docker-Jenkins-Leszko/dp/1787125238/ref=sr_1_24?s=books-intlde&ie=UTF8&qid=1505217371&sr=1-24&keywords=docker 

Jenkins-X - https://jenkins-x.io/
* A way to automatically create and run CI/CD pipelines in a cloud environment (i.e. for Kubernetes-based apps).
* Provides “on-demand” pipelines with (GitOps) workflows built-in.

GoCD - https://www.go.cd/
*	Continuous delivery server with a value stream map view integrated as its core functionality (and thus unlike Jenkins not with plugins).

Bamboo - https://www.atlassian.com/software/bamboo

TeamCity - https://www.jetbrains.com/teamcity/
*	Easy to configure

Travis CI - https://travis-ci.org/
*	Travis CI provides a simple GitHub integration

Circle CI - https://circleci.com/ 
* Simple GitHub integration

GitLab - https://about.gitlab.com/
*	GitLab is based on GitOps concepts and tries to provides a comprehensive CI&CD functionality.

Bitrise - https://www.bitrise.io/
*	CI&CD platform as a service (PaaS) with a main focus on mobile app development

### Tools for Build Automation
Java Build Tools: Ant vs Maven vs Gradle: https://www.baeldung.com/ant-maven-gradle 
iOS Build Tools: xcode server, fastlane, and alternatives
JavaScript Build Tools & Bundlers https://survivejs.com/webpack/appendices/comparison/ 

Gradle - https://gradle.org/

Make - https://www.gnu.org/software/make/

Rake - https://github.com/ruby/rake

Maven - https://maven.apache.org/

Gulp - http://gulpjs.com/

Packer - https://www.packer.io/

### Artifact Repository

Dockerhub - https://hub.docker.com/

Artifactory - https://www.jfrog.com/artifactory/
* Artifactory is commonly used in enterprises

Nexus - http://www.sonatype.org/nexus/

Bintray - https://bintray.com/

Amazon S3 - https://aws.amazon.com/s3/

### Deployment

Rundeck - http://rundeck.org/

Urbancode - https://developer.ibm.com/urbancode/products/urbancode-deploy/

Thoughtworks - https://www.thoughtworks.com/continuous-delivery

Deployinator - https://github.com/etsy/deployinator
