---
title: "Tạo 6 Subnets"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.3.1 </b> "
---

#### Tạo 6 Subnets

1. Tại giao diện **VPC**

   - Chọn **Subnets**
   - Chọn **Create subnet**

   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0001-createsubnet.png?featherlight=false&width=90pc)

2. Trong giao diện **Create subnet**

   - Tại **VPC ID**, chọn **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)** là VPC của bạn vừa tạo

   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0002-createsubnet.png?featherlight=false&width=90pc)

   Tiếp tục, tại **Subnet settings** chúng ta sẽ tạo liên tục 6 subnet như sau:

   - Tạo Public Subnet 1:
     - Tại mục **Subnet name**, nhập **`pub-sub-1a`**
     - Tại mục **Availability Zone**, chọn **US East (N. Virginia) / us-east-1a**
     - Tại mục **IP4 subnet CIDR block**, nhập **`10.0.1.0/24`**
     - Tại mục **Tags**:
       - **Key** nhập **`Name`**
       - **Value - optional** nhập **`pub-sub-1a`**

   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0003-createsubnet.png?featherlight=false&width=90pc)

   - Tạo Public Subnet 2:
     - Tại mục **Subnet name**, nhập **`pub-sub-2b`**
     - Tại mục **Availability Zone**, chọn **US East (N. Virginia) / us-east-1b**
     - Tại mục **IP4 subnet CIDR block**, nhập **`10.0.2.0/24`**
     - Tại mục **Tags**:
       - **Key** nhập **`Name`**
       - **Value - optional** nhập **`pub-sub-2b`**

   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0004-createsubnet.png?featherlight=false&width=90pc)

   - Tạo Private Subnet 3:
     - Tại mục **Subnet name**, nhập **`pri-sub-3a`**
     - Tại mục **Availability Zone**, chọn **US East (N. Virginia) / us-east-1a**
     - Tại mục **IP4 subnet CIDR block**, nhập **`10.0.3.0/24`**
     - Tại mục **Tags**:
       - **Key** nhập **`Name`**
       - **Value - optional** nhập **`pri-sub-3a`**

   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0005-createsubnet.png?featherlight=false&width=90pc)

   - Tạo Private Subnet 4:
     - Tại mục **Subnet name**, nhập **`pri-sub-4b`**
     - Tại mục **Availability Zone**, chọn **US East (N. Virginia) / us-east-1b**
     - Tại mục **IP4 subnet CIDR block**, nhập **`10.0.4.0/24`**
     - Tại mục **Tags**:
       - **Key** nhập **`Name`**
       - **Value - optional** nhập **`pri-sub-4b`**

   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0006-createsubnet.png?featherlight=false&width=90pc)

   - Tạo Private Subnet 5:
     - Tại mục **Subnet name**, nhập **`pri-sub-5a`**
     - Tại mục **Availability Zone**, chọn **US East (N. Virginia) / us-east-1a**
     - Tại mục **IP4 subnet CIDR block**, nhập **`10.0.5.0/24`**
     - Tại mục **Tags**:
       - **Key** nhập **`Name`**
       - **Value - optional** nhập **`pri-sub-5a`**

   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0007-createsubnet.png?featherlight=false&width=90pc)

   - Tạo Private Subnet 6:
     - Tại mục **Subnet name**, nhập **`pri-sub-6b`**
     - Tại mục **Availability Zone**, chọn **US East (N. Virginia) / us-east-1b**
     - Tại mục **IP4 subnet CIDR block**, nhập **`10.0.6.0/24`**
     - Tại mục **Tags**:
       - **Key** nhập **`Name`**
       - **Value - optional** nhập **`pri-sub-6b`**

   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0008-createsubnet.png?featherlight=false&width=90pc)

3. Các Subnet đã tạo thành công như sau:
   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0010-createsubnet.png?featherlight=false&width=90pc)
