---
Title: "Setting up the frontend on AWS"
Date: 2024-01-01
Weight: 4
Chapter: False
Pre: "<b>5.4.</b>"
---

Setting up the frontend on Amazon S3 and CloudFront
The backend stack created a separate S3 bucket for the frontend. Initially, the frontend ran locally to test the API and Cognito; it was then built, uploaded to S3, and privately distributed via CloudFront.

Contents
Connecting the frontend to the API and Cognito
Building and uploading the frontend to S3
Setting up CloudFront and CORS
Testing the system on AWS
