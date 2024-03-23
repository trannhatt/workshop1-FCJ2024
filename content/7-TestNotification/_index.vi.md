---
title: "Kiểm tra thông báo"
date: "`r Sys.Date()`"
weight: 7
chapter: false
pre: " <b> 7. </b> "
---

#### Kiểm tra thông báo

Chúng ta sẽ giả sử một máy chủ EC2 Web Server bị sự cố bằng cách Terminate, và xem việc nhận thông báo về sữ cố qua Email mà chúng ta đã cung cấp từ trước.

1. Tại giao diện **EC2**

   - Chọn **Instances**
   - Chọn vào một máy chủ Web **bookstore-asg**
   - Trên thanh **Instance state** chọn **Terminate instance**

   ![Test Notification](/workshop1-FCJ2024/images/7-TestNotification/0001-testnotifi.png?featherlight=false&width=90pc)

2. Trong phần **Terminate instance?**, chọn **Terminate**

   ![Test Notification](/workshop1-FCJ2024/images/7-TestNotification/0002-testnotifi.png?featherlight=false&width=90pc)

3. Chờ đợi một lúc, vào Email đã đăng ký, chúng ta thấy rằng có một Email đã được gửi đến với nội dung như sau:

   ![Test Notification](/workshop1-FCJ2024/images/7-TestNotification/0003-testnotifi.png?featherlight=false&width=90pc)
