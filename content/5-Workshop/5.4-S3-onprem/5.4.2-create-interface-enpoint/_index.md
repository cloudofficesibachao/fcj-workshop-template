---
Title: "Setting up the S3 frontend bucket"
Date: 2024-01-01
Weight: 2
Chapter: False
Prefix: "<b>5.4.2</b>"
---

Build and deploy the frontend to Amazon S3
1. Production Configuration
Create frontend/.env.production.local with the current API URL and Cognito ID.

2. Build the application
npm run frontend:build
3. Upload to S3
Compare the bucket with the output FrontendBucketName, then run:

aws s3 sync frontend\dist `

s3://YOUR_FRONTEND_BUCKET `
--delete `

--region ap-southeast-1
4. Check bucket configuration
Block Public Access is enabled.
Server-side encryption uses AES-256.

Do not create a public bucket policy.
CloudFront Origin Access Control will be the component reading the production object.
--delete removes the object that is no longer in the build directory. Only run this after confirming the frontend bucket is correct.

Create endpoint
