---
title: "Xây dựng một AWS Network VPC 3 tầng"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

#### Xây dựng một AWS Network VPC 3 tầng

Trong phần này, chúng ta sẽ xây dựng một AWS Network VPC 3 tầng như sau:

- **VPC** sẽ được tạo trong 2 availability zones với 1 public subnet và 2 private subnets trong mỗi AZ.
- 1 **Internet Gateway** được sử dụng để cho phép giao tiếp giữa các instance trong VPC và Internet.
- Chúng ta sẽ sử dụng 2 **Availability Zones** để đảm bảo khả năng sẵn sàng cao và có khả năng chịu lỗi.
- Các tài nguyên như Nat Gateway, Bastion Host và Application Load Balancer sẽ được triển khai trong **Public subnets**.
- Chúng tôi sẽ đặt các webservers và database servers trong các **Private Subnets** để bảo vệ chúng.
- **Public Route Table** được liên kết với các pubic subnets và định tuyến lưu lượng truy cập vào Internet thông qua internet gateway.
- **Main Route Table** được liên kết với các private subnets.

#### Nội dung

1. [Tạo và cấu hình VPC](2.1-vpc/)
2. [Tạo và gắn Internet Gateway (IGW) vào VPC](2.2-internetgateway/)
3. [Tạo và cấu hình các Subnet](2.3-subnet/)
4. [Tạo và cấu hình các Route Table](2.4-routetable/)
