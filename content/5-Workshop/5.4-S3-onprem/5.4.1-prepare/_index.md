---
Title: "Connecting the frontend to AWS"
Date: 2024-01-01
Weight: 1
Chapter: False
Prefix: "<b>5.4.1</b>"
---

Before creating an Interface Endpoint, you need to check that the Cloud Office infrastructure is fully deployed.

The practice environment includes:

CloudOffice VPC
Public Subnet
Private Subnet
Backend Server (Amazon EC2)
Security Group
Route Table

The Backend Server is located in the Private Subnet and will use Interface Endpoint to connect to AWS services.

Check the infrastructure

Log in to the AWS Console.

Open the Amazon VPC service.

Verification:

VPC CloudOffice
Private Subnet
Security Group
EC2 Backend

If all resources are working, proceed to the step of creating the Interface Endpoint. Configure API Gateway and Cognito for the frontend.
Create frontend/.env.development.local from CloudFormation output:

VITE_API_BASE_URL=https://YOUR_API_ID.execute-api.ap-southeast-1.amazonaws.com
VITE_COGNITO_USER_POOL_ID=YOUR_POOL_ID
VITE_COGNITO_CLIENT_ID=YOUR_CLIENT_ID
VITE_USE_DEMO_FALLBACK=false
VITE_BYPASS_ADMIN_AUTH=false
Run the frontend with the origin enabled in CORS:

cd D:\THUCTAPTT\cloudoffice
npm run frontend:dev:aws
Open http://localhost:5173 and check:

The /offices API can load DynamoDB data.

Users can register, confirm email, and log in to Cognito.
A token is sent in the Authorization header for the private API.
The admin group can access the administration interface.
After changing environment variables, Vite must be restarted.
