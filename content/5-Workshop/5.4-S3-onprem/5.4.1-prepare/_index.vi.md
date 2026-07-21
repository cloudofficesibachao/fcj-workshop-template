---
title : "Chuẩn bị tài nguyên"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.4.1 </b> "
---

Trước khi tạo Interface Endpoint, cần kiểm tra hạ tầng Cloud Office đã được triển khai đầy đủ.

Môi trường thực hành bao gồm:

CloudOffice VPC
Public Subnet
Private Subnet
Backend Server (Amazon EC2)
Security Group
Route Table

Backend Server được đặt trong Private Subnet và sẽ sử dụng Interface Endpoint để kết nối tới các dịch vụ AWS.

Kiểm tra hạ tầng

Đăng nhập AWS Console.

Mở dịch vụ Amazon VPC.

Kiểm tra:

VPC CloudOffice
Private Subnet
Security Group
EC2 Backend

Nếu tất cả tài nguyên đều hoạt động, tiếp tục sang bước tạo Interface Endpoint


