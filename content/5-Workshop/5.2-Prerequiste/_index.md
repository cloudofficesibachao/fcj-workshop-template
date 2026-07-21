---
title: "Preparation Steps"
date: 2024-01-01
weight: 2
chapter: false
pre: "<b>5.2.</b>"
---

### IAM Permissions

Attach the following IAM Policy to your AWS account to prepare permissions for creating resources for the Cloud Office system:

```json
{

"Version": "2012-10-17",

"Statement": [

{
"Sid": "CloudOfficePermissions",

"Effect": "Allow",

"Action": [
"cloudformation:*",

"s3:*",

"rds:*",

"cognito-idp:*",

"ec2:*",

"iam:PassRole",

"iam:CreateRole"

],

"Resource": "*"

}
]
}

#### Initialize resources using CloudFormation
Introduction

AWS CloudFormation is a service that allows infrastructure deployment as code (IaC). Instead of manually creating each resource on the AWS Console, users only need to prepare a YAML or JSON file describing the infrastructure. CloudFormation will automatically create and configure the resources according to the definition.

In the Cloud Office workshop, CloudFormation is used to quickly create infrastructure components such as:

Virtual Private Cloud (VPC)
Public Subnet
Internet Gateway
Route Table
Security Group
Amazon EC2 Instance
IAM Instance Profile (if needed)

Using CloudFormation offers many benefits such as:

Fast and consistent infrastructure deployment.

Easily reusable across multiple environments (Development, Testing, Production).

Reduced errors compared to manual configuration.

Easy to update or delete the entire infrastructure via the Stack.
