---
title : "Test the Interface Endpoint"
date : 2024-01-01
weight : 3
chapter : false
pre : " <b> 5.4.3 </b> "
---

After the Endpoint is in the Available state, proceed with testing.

Open

AWS Systems Manager

↓

Session Manager

↓

Connect to

CloudOffice-Backend

After successfully logging in, run the command

aws ssm describe-instance-information

If the command returns EC2 information, it means the Backend Server has successfully accessed the AWS service through the Endpoint Interface.




