---
Title: "Checking and Configuring Backend Resources"
Date: 2024-01-01
Weight: 2
Chapter: False
Pre: "<b>5.3.2</b>"
---
Checking AWS Services After Creating the Stack
1. Get Stack Output
aws cloudformation describe-stacks `

--stack-name cloffice-backend `

--region ap-southeast-1 `

--query "Stacks[0].Outputs"
Save ApiUrl, CognitoUserPoolId, CognitoClientId, FrontendBucketName, StorageBucketName, and ProcessedBucketName.

2. Check Each Service
API Gateway: HTTP API cloffice-api has CloudOffice routes.

Lambda: business logic, image processor, and contract expiry notifier are active.

DynamoDB: The cloffice-offices-table is set to On-Demand mode and has GSI1–GSI3.

Cognito: The User Pool, App Client, and admin group have been created.

S3: Encryption and Public Access are enabled on the frontend, storage, and processed buckets.

CloudWatch/SNS: Log groups, alarms, and alert topics exist.

3. Confirm SNS
Open the email specified in AlertEmail and select Confirm subscription.

4. Seed DynamoDB data
cd D:\THUCTAPTT\cloudoffice\backend
npm run seed --table cloffice-offices-table --region ap-southeast-1
5. Create Cognito admin
Use AWS CLI or Cognito Console to create a user, set a permanent password, and add them to the admin group. Then call ApiUrl/offices to confirm the public API returns data.
This demonstrates that the Backend Server was able to upload documents to Amazon S3 via the Gateway Endpoint.
