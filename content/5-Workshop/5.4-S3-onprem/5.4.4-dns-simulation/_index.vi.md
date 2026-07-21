---
title : "Mô phỏng On-premises DNS "
date : 2024-01-01
weight : 4
chapter : false
pre : " <b> 5.4.4 </b> "
---

Để kiểm tra Private DNS, thực hiện trên Backend Server:

nslookup ssm.ap-southeast-1.amazonaws.com

Kết quả sẽ trả về địa chỉ IP riêng của Interface Endpoint trong VPC.

Điều này chứng minh rằng yêu cầu từ Backend Server không đi qua Internet mà được chuyển trực tiếp tới Interface Endpoint thông qua mạng nội bộ của AWS.
