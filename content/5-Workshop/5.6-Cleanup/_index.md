---
Title: "Checking and Cleaning AWS Resources"
Date: 2024-01-01
Weight: 6
Chapter: False
Pre: "<b>5.6.</b>"
---


Checking Set-Up Resources
Before the workshop ends, check the CloudFormation stack, API Gateway, Lambda, DynamoDB, Cognito, S3, CloudFront, EventBridge, CloudWatch, and SNS. Record the stack output and test results.

Cleaning Up the Learning Environment
1. Account Verification
aws sts get-caller-identity
2. Delete the Main Stack
cd backend
sam delete --stack-name cloffice-backend --region ap-southeast-1
3. Dispose of Remaining Resources
If the S3 bucket still has objects, match the bucket name to the stack output before emptying it.
If a WAF was created at us-east-1, delete the separate WAF stack. Verify that the CloudFront distribution, CloudWatch Log Group, and SNS topic are no longer unexpected.
Open Billing and AWS Budget to confirm there are no longer any resources incurring costs.
Deleting the stack and data is irreversible. Always check your AWS Account, Region, stack name, and bucket name before proceeding.
