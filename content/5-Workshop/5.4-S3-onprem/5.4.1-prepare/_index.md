---
title : "Prepare the environment"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.4.1 </b> "
---

Before creating an Interface Endpoint, verify that the Cloud Office infrastructure is fully deployed.

The practice environment includes:

CloudOffice VPC
Public Subnet
Private Subnet
Backend Server (Amazon EC2)
Security Group
Route Table

The Backend Server is located in the Private Subnet and will use Interface Endpoint to connect to AWS services.

Infrastructure Verification

Log in to the AWS Console.

Open the Amazon VPC service.

Verify:

VPC CloudOffice
Private Subnet
Security Group
EC2 Backend

If all resources are working, proceed to the Interface Endpoint creation step.
