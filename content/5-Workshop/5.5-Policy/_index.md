---
Title: "Security, Monitoring, and Alerting Setup"
Date: 2024-01-01
Weight: 5
Chapter: False
Prefix: "<b>5.5</b>"
---

Security, Monitoring, and Alerting Setup
Completing Security and Monitoring Setup
IAM and Cognito
Use IAM Roles for Lambda instead of access keys.
Limit Lambda permissions to the specific DynamoDB table, S3 bucket, and SNS topic to be used.
Use Cognito JWT Authorizer for private APIs.
Check the admin group in the backend before performing administrative tasks.
S3 and CloudFront
Enable encryption and block public access for all three buckets.
Upload using short-term presigned URLs.
Use CloudFront OAC instead of public website buckets.
Augment AWS WAF to CloudFront if budget allows.
CloudWatch, SNS
Lambda's Log Group stores logs for 14 days.
CloudWatch Alarm alerts when Lambda Business Logic errors occur.
SNS sends emails to the operations manager.
Checklist
CORS only allows CloudFront URLs.
SNS subscription confirmed.
S3 is not public.
Users typically cannot access the admin API.
CloudWatch receives logs and metrics.
AWS Budget has cost alerts enabled.
