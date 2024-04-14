# Container Deployment with AWS CoPilot

AWS Copilot is a command line interface (CLI) that enables quick launch and easy manageability of containerized applications on AWS. Copilot automates each step in the application deployment lifecycle including pushing to a registry, creating a task definition, and creating a cluster. In this exercise, you learn to launch a containerized application using AWS CoPilot.


Step1: Pre-Requisite
-------------

You need to have an AWS account with administrative access to complete this Project.



Step2: Create IAM User
-------------------

Let’s create an IAM user which is used to containerize the application using Amazon CoPilot in Amazon Cloud9. When building this project, we tried to use Cloud9 temporary managed credentials but we were getting credentials reset error; hence we used IAM user credentials in Cloud9 for the Project.

1) Login to the AWS Console and select mumbai as the region.

2) Goto IAM Management Console, click on the Users menu in the left and then click on the Add user button.

3) On the next screen, type in (user name) as the user name and select Programmatic access as the option for the access type. Click on the Next: Permissions button.

4) On the next screen, select Attach existing policies directly option. Select AdministratorAccess as the policy and click on the Next: Tags button

5) Click on the Create user button. It creates the user and it also generates Access key ID and Secret access key. Click on the Download.csv link to download the keys.
 
    Note: please make sure you make note of the keys as you need them in the later steps.


   ![image](https://github.com/RanguRahul/AWS-CoPilot/assets/120587828/3d53fcd1-2805-4168-b183-0b4a9885aff0)

Step3: Create Cloud9 Environment
-----------------------

Amazon Cloud9 environment to create container application and then deploy it using AWS CoPilot commands.

![image](https://github.com/RanguRahul/AWS-CoPilot/assets/120587828/3e1ff1e0-52d8-4961-8d9d-df78de299b70)


Step4: Configure Cloud9 Environment
------------

In the Cloud9 environment, you deploy Docker and AWS CoPilot CLI.

1) In the AWS Cloud9 console, run the following commands one by one to install docker.

              sudo yum install update

              sudo yum install docker* -y

              sudo service docker start

2) Run docker –version command to verify the docker installation.

             docker --version
        

3) Run the following commands one by one to install AWS Copilot.
   

             sudo curl -Lo /usr/local/bin/copilot https://github.com/aws/copilot-cli/releases/download/v0.4.0/copilot-linux-v0.4.0
   
             sudo chmod +x /usr/local/bin/copilot

 4)   Next run the command copilot –help to verify if Copilot CLI is deployed.

            copilot --help

      ![image](https://github.com/RanguRahul/AWS-CoPilot/assets/120587828/07cd8112-60ad-4e5e-97d2-8ae3f87f6ef9)

  5) Step5: Create Container Application
     
       In this step, you create a sample container application and later use AWS Copilot CLI to deploy it.

       In Cloud9 environment, use New File menu option under File to create a new file index.html. Copy-paste the following HTML code into it.

     





