---
title : "Private-AWS-Services"
date : 2024-01-01
weight : 4
chapter : false
pre : " <b> 5.4.4 </b> "
---

To check the Private DNS, perform the following on the Backend Server:

nslookup ssm.ap-southeast-1.amazonaws.com

The result will return the private IP address of the Interface Endpoint in the VPC.

This proves that the request from the Backend Server does not go over the Internet but is routed directly to the Interface Endpoint via the AWS internal network.
