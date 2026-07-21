---
title: "Blog 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---
Xây dựng kiến trúc dữ liệu hiện đại đa Region và đáng tin cậy bằng AWS Glue và AWS Lake Formation
1. Mục tiêu
Xây dựng một Data Lake đa Region (Multi-Region Data Lake) trên AWS nhằm:
Đảm bảo tính sẵn sàng cao (High Availability).
Hỗ trợ khôi phục sau thảm họa (Disaster Recovery - DR).
Quản lý và chia sẻ dữ liệu tập trung.
Phân quyền chi tiết đến từng bảng, cột hoặc hàng.
Phục vụ phân tích dữ liệu theo thời gian thực và theo lô (batch).

2. Kiến trúc tổng thể
+----------------+
| Data Sources |
| ERP, CRM, IoT |
+-------+--------+
|
AWS Glue Jobs
|
▼
Amazon S3 Data Lake (Primary Region)
|
+--------------+--------------+
| |
AWS Glue Data Catalog Lake Formation
| |
+--------------+--------------+
|
Amazon Athena
|
Amazon QuickSight
|
Business Users
Cross-Region Replication
│
▼
Amazon S3 (Secondary Region)
|
Glue Catalog Replication
|
Lake Formation
|
Athena / EMR / Redshift
3. Tính năng mới của các dịch vụ
AWS Glue
Glue Data Quality
Kiểm tra chất lượng dữ liệu tự động.
Phát hiện giá trị thiếu.
Phát hiện dữ liệu bất thường.
Sinh báo cáo Data Quality.

Glue Flex Jobs
Chi phí thấp hơn cho các tác vụ ETL không cần xử lý ngay.
Phù hợp với các công việc theo lịch hoặc không khẩn cấp.

Glue Studio
Thiết kế ETL trực quan (drag-and-drop).
Sinh mã PySpark tự động.
Dễ bảo trì và giảm thời gian phát triển.

Glue 5.0
Hỗ trợ Spark phiên bản mới.
Cải thiện hiệu năng xử lý.
Hỗ trợ Python mới.
Tối ưu cho Apache Iceberg, Hudi và Delta Lake.

AWS Lake Formation
LF-Tags
Quản lý quyền dựa trên nhãn (tag) thay vì từng bảng.
Ví dụ:
Department = Finance
Sensitivity = Confidential
Mọi bảng có cùng nhãn sẽ kế thừa chính sách truy cập.

Row-Level Security
Ví dụ:
User A
chỉ xem
Region = Hà Nội

Column-Level Security
Ví dụ:
Salary
chỉ HR được xem

Cross-Account Sharing
Chia sẻ Data Lake giữa nhiều tài khoản AWS mà không cần sao chép dữ liệu.

Hybrid Access Mode
Kết hợp quản lý quyền bằng IAM và Lake Formation để hỗ trợ quá trình chuyển đổi hoặc các hệ thống hiện hữu.
4. Lợi ích của kiến trúc
Tiêu chí
Giải pháp
High Availability
Dữ liệu được sao chép sang Region dự phòng bằng S3 Cross-Region Replication.
Disaster Recovery
Có thể chuyển sang Region thứ hai khi Region chính gặp sự cố.
Data Governance
Lake Formation quản lý quyền truy cập tập trung và chi tiết.
Khả năng mở rộng
Glue, Athena và S3 đều là dịch vụ serverless, tự động mở rộng theo nhu cầu.
Bảo mật
Mã hóa dữ liệu với AWS KMS, phân quyền bằng IAM và Lake Formation, ghi nhật ký với CloudTrail.
Hiệu năng
Parquet, Partition, Compression và Athena Engine v3 giúp giảm thời gian truy vấn.
Tối ưu chi phí
Sử dụng Glue Flex Jobs, S3 Lifecycle, Query Result Reuse và định dạng cột (Parquet) để giảm chi phí lưu trữ và phân tích.
Kết luận
Kiến trúc sử dụng AWS Glue và AWS Lake Formation giúp xây dựng một Data Lake hiện đại, đa Region và đáng tin cậy với khả năng quản trị dữ liệu tập trung, phân quyền chi tiết, tích hợp tốt với các dịch vụ phân tích như Athena và QuickSight. Kết hợp với Amazon S3 Cross-Region Replication, Glue Data Quality, Glue Flex Jobs, LF-Tags, Apache Iceberg và các kỹ thuật tối ưu lưu trữ như Parquet, Partition và Lifecycle Policies sẽ mang lại một nền tảng dữ liệu có khả năng mở rộng cao, đáp ứng yêu cầu về tính sẵn sàng, bảo mật và tối ưu chi phí cho doanh nghiệp.
Nguồn link tham khảo : https://awsstudygroup.com/2023/05/06/xay-dung-kien-truc-du-lieu-hien-dai-da-region-va-dang-tin-cay-bang-cach-su-dung-aws-glue-va-aws-lake-formation/<img width="807" height="342" alt="Screenshot 2026-07-21 003953" src="https://github.com/user-attachments/assets/0f6c0146-160a-42e6-af79-187e0ff1edd8" />
<img width="849" height="405" alt="Screenshot 2026-07-21 003923" src="https://github.com/user-attachments/assets/9706eb55-20ef-48e8-a26d-1694ba72a052" />
<img width="560" height="591" alt="Screenshot 2026-07-21 003857" src="https://github.com/user-attachments/assets/8acdffa6-8861-466c-8be7-e6aaff4ddb05" />
