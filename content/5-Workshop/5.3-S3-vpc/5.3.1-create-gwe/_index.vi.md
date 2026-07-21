---
title : "Tạo một Gateway Endpoint"
date : 2024-01-01 
weight : 1
chapter : false
pre : " <b> 5.3.1 </b> "
---

Thực hiện
Đăng nhập AWS Management Console.
Tìm kiếm và mở dịch vụ Amazon VPC.
Trong thanh điều hướng bên trái, chọn Endpoints, sau đó nhấn Create endpoint.

Cấu hình Endpoint

Trong màn hình Create endpoint, cấu hình như sau:

Name tag cloud-office-s3-endpoint
Service category AWS services

Chọn VPC
Đây là VPC chứa toàn bộ tài nguyên của hệ thống Cloud Office như:

Backend Server (EC2)
Database Server
Private Subnet
Public Subnet

Sau khi tạo thành công S3 Gateway Endpoint:

Backend Server của Cloud Office có thể upload và download tài liệu từ Amazon S3.
Lưu lượng truyền giữa EC2 và S3 không đi qua Internet công cộng.
Giảm chi phí sử dụng NAT Gateway khi xử lý nhiều hợp đồng và tài liệu.
Tăng cường bảo mật cho dữ liệu của hệ thống.
