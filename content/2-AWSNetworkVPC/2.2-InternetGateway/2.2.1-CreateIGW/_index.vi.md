---
title: "Tạo Internet Gateway"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.2.1 </b> "
---

#### Tạo Internet Gateway

1. Tại giao diện **VPC**

   - Chọn **Internet gateways**
   - Chọn **Create internet gateway**

   ![Create Internet Gateway](/workshop1-FCJ2024/images/2.2-InternetGateway/2.2.1-CreateIGW/0001-createigw.png?featherlight=false&width=90pc)

2. Trong giao diện **Create internet gateway**

   - Tại mục **Name tag**, nhập **`lamp-stack-igw`**
   - Tại mục **Tags**:
     - **Key** nhập **`Name`**
     - **Value - optional** nhập **`lamp-stack-igw`**
   - Cuối cùng, chọn **Create internet gateway**

   ![Create Internet Gateway](/workshop1-FCJ2024/images/2.2-InternetGateway/2.2.1-CreateIGW/0002-createigw.png?featherlight=false&width=90pc)

3. Chúng ta đã tạo **Internet Gateway** thành công nhưng hiện tại vẫn đang ở tình trạng **Detached** do chưa được gắn vào VPC nào.
   ![Create Internet Gateway](/workshop1-FCJ2024/images/2.2-InternetGateway/2.2.1-CreateIGW/0003-createigw.png?featherlight=false&width=90pc)
   ![Create Internet Gateway](/workshop1-FCJ2024/images/2.2-InternetGateway/2.2.1-CreateIGW/0004-createigw.png?featherlight=false&width=90pc)
