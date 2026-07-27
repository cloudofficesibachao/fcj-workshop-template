---
title : "Thiết lập frontend trên AWS"
date : 2024-01-01 
weight : 4 
chapter : false
pre : " <b> 5.4. </b> "
---

Thiết lập frontend trên Amazon S3 và CloudFront
Backend stack đã tạo một S3 bucket riêng cho frontend. Trong giai đoạn đầu, frontend chạy local để kiểm tra API và Cognito; sau đó được build, upload lên S3 và phân phối riêng tư qua CloudFront.

Nội dung
Kết nối frontend với API và Cognito
Build và upload frontend lên S3
Thiết lập CloudFront và CORS
Kiểm tra hệ thống trên AWS
