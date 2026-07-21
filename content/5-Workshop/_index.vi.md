---
title: "Workshop"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

Cloud Office -Hệ thống quản lý cho thuê văn phòng trên AWS

Cloud Office là nền tảng quản lý và đặt thuê văn phòng được xây dựng theo mô hình cloud-native. Dự án được thiết kế theo kiến trúc tách biệt giữa Frontend và Backend, giúp quá trình phát triển, triển khai và bảo trì trở nên thuận tiện hơn. Đồng thời, việc tách riêng các thành phần cũng giúp giảm tải khi cài đặt các thư viện Node.js, tối ưu quy trình phát triển và phù hợp với kiến trúc serverless trên nền tảng AWS.

Giao diện Public hướng đến khách hàng có nhu cầu tìm kiếm và thuê văn phòng. Người dùng có thể tìm kiếm, xem thông tin chi tiết, hình ảnh và gửi yêu cầu thuê trực tiếp thông qua hệ thống.

Khu vực Admin được xây dựng dành cho quản trị viên, tập trung vào việc quản lý dữ liệu và vận hành hệ thống. Các chức năng chính bao gồm quản lý văn phòng, khách hàng, hợp đồng, yêu cầu thuê, xử lý hình ảnh, theo dõi trạng thái hệ thống và thực hiện các thao tác CRUD (Create, Read, Update, Delete) đối với các dữ liệu nghiệp vụ.




#### Nội dung

1. [Tổng quan về workshop](5.1-Workshop-overview/)
2. [Chuẩn bị](5.2-Prerequiste/)
3. [Truy cập đến S3 từ VPC](5.3-S3-vpc/)
4. [Truy cập đến S3 từ TTDL On-premises](5.4-S3-onprem/)
5. [VPC Endpoint Policies (làm thêm)](5.5-Policy/)
6. [Dọn dẹp tài nguyên](5.6-Cleanup/)
