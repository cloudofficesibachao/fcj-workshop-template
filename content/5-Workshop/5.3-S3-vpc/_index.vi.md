---
title : "Thiết lập hạ tầng backend"
date : 2024-01-01 
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

Thiết lập hạ tầng backend AWS
Hạ tầng CloudOffice được khai báo trong AWS SAM template và được CloudFormation tạo đồng bộ. Stack bao gồm API Gateway, Lambda, DynamoDB, Cognito, S3, EventBridge, CloudWatch và SNS.

Nội dung
Kiểm tra template và tạo CloudFormation stack
Kiểm tra tài nguyên và cấu hình dữ liệu ban đầu
Ở lần thiết lập đầu tiên, nên để EnableCloudFront=false và EnablePointInTimeRecovery=false. Hai tùy chọn này có thể bật sau khi backend hoạt động ổn định và ngân sách đã được xem xét.
