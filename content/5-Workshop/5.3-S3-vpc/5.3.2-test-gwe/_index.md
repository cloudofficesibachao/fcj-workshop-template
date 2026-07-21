---
title : "Test the Gateway Endpoint"
date : 2024-01-01 
weight : 2
chapter : false
pre : " <b> 5.3.2 </b> "
---

In a Cloud Office system, the Backend Server is responsible for handling document storage operations such as office lease agreements, invoices, office images, and customer attachments. This verification confirms that the server can communicate with Amazon S3 via the Gateway Endpoint without using an Internet Gateway or NAT Gateway.

Creating an Amazon S3 Bucket

First, create an S3 Bucket to store Cloud Office system documents.

Log in to the AWS Management Console.

Open the Amazon S3 service.

Select Create bucket.

Configure Bucket
In the Create bucket screen, enter the following information: Bucket name
The name of the Bucket that will be used to store:
Office lease agreements
Invoices
Office images
Customer profiles
Attachments

Keep the remaining default settings and select Create bucket.

Connecting to the Backend Server using AWS Session Manager

To test the connection to Amazon S3, we will log into the Backend Server via AWS Systems Manager Session Manager.

Session Manager is a feature of AWS Systems Manager that allows administrators to access EC2 through a browser without needing:

SSH Key Pair
Public IP
Bastion Host
Opening an SSH port (22)

Starting a Session
Search for Systems Manager on the AWS Console.

Select Session Manager.

Select Start Session.
Select the EC2 Instance running the Cloud Office Backend.

Creating a Template Document and Uploading it to Amazon S3
* Go back to the user directory
* Create a template document
* Upload the template to Amazon S3

Checking the Data on Amazon S3

Return to the Amazon S3 Console.

Open the Bucket you just created.

You will see the file appear in the Bucket.

This proves that the Backend Server has been able to upload the document to Amazon S3.








