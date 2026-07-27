---
title: "Preparation Steps"
date: 2024-01-01
weight: 2
chapter: false
pre: "<b>5.2.</b>"
---

Setting up your AWS account and environment
1. Select a Region
Log in to the AWS Management Console and select the Asia Pacific (Singapore) Region – ap-southeast-1. Use this Region consistently for CloudFormation, Lambda, DynamoDB, Cognito, S3, and CloudWatch.

2. Set up account security
Enable MFA for the root user and do not use the root user for daily tasks.
Create an IAM user or IAM Identity Center user for deployment purposes.
Grant only necessary permissions to CloudFormation, Lambda, API Gateway, DynamoDB, S3, Cognito, IAM, CloudWatch, EventBridge, and SNS.
Do not store access keys in source code or upload them to Git.

3. Set up cost management
Open Billing and Cost Management to check the Free Tier and invoices.
Create an AWS Budget with appropriate thresholds for the learning environment.
Configure email alerts when actual or projected costs exceed the thresholds.
4. Install the tools
Install Node.js 22.x, npm, AWS CLI v2, AWS SAM CLI, and Docker Desktop, then check:

node --version
npm --version
aws --version
sam --version
docker --version
5. Configure AWS CLI
aws configure
aws sts get-caller-identity
aws configure get region
The get-caller-identity result must match the expected AWS Account, and the default Region should be ap-southeast-1.

6. Prepare the source code
npm install
npm run frontend:install
npm run backend:install
Do not proceed with deployment if the AWS Account or Region is incorrect. Docker must run before building Lambda with the sharp library.

Easy to update or delete the entire infrastructure via the Stack.
