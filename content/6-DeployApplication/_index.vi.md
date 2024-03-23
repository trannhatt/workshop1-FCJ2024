---
title: "Triển khai ứng dụng"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

#### Triển khai ứng dụng

Trong phần này, chúng ta sẽ tạo Application Load Balancer để phân phối tải và điều hướng yêu cầu từ người dùng đến các máy chủ ứng dụng EC2. Việc tạo AMI và Launch Template giúp đơn giản hóa quá trình triển khai, trong khi Auto Scaling Group tự động mở rộng hoặc thu hẹp số lượng máy chủ EC2 dựa trên tải. Cuối cùng, chúng ta sẽ tạo CloudFront distribution và Web ACL giúp cải thiện bảo mật và hiệu suất của ứng dụng.

#### Nội dung

1. [Tạo Target Group](6.1-createtargetgroup/)
2. [Tạo Application Load Balancer](6.2-createalb/)
3. [Tạo AMI](6.3-createami/)
4. [Tạo Launch Template](6.4-createlaunchtemp/)
5. [Tạo Autoscaling Group](6.5-createasg/)
6. [Tạo Cloudfront và Web ACL](5.5-updatedbtordsinstance/)
