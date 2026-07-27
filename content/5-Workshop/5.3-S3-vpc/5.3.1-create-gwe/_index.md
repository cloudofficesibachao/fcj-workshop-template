---
title : "Create CloudFormation stack"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.3.1 </b> "
---

Test the template and create the backend stack
1. Check the source code
cd backend
node --check functions\business-logic\app.mjs
node --check functions\image-processor\index.mjs
node --check functions\contract-expiry-notifier\index.mjs
npm test
2. Check the AWS SAM template
sam validate ` 
--template-file infra\template.yaml ` 
--lint ` 
--region ap-southeast-1
3. Build Lambda for AWS
sam build ` 
--use-container ` 
--config-file samconfig.toml ` 
--no-cached
4. Create CloudFormation stack
sam deploy ` 
--config-file samconfig.toml `
--template-file .aws-sam\build\template.yaml `

--parameter-overrides `
ProjectName=cloffice `
AlertEmail=YOUR_REAL_EMAIL `
CorsAllowOrigin="http://localhost:5173" `
EnablePointInTimeRecovery=false `
EnableCloudFront=false
Check the change set before confirming. CloudFormation will create resources and rollback if the setup fails.

5. Check the status
In the AWS Console, open CloudFormation → Stacks → cloffice-backend. The stack should change to CREATE_COMPLETE or UPDATE_COMPLETE.

Enhance system data security.
