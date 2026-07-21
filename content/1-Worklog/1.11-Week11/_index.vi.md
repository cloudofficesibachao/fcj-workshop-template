---
title: "Worklog Tuần 11"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---

Báo cáo thực tập tuần 11

1. Nội dung công việc thực hiện

* Nghiên cứu quy trình thiết kế API Flow cho chức năng người dùng gửi nội dung (User Submissions).
* Tìm hiểu quy trình tải ảnh (Photo Upload) lên Amazon S3 và cách lưu trữ thông tin ảnh trong cơ sở dữ liệu.
* Thiết kế luồng xử lý dữ liệu từ phía người dùng đến Backend thông qua API Gateway.
* Xây dựng sơ đồ luồng xử lý cho các chức năng tạo bài đăng, tải ảnh và truy xuất dữ liệu.
* Tìm hiểu cơ chế phân quyền người dùng khi thực hiện các thao tác gửi dữ liệu và tải ảnh.
* Thảo luận với nhóm về cấu trúc API và cách tổ chức dữ liệu nhằm đảm bảo khả năng mở rộng và bảo trì hệ thống.

2. Kết quả đạt được

* Hiểu được quy trình hoạt động của API phục vụ chức năng User Submissions.
* Nắm được cách tích hợp Amazon S3 để lưu trữ hình ảnh và quản lý metadata của ảnh.
* Thiết kế được luồng xử lý dữ liệu giữa Client, API Gateway, Backend và các dịch vụ AWS.
* Hoàn thiện sơ đồ API Flow phục vụ cho việc phát triển các chức năng tiếp theo của dự án.
* Củng cố kiến thức về thiết kế RESTful API và cách tổ chức luồng dữ liệu trong hệ thống Cloud.

3. Khó khăn gặp phải

* Ban đầu còn gặp khó khăn trong việc xác định thứ tự xử lý giữa việc tải ảnh và lưu dữ liệu bài đăng.
* Chưa quen với việc thiết kế luồng API cho nhiều trường hợp ngoại lệ như lỗi tải ảnh hoặc dữ liệu không hợp lệ.
* Việc kết nối giữa các thành phần AWS cần được nghiên cứu thêm để tối ưu hiệu suất và bảo mật.

4. Cách giải quyết

* Đọc lại tài liệu workshop và tài liệu AWS về API Gateway, Amazon S3 và kiến trúc Serverless.
* Thảo luận với các thành viên trong nhóm để thống nhất quy trình xử lý dữ liệu.
* Thiết kế sơ đồ luồng từng bước trước khi xây dựng API nhằm hạn chế sai sót trong quá trình phát triển.
* Kiểm tra lại các trường hợp ngoại lệ để đảm bảo API hoạt động ổn định.

5. Kế hoạch tuần tiếp theo

* Tiến hành hiện thực các API theo thiết kế đã xây dựng.
* Tích hợp chức năng Upload ảnh với Amazon S3 vào hệ thống.
* Kiểm thử các API bằng Postman và đánh giá kết quả trả về.
* Hoàn thiện chức năng User Submissions và tiếp tục tối ưu hiệu năng, bảo mật của hệ thống.
* Chuẩn bị tài liệu kỹ thuật và cập nhật tiến độ dự án cho nhóm.
