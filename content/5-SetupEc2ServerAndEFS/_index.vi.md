---
title: "Thiết lập và cấu hình các máy chủ"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

#### Thiết lập và cấu hình các máy chủ

Trong phần này, chúng ta sẽ tiến hành quá trình thiết lập và cấu hình các máy chủ. Đầu tiên, chúng ta sẽ tạo một **Bastion Host** trong Public Subnet, cho phép truy cập an toàn vào các máy chủ ứng dụng trong Private Subnet. Tiếp theo, một máy chủ **EC2 Setup Server** sẽ được tạo trong Private Subnet chuẩn bị triển khai ứng dụng. Sau khi cấu hình xong, chúng ta sẽ tải mã nguồn từ **S3 Bucket** vào EC2 Setup Server và cập nhật cơ sở dữ liệu vào **RDS Instance**.

#### Nội dung

1. [Tạo Bastion Host trong Public Subnet](5.1-createbastionhost/)
2. [Tạo EC2 Setup Server trong Private Subnet](5.2-createec2setupserver/)
3. [Cấu hình cho EC2 Setup Server](5.3-configureec2/)
4. [Tải file từ S3 vào EC2 Setup Server](5.4-downloadsourcecodes3/)
5. [Cập nhật Database vào RDS Instance](5.5-updatedbtordsinstance/)
