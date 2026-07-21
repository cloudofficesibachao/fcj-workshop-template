---
title : "Tạo một S3 Interface endpoint"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.4.2 </b> "
---

Mục tiêu

Trong phần này, chúng ta sẽ tạo Interface Endpoint cho các dịch vụ AWS mà Cloud Office sử dụng.

Thực hiện

Mở Amazon VPC

Chọn

Endpoints

Chọn

Create endpoint

Name

Đặt tên

cloud-office-ssm-endpoint
Service Category

Chọn

AWS services
Services

Tìm

Systems Manager

hoặc

ssm

Chọn dịch vụ

com.amazonaws.<region>.ssm

Interface

VPC

Chọn

CloudOffice-VPC
Subnets

Chọn Private Subnet chứa Backend Server.

Security Group

Chọn Security Group của Interface Endpoint.

Security Group cần cho phép HTTPS (443) từ Backend Server.

Private DNS

Đánh dấu

Enable DNS name

Điều này giúp Backend Server có thể truy cập dịch vụ AWS bằng tên miền mặc định mà không cần thay đổi ứng dụng.

Nhấn

Create endpoint
