# Elastic Beanstalk Deployment of Python application

## 📌 Overview

A basic repository to deploy sample python application using elastic beanstalk service.

## 🔧 Answers to Questions

##How would it look like managing an application across multiple environments in Elastic Beanstalk? ##

Managing an application across multiple environments (dev, staging, prod) in Elastic Beanstalk involves setting environment-specific variables.

##Service Role vs. EC2 Instance Profile##
_Service Role:_

- Used by Elastic Beanstalk service itself <br>
- Manages resources on your behalf (EC2, ELB, ASG, etc.) <br>
- Needs permissions to create, modify, and delete AWS resources <br>
- Example permissions: elasticbeanstalk:_, ec2:_, elasticloadbalancing:\* <br>

_EC2 Instance Profile:_

- Used by EC2 instances running your application <br>
- Allows your application to access AWS services <br>
- Needs permissions specific to your application needs <br>
- Example permissions: s3:GetObject, dynamodb:Query, sqs:ReceiveMessage <br>

##Elastic Beanstalk can work with RDS in two ways:##

_Integrated RDS (not recommended for production):_

- Beanstalk creates and manages the RDS instance <br>
- Database is tied to the environment lifecycle <br>
- Database is terminated when environment is terminated <br>

_External RDS (recommended approach):_

- Create RDS separately using dedicated resources <br>
- Connect via environment variables <br>
- Database lifecycle is independent of environment <br>

## 🚀 Extras

**CLI command for Ubuntu WSL for zipping and unzipping the package**

`sh \n echo "zip python2.zip *" \n `
✅ This creates python2.zip containing all files in the current directory.

`sh \n echo "unzip python2.zip -d your_destination_folder/" \n `
✅ Extract python2.zip content to a your desired folder
