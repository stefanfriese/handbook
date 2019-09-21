# Exercise – Jenkins Pipelines on AWS
Deploy and run a Jenkins instance on AWS, configure Jenkins, and create a pipeline.

## Before you begin
AWS Account (AWS Educate, promotional credit issued), IAM username and password, EC2 Key pair

## Infrastructure
Raise AWS EC2 instance:
* Ubuntu 18.04
* t2.micro
* tag: Name: Jenkins
* Security Group: open port 22 and 8080

Eventually, you can select for a trial “My IP” to improve security but note that this means that you have to update your settings if your public IP is changing.

### Detailed instructions to raise EC2 instance
1) Log in to the AWS management console. Find and select the IAM (Identify and Access Management).

2) Create a new group, select "Group" from the left sidebar, name it "jenkins", and attach the following policies:
* AmazonEC2FullAccess
* AmazonVPCFullAccess
* AmazonS3FullAccess.
Hit Next Step, review, and then "Create Group."

3) Create a new user, select "Users" from the left sidebar, then "Add user," and use "jenkins" as the user name. Click on both "programmatic access" and "AWS management console access." The defaults for auto-generated password and "users must create a new password at next sign-in" are OK and should be kept. Hit "Next", and add the "jenkins" user to the "jenkins" group. Hit "next," no need to add "Tags." Review, and accept. Capture the Access Key, Secret Access Key, and the password so that you can log in as that user (easy to just download the csv file).
To sign in as this new IAM user, sign out of the AWS console, then use the following URL, where your_aws_account_id is your AWS account number without the hyphens (for example, if your AWS account number is 1234-5678-9012, your AWS account ID is 123456789012):
https://your_aws_account_id.signin.aws.amazon.com/console/
This is available in the 'Users' section of the sidebar, under the 'jenkins' user link, in the Security credentials tab, as a "Console sign-in link."
Upon signing in, go through the "renew your password" steps.

4) Create a new key pair for access to your instance(s). Choose EC2 as the service after logging in. Select "Key Pairs" from the sidebar on the left, from the "Network and Security" section. Enter the "pipeline" name when prompted. Save the ".pem" file.
If you will use an SSH client on a Mac or Linux computer to connect to your Linux instance, use the following command to set the permissions of your private key file so that only you can read it:
```shell
chmod 400 your_user_name-key-pair-region_name.pem
```
5) Launch the EC2 t2.micro for the free tier, pick "Ubuntu 18.04 LTS amd64," review, and when hitting "launch" ensure that an existing pair ("pipeline") from before is selected. If you're not using the right key pair, you cannot log in.

6) Once launched, create a security group for the vm. In the left sidebar, under Network and Security, select "Security Groups." Under name, use: 'jenkins', description: "basic Jenkins security group," VPC should have the default one used. Click Add Rule: Custom TCP Rule, Protocol: TCP, Port Range 8080, Source 0.0.0.0/0 Then add the SSH rule: Protocol: SSH, Port range: 22, From source, use the dropdown and select "My IP."

7) Go back to instances, and right click the running instance, select Networking and change the security groups. Select the Jenkins security group that was created previously.

8) To connect to your instance using your key pair, follow these steps. Right click your running instance and select "Connect," then follow the instructions to SSH into it. For example, here are the directions that popped up in my AWS console on how to SSH into my machine (your directions will not look exactly like this, since portions of the information, like the full domain address of the instance, will be different):

Find the pem file, ensure it has the right permissions (if on Mac or Linux):
```shell
chmod 400 pipeline.pem
```

If on Mac or Linux then open the terminal and SSH into it:
```shell
ssh -i "pipeline.pem" ubuntu@ec2-18-222-139-16.us-east-2.compute.amazonaws.com
```

NOTE: If on Windows, an SSH client will need to be installed (PuTTy).

**Stop EC2 after completing the exercise to avoid unnecessary costs:**
In the AWS Console, go to the EC2 service and select "Stop instance".


## Deploy Jenkins
ssh on machine (as user ‘ubuntu’):
```shell
ssh -i your_key.pem ubuntu@public_ip
```
If you need a root password, see: https://aws.amazon.com/premiumsupport/knowledge-center/set-change-root-linux/

1. Prep steps
```shell
sudo apt-get update
sudo apt install -y default-jdk
```

2. Install Jenkins according to https://wiki.jenkins.io/display/JENKINS/Installing+Jenkins+on+Ubuntu

Note that the version of Jenkins included with the default Ubuntu packages is often behind the latest available version from the project itself. To take advantage of the latest fixes and features, you can use the project-maintained packages to install Jenkins.
* First, add the repository key to the system.
* When the key is added, the system will return OK. Next, append the Debian package repository address to the server's sources.list.
* When both of these are in place, run update so that apt will use the new repository.
* Finally, install Jenkins and its dependencies.

```shell
wget -q -O - https://pkg.jenkins.io/debian/jenkins-ci.org.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt-get update
sudo apt-get install jenkins
```

3. Start Jenkins UI
Go to a browser and enter: <public_ip>:8080
Get password via shell:
```shell
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

4. Configure Jenkins in “Manage Jenkins”
•	Change password
•	Install “Blue Ocean” plugins including customizations

Blue Ocean re-skins Jenkins to make management easier. It makes Jenkins become IasC (Infrastructure as Code).


## Adding GitHub Repo to the Pipeline 
Blue Ocean > Create a new Pipeline > Connect to GitHub > Create new token > select repo
Note that you shall select a repo which includes a jenkinsfile.
```shell
sudo install docker.io
sudo usermod -aG  docker jenkins
sudo systemctl restart jenkins
```
