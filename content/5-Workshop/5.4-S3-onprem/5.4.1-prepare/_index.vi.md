---
title : "Kết nối frontend với AWS"
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

Nếu tất cả tài nguyên đều hoạt động, tiếp tục sang bước tạo Interface EndpointCấu hình API Gateway và Cognito cho frontend
Tạo frontend/.env.development.local từ CloudFormation output:

VITE_API_BASE_URL=https://YOUR_API_ID.execute-api.ap-southeast-1.amazonaws.com
VITE_COGNITO_USER_POOL_ID=YOUR_POOL_ID
VITE_COGNITO_CLIENT_ID=YOUR_CLIENT_ID
VITE_USE_DEMO_FALLBACK=false
VITE_BYPASS_ADMIN_AUTH=false
Chạy frontend với origin đã cho phép trong CORS:

cd D:\THUCTAPTT\cloudoffice
npm run frontend:dev:aws
Mở http://localhost:5173 và kiểm tra:

API /offices tải được dữ liệu DynamoDB.
Người dùng có thể đăng ký, xác nhận email và đăng nhập Cognito.
Token được gửi trong header Authorization cho API riêng tư.
Admin group truy cập được giao diện quản trị.
Sau khi thay đổi biến môi trường, phải khởi động lại Vite.


