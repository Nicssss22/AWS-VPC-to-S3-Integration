<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Access S3 from a VPC

**Project Link:** [View Project](https://nextwork.ai/projects/36d7dc8f-3a9f-51ff-91ae-662077ea9920)

**Author:** agustinnico2302@gmail.com  
**Email:** agustinnico2302@gmail.com

---

![Image](https://nextwork.ai/content_gray_heroic_hyena/uploads/36d7dc8f-3a9f-51ff-91ae-662077ea9920_3e1e79a2)

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC gives you a private network in AWS to launch and manage your cloud resources. You can tailor it by setting security rules, directing network traffic, and grouping resources into subnets as your needs change.

### How I used Amazon VPC in this project

In today’s project, I used Amazon VPC to launch an EC2 instance in a public subnet, created access keys for the instance, and connected it to an S3 bucket.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project is that I can copy files from my local machine or EC2 to be the object of a S3 bucket.

### This project took me...

This project took me for about 1-2 hours because there are terms I wasn't familiar with and trying the understand what they mean.

## In the first part of my project...

### Step 1 - Architecture set up

In this step, I will create VPC from the scratch and launch an EC2 instance inside of it.

### Step 2 - Connect to my EC2 instance

I will connect to my EC2 instance using the EC2 instance Connect to directly access the server in AWS Management Console.

### Step 3 - Set up access keys

In this step, I will be generating an access key for my instance to it can finally communicate with AWS services.

## Architecture set up

I started my project by creating a VPC with one public subnet, where I I'd launch my EC2 instance. I also created a new security group upon the configuration of the EC2 rather using the default one.

I created an S3 budket then uploaded two (2) images to serve as the objects.

![Image](https://nextwork.ai/content_gray_heroic_hyena/uploads/36d7dc8f-3a9f-51ff-91ae-662077ea9920_4334d777)

## Running CLI commands

AWS CLI is a tool used to interact with the AWS services thru the use of command-line interface. Cloud engineers use this tool on making their work efficient by incorporating scripts and automation.

The first command I ran was the 'aws s3 ls' to list all my buckets in Amazon S3. However it failed because I didn't configured my AWS credentials first on my EC2 instance to know which account to access.

The second command I ran was 'aws configure'. It is used to configure AWS credentials in the EC2 instance. After a successful credential configuration, my instance can finally access AWS services using the authenticated account.

![Image](https://nextwork.ai/content_gray_heroic_hyena/uploads/36d7dc8f-3a9f-51ff-91ae-662077ea9920_e7fa8776)

## Access keys

### Credentials

To set up my EC2 instance to interact with my AWS environment, I configured it by entering the command "aws configure" then it prompts me to enter the AWS Access Key ID, Secret Access Key, Default region name, and defaut output format. After entering the correct details, the authentication will become successful and the machine can finally interact with the AWS environment.

Access keys are the credentials used by applications and other servers to authenticate an account and to access its available services. In my case, I will be using access keys of an IAM role and attach it to my EC2 instance.

Secret access keys are like passwords in any typical credentials like in Social Media Account, but in the context of authenticating an application or other servers to access AWS services from an account.

### Best practice

Although I'm using access keys in this project, a best practice alternative is to use the AWS CLI v2 using the 'aws login' command, which allows to login into AWS account using the browser as if your logging in AWS Management Console. Another alternative is to use the AWS CloudShell to directly interact with AWS services in Management Console by using a CLI.

## In the second part of my project...

### Step 4 - Set up an S3 bucket

In this step, I will create an S3 bucket so I could test my instance can reach that bucket.

### Step 5 - Connecting to my S3 bucket

I will connect my EC2 instance to my S3 bucket using the EC2 Instance Connect.

## Connecting to my S3 bucket

The first command I ran was the 'aws s3 ls' to list all my buckets in Amazon S3. However it failed because I didn't configured my AWS credentials first on my EC2 instance to know which account to access.

I ran to commands which is the 'aws sts get-caller-identity' to verify the logged in identity and 'aws s3 ls' to list all the listed s3 bucket. All commands shows the expected output.

![Image](https://nextwork.ai/content_gray_heroic_hyena/uploads/36d7dc8f-3a9f-51ff-91ae-662077ea9920_4334d778)

## Connecting to my S3 bucket

Another CLI command I ran was the 'aws s3 ls s3://nextwork-vpc-project-nicoagustins3vpc' which it listed all the objects within the specified bucket.

![Image](https://nextwork.ai/content_gray_heroic_hyena/uploads/36d7dc8f-3a9f-51ff-91ae-662077ea9920_4334d779)

## Uploading objects to S3

To upload a new file to my bucket, I first ran the command 'sudo touch /tmp/test.txt' to create an empty file.  

Second is that I ran 'aws s3 cp /tmp/test.txt s3://nextwork-vpc-project-NicoAgustinS3' to copy this newly created file to the S3 bucket.

Lastly, I ran 'aws s3 ls s3://nextwork-vpc-project-nicoagustins3vpc' to verify if the operation is successful.

![Image](https://nextwork.ai/content_gray_heroic_hyena/uploads/36d7dc8f-3a9f-51ff-91ae-662077ea9920_3e1e79a2)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/36d7dc8f-3a9f-51ff-91ae-662077ea9920)*
