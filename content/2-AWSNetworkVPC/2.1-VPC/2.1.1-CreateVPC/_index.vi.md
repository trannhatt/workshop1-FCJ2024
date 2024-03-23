---
title: "Tạo VPC"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.1.1 </b> "
---

#### Tạo VPC

1. Tại giao diện **AWS console**

   - Nhấn chọn thanh tìm kiếm và nhập **`VPC`**
   - Tại mục **Services** chọn **VPC**

   ![Create VPC](/workshop1-FCJ2024/images/2.1-VPC/2.1.1-CreateVPC/0001-createvpc.png?featherlight=false&width=90pc)

2. Tại giao diện **VPC**

   - Chọn **Yours VPC**
   - Chọn **Create VPC**

   ![Create VPC](/workshop1-FCJ2024/images/2.1-VPC/2.1.1-CreateVPC/0002-createvpc.png?featherlight=false&width=90pc)

3. Trong giao diện **Create VPC**

   - Tại mục **Resources to create**, chọn **VPC only**
   - Tại mục **Name tag - optional**, nhập **`lamp-stack-vpc`**
   - Tại mục **IPv4 CIDR block**, chọn **IPV4 CIDR manual input**
   - Tại mục **IPv4 CIDR**, nhập **`10.0.0.0/16`**

   ![Create VPC](/workshop1-FCJ2024/images/2.1-VPC/2.1.1-CreateVPC/0003-createvpc.png?featherlight=false&width=90pc)

   Tiếp tục,

   - Tại mục **IPv6 CIDR block**, chọn **No IPv6 CIDR block**
   - Tại mục **Tags**:
     - **Key** nhập **`Name`**
     - **Value - optional** nhập **`lamp-stack-vpc`**
   - Cuối cùng, chọn **Create VPC**

   ![Create VPC](/workshop1-FCJ2024/images/2.1-VPC/2.1.1-CreateVPC/0004-createvpc.png?featherlight=false&width=90pc)

4. Chúng ta đã tạo **VPC** thành công
   ![Create VPC](/workshop1-FCJ2024/images/2.1-VPC/2.1.1-CreateVPC/0005-createvpc.png?featherlight=false&width=90pc)
   ![Create VPC](/workshop1-FCJ2024/images/2.1-VPC/2.1.1-CreateVPC/0007-createvpc.png?featherlight=false&width=90pc)
