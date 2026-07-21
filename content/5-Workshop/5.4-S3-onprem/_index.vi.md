---
title : "Truy cập S3 từ môi trường truyền thống"
date : 2024-01-01 
weight : 4 
chapter : false
pre : " <b> 5.4. </b> "
---

Trong hệ thống Cloud Office, Backend Server được triển khai trong Private Subnet nhằm hạn chế truy cập trực tiếp từ Internet. Tuy nhiên, máy chủ vẫn cần kết nối tới một số dịch vụ của AWS để phục vụ quá trình vận hành hệ thống như:

AWS Systems Manager (SSM) để quản trị máy chủ.
Amazon CloudWatch để thu thập log và giám sát ứng dụng.
AWS Secrets Manager (nếu sử dụng) để lưu trữ chuỗi kết nối cơ sở dữ liệu và các thông tin nhạy cảm.

Nếu không sử dụng VPC Interface Endpoint, các yêu cầu này sẽ phải đi qua Internet Gateway hoặc NAT Gateway. Điều này vừa làm tăng chi phí vừa giảm mức độ bảo mật.

Trong phần thực hành này, chúng ta sẽ tạo VPC Interface Endpoint để Backend Server của Cloud Office có thể truy cập các dịch vụ AWS hoàn toàn thông qua mạng nội bộ của AWS.
