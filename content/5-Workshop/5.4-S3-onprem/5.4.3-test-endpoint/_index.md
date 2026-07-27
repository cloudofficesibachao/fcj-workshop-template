---
Title: "Setting Up CloudFront and CORS"
Date: 2024-01-01
Weight: 3
Chapter: False
Prefix: "<b>5.4.3</b>"
---

Setting Up Frontend Distribution with CloudFront
1. Enable CloudFront
After your account is approved by AWS, build and redeploy the stack with EnableCloudFront=true. CloudFormation will create the distribution, Origin Access Control, and bucket policy for the frontend.

2. Get Distribution Information
Get CloudFrontUrl and CloudFrontDistributionId from the stack output. Wait for the distribution to become Deployed.

3. Clear cache after frontend update
aws cloudfront create-invalidation `

--distribution-id YOUR_DISTRIBUTION_ID `

--paths "/*"
4. Tighten CORS
Deploy backend with CorsAllowOrigin using only https://...cloudfront.net, do not use * in production.

5. Verify
Website loads via HTTPS.
Refresh React routes directly without returning 403/404.
API requests do not have CORS errors.
S3 bucket remains private and only CloudFront can read the object.
