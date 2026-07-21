---
title: "Blog 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---
Cách sử dụng AD FS user và Tableau để truy vấn dữ liệu một cách an toàn trong AWS Lake Formation
Mục tiêu
Xây dựng giải pháp cho phép người dùng doanh nghiệp đăng nhập bằng tài khoản Active Directory (AD FS), truy cập Tableau và chỉ xem được dữ liệu mà họ được cấp quyền trong AWS Lake Formation.
Kiến trúc
User
│
▼
Active Directory
│
AD FS (SAML)
│
▼
AWS IAM Identity Center / IAM Role
│
▼
Tableau Server / Tableau Cloud
│
Athena
│
Lake Formation
│
Amazon S3 Data Lake
Lợi ích bảo mật
Single Sign-On (SSO)
Đăng nhập một lần bằng tài khoản AD.
Không cần tạo IAM User riêng.
Tuân thủ chính sách mật khẩu của doanh nghiệp.

Không sử dụng Access Key
Tableau không cần lưu:
Access Key
Secret Key
AWS cấp thông tin xác thực tạm thời (temporary credentials) sau khi xác thực thành công.

Fine-grained Access Control
Lake Formation hỗ trợ:
Row-level Security
Column-level Security
Cell Filtering
Ví dụ:
Kế toán xem được cột Salary.
Nhân viên chỉ xem được Employee Name.
Quản lý chỉ xem dữ liệu của phòng ban mình.
Audit
Mọi truy vấn đều được ghi lại qua:
AWS CloudTrail
Athena Query History
Lake Formation Audit Logs
Giúp truy vết ai đã truy cập dữ liệu, khi nào và truy vấn những gì.
Tính năng mới của các dịch vụ AWS
Một số tính năng đáng chú ý có thể áp dụng:
AWS Lake Formation
Fine-grained access control.
Row-level và column-level security.
LF-Tags để quản lý quyền theo nhãn.
Chia sẻ dữ liệu giữa nhiều tài khoản AWS bằng AWS RAM.
Tích hợp với IAM Identity Center.
Amazon Athena
Athena Engine v3 với hiệu năng tốt hơn.
Prepared Statements.
Query Result Reuse.
Apache Iceberg hỗ trợ ACID.
Truy vấn dữ liệu trực tiếp trên S3.
Amazon S3
S3 Intelligent-Tiering.
S3 Access Points.
S3 Object Lambda.
S3 Versioning.
Lifecycle Rules tự động chuyển dữ liệu sang lớp lưu trữ chi phí thấp.
Tableau
Hỗ trợ SAML SSO.
Kết nối trực tiếp với Athena.
Live Connection.
Extract Refresh.
Row-Level Security tích hợp.

IAM Identity Center
Quản lý tập trung người dùng và nhóm.
Federation với AD FS.
Temporary Credentials.
Permission Sets.
Tối ưu chi phí
-Lưu trữ dữ liệu ở định dạng Parquet
Thay vì: CSV sử dụng Parquet
Lợi ích:
Giảm dung lượng lưu trữ.
Athena chỉ đọc các cột cần thiết.
Giảm đáng kể chi phí truy vấn.
-Partition dữ liệu
Ví dụ:
/year=2025
/month=07
/day=15
Athena chỉ quét các phân vùng liên quan thay vì toàn bộ dữ liệu.
- Nén dữ liệu
Sử dụng:
Snappy
ZSTD
GZIP
để giảm dung lượng và chi phí quét dữ liệu.
-Lifecycle Policy
Thiết lập quy tắc:
Dữ liệu mới → S3 Standard.
Sau 30 ngày → S3 Standard-IA.
Sau 90 ngày → Glacier Instant Retrieval.
Sau 1 năm → Glacier Deep Archive.
-Query Result Reuse
Athena có thể tái sử dụng kết quả truy vấn nếu dữ liệu không thay đổi, giúp giảm số lần quét dữ liệu và chi phí.
- CloudFront (nếu có dashboard công khai)
Nếu Tableau được nhúng vào cổng thông tin web và có nội dung tĩnh, có thể dùng CloudFront để tăng tốc phân phối và giảm tải cho máy chủ.
- Auto Scaling
Nếu Tableau Server chạy trên:
Amazon EC2
Amazon ECS
có thể cấu hình Auto Scaling để mở rộng khi nhiều người dùng truy cập và thu hẹp khi tải thấp, tối ưu chi phí vận hành.
Nguồn link tham khảo : https://awsstudygroup.com/2022/08/16/cach-su-dung-ad-fs-user-va-tableau-de-truy-van-du-lieu-mot-cach-an-toan-trong-aws-lake-formation/
<img width="789" height="580" alt="Screenshot 2026-07-21 001955" src="https://github.com/user-attachments/assets/fcb4f2f2-46c7-4dfa-aa82-8767bd66ff53" />
