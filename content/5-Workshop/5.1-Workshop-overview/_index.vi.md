<img width="987" height="552" alt="z8017702787875_29f6937410b357be65366c9febe426db" src="https://github.com/user-attachments/assets/5d733047-90f6-4dbc-b01a-aa47816767c2" />
---
title : "Giới thiệu"
date : 2024-01-01 
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

Cloud Office – Hệ thống quản lý cho thuê văn phòng trên AWS

Giới thiệu

Cloud Office là hệ thống quản lý cho thuê văn phòng được xây dựng trên nền tảng điện toán đám mây Amazon Web Services (AWS) nhằm hỗ trợ các doanh nghiệp và đơn vị quản lý bất động sản văn phòng số hóa toàn bộ quy trình quản lý. Hệ thống cung cấp các chức năng từ quản lý tòa nhà, tầng, phòng làm việc, khách hàng, hợp đồng thuê, hóa đơn thanh toán đến theo dõi tình trạng sử dụng văn phòng và báo cáo thống kê.

Việc triển khai trên AWS giúp hệ thống có khả năng mở rộng linh hoạt, tính sẵn sàng cao, bảo mật tốt và tối ưu chi phí vận hành. Đồng thời, người dùng có thể truy cập hệ thống mọi lúc, mọi nơi thông qua trình duyệt web mà không cần cài đặt phần mềm.

Tổng quan hệ thống

Cloud Office được thiết kế theo mô hình ứng dụng web nhiều lớp (Multi-tier Architecture), bao gồm:

Frontend: Phát triển bằng Blazor Web App, cung cấp giao diện trực quan cho quản trị viên, nhân viên và khách hàng.
Backend: Xây dựng trên ASP.NET Core Web API, xử lý các nghiệp vụ như quản lý văn phòng, hợp đồng, khách hàng và thanh toán.
Database: Sử dụng Microsoft SQL Server trên Amazon RDS hoặc SQL Server cài đặt trên Amazon EC2 để lưu trữ dữ liệu.
Cloud Infrastructure: Hệ thống được triển khai trên AWS với các dịch vụ như EC2, RDS, S3, IAM, VPC và CloudWatch nhằm đảm bảo hiệu năng, tính bảo mật và khả năng giám sát.
