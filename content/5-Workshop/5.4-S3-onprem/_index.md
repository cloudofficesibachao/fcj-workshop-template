---
Title: "AWS System Test"
Date: 2024-01-01
Weight: 4
Chapter: False
Pre: "<b>5.4.</b>"
---

AWS Post-Setup Test
Authentication and Authorization
Register, verify email, and log in using Cognito.
Test the private API rejecting requests lacking tokens.
Test for users who frequently cannot use admin functions.
Data and Business
View office listings and details from DynamoDB.
Create rental requests, appointments, and verify that data is saved correctly.
Upload images or documents using presigned URLs.
Confirm that the Lambda Image Processor creates images in the processed bucket.
Operations
Check the logs of each Lambda in CloudWatch.
View CloudWatch Alarm error metrics and status.
Confirm that SNS is ready to send emails.
Check the EventBridge schedule of the Contract Expiry Notifier.
If errors occur, review the API Gateway CORS, Lambda Logs, IAM Role, and frontend environment variables before redeploying.
