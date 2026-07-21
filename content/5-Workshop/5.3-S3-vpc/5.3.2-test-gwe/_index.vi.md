---
title : "Kiểm tra Gateway Endpoint"
date : 2024-01-01 
weight : 2
chapter : false
pre : " <b> 5.3.2 </b> "
---

Trong hệ thống Cloud Office, Backend Server chịu trách nhiệm xử lý các thao tác lưu trữ tài liệu như hợp đồng thuê văn phòng, hóa đơn, hình ảnh văn phòng và các tài liệu đính kèm của khách hàng. Việc kiểm tra này giúp xác nhận rằng máy chủ có thể giao tiếp với Amazon S3 thông qua Gateway Endpoint mà không cần sử dụng Internet Gateway hoặc NAT Gateway.

Tạo Amazon S3 Bucket

Đầu tiên, tạo một S3 Bucket để lưu trữ tài liệu của hệ thống Cloud Office.

Đăng nhập AWS Management Console.
Mở dịch vụ Amazon S3.
Chọn Create bucket.

Cấu hình Bucket
Trong màn hình Create bucket, nhập các thông tin: Bucket name
Tên Bucket sẽ được sử dụng để lưu:
Hợp đồng thuê văn phòng
Hóa đơn thanh toán
Hình ảnh văn phòng
Hồ sơ khách hàng
Các tài liệu đính kèm

Giữ nguyên các thiết lập mặc định còn lại và chọn Create bucket.


Kết nối Backend Server bằng AWS Session Manager

Để kiểm tra kết nối đến Amazon S3, chúng ta sẽ đăng nhập vào Backend Server thông qua AWS Systems Manager Session Manager.

Session Manager là một tính năng của AWS Systems Manager cho phép quản trị viên truy cập EC2 thông qua trình duyệt mà không cần:

SSH Key Pair
Public IP
Bastion Host
Mở cổng SSH (22)

Bắt đầu phiên làm việc
Tìm kiếm Systems Manager trên AWS Console.
Chọn Session Manager.
Chọn Start Session.
Chọn EC2 Instance chạy Backend của Cloud Office.

Tạo tài liệu mẫu và tải lên Amazon S3
* Chuyển về thư mục người dùng
* Tạo 1 tài liệu mẫu
* Tải mẫu lên Amazon S3

Kiểm tra dữ liệu trên Amazon S3

Quay lại Amazon S3 Console.

Mở Bucket vừa tạo.

Bạn sẽ thấy tệp xuất hiện trong Bucket.

Điều này chứng minh rằng Backend Server đã có thể tải tài liệu lên Amazon S3 thông qua Gateway Endpoint.

