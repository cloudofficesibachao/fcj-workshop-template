---
title : "Setting up AWS backend infrastructure"
date : 2024-01-01
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---


Setting up AWS backend infrastructure
The CloudOffice infrastructure is declared in the AWS SAM template and created synchronously by CloudFormation. The stack includes API Gateway, Lambda, DynamoDB, Cognito, S3, EventBridge, CloudWatch, and SNS.

Contents
Checking the template and creating the CloudFormation stack
Checking resources and initial data configuration
In the initial setup, it is recommended to leave EnableCloudFront=false and EnablePointInTimeRecovery=false. These two options can be enabled after the backend is stable and the budget has been reviewed.
The CloudOffice infrastructure is declared in the AWS SAM template and created synchronously by CloudFormation. The stack includes API Gateway, Lambda, DynamoDB, Cognito, S3, EventBridge, CloudWatch, and SNS.

Contents
Checking the template and creating the CloudFormation stack
Checking resources and initial data configuration
In the initial setup, it is recommended to leave EnableCloudFront=false and EnablePointInTimeRecovery=false. These two options can be enabled after the backend is stable and the budget has been reviewed.
