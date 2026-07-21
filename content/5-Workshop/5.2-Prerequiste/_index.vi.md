---
title : "Các bước chuẩn bị"
date : 2024-01-01 
weight : 2
chapter : false
pre : " <b> 5.2. </b> "
---

#### IAM permissions
Gắn IAM permission policy sau vào tài khoản aws user của bạn để triển khai và dọn dẹp tài nguyên trong workshop này.
```
### IAM Permissions

Gắn IAM Policy sau vào tài khoản AWS của bạn để chuẩn bị quyền tạo tài nguyên cho hệ thống Cloud Office:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "CloudOfficePermissions",
            "Effect": "Allow",
            "Action": [
                "cloudformation:*",
                "s3:*",
                "rds:*",
                "cognito-idp:*",
                "ec2:*",
                "iam:PassRole",
                "iam:CreateRole"
            ],
            "Resource": "*"
        }
    ]
}

#### Khởi tạo tài nguyên bằng CloudFormation
Giới thiệu

AWS CloudFormation là dịch vụ cho phép triển khai hạ tầng dưới dạng mã (Infrastructure as Code - IaC). Thay vì tạo từng tài nguyên thủ công trên AWS Console, người dùng chỉ cần chuẩn bị một tệp YAML hoặc JSON mô tả hạ tầng. CloudFormation sẽ tự động tạo và cấu hình các tài nguyên theo đúng định nghĩa.

Trong workshop Cloud Office, CloudFormation được sử dụng để tạo nhanh các thành phần hạ tầng như:

Virtual Private Cloud (VPC)
Public Subnet
Internet Gateway
Route Table
Security Group
Amazon EC2 Instance
IAM Instance Profile (nếu cần)

Việc sử dụng CloudFormation mang lại nhiều lợi ích như:

Triển khai hạ tầng nhanh chóng và nhất quán.
Dễ dàng tái sử dụng cho nhiều môi trường (Development, Testing, Production).
Giảm sai sót khi cấu hình thủ công.
Dễ dàng cập nhật hoặc xóa toàn bộ hạ tầng thông qua Stack.
