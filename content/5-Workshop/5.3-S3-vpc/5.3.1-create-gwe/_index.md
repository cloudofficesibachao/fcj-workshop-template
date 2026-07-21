---
title : "Create a gateway endpoint"
date : 2024-01-01 
weight : 1
chapter : false
pre : " <b> 5.3.1 </b> "
---



Instructions:

Log in to the AWS Management Console.
Search for and open the Amazon VPC service.

In the left-hand navigation bar, select Endpoints, then click Create endpoint.

Configure the Endpoint

In the Create endpoint screen, configure as follows:

Name tag: cloud-office-s3-endpoint
Service category: AWS services

Select VPC
This VPC contains all the resources of the Cloud Office system, such as:

Backend Server (EC2)
Database Server
Private Subnet
Public Subnet

After successfully creating the S3 Gateway Endpoint:

The Cloud Office Backend Server can upload and download documents from Amazon S3.
Traffic between EC2 and S3 does not go through the public internet.
Reduces the cost of using NAT Gateway when handling many contracts and documents.
Enhances the security of the system's data.
