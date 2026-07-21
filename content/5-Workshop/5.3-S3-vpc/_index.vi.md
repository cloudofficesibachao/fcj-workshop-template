---
title : "Truy cập S3 từ VPC"
date : 2024-01-01 
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

1. Giới thiệu về S3 Gateway Endpoint

Amazon S3 Gateway Endpoint là một loại VPC Endpoint cho phép các tài nguyên bên trong Amazon VPC truy cập trực tiếp tới dịch vụ Amazon S3 thông qua mạng nội bộ của AWS. Không giống việc truy cập S3 qua Internet Gateway hoặc NAT Gateway, Gateway Endpoint sử dụng các tuyến (Route Table) trong VPC để định tuyến lưu lượng tới S3, giúp dữ liệu không phải đi qua Internet công cộng.

2. Bối cảnh của hệ thống Cloud Office

Trong hệ thống Cloud Office, người dùng thường xuyên tải lên và tải xuống nhiều loại tài liệu như hợp đồng thuê văn phòng, hình ảnh văn phòng, hóa đơn thanh toán và các giấy tờ xác minh khách hàng. Các tài liệu này đều được lưu trữ trên Amazon S3 nhằm đảm bảo khả năng mở rộng và độ bền dữ liệu.

Backend của hệ thống được triển khai trên Amazon EC2 trong Private Subnet để tăng tính bảo mật. Nếu không cấu hình S3 Gateway Endpoint, các yêu cầu truy cập S3 sẽ phải đi qua NAT Gateway hoặc Internet Gateway. Điều này vừa làm tăng chi phí truyền dữ liệu vừa tạo thêm một điểm kết nối ra Internet không cần thiết.

3. Kiến trúc trước và sau khi cấu hình

Trước khi tạo Gateway Endpoint

Backend EC2
      │
      ▼
NAT Gateway
      │
      ▼
Internet
      │
      ▼
Amazon S3

Sau khi tạo Gateway Endpoint

Backend EC2
      │
      ▼
Route Table
      │
      ▼
S3 Gateway Endpoint
      │
      ▼
Amazon S3
