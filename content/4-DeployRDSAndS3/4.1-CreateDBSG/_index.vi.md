---
title: "Tạo DB Subnet Group"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1 </b> "
---

#### Tạo DB Subnet Group

1. Chúng ta nhấn chọn thanh tìm kiếm

   - Nhập **`rds`**
   - Tại mục **Services** chọn **RDS**

   ![Create DB Subnet Group](/images/4-DeployRDSAndS3/4.1-CreateDBSG/0001-createdbsubnetgroup.png?featherlight=false&width=90pc)

2. Tại giao diện **Amazon RDS**

   - Chọn **Subnet groups**
   - Chọn **Create DB subnet group**

   ![Create DB Subnet Group](/images/4-DeployRDSAndS3/4.1-CreateDBSG/0002-createdbsubnetgroup.png?featherlight=false&width=90pc)

3. Tại giao diện **Create DB subnet group**

   - Tại mục **Name**, nhập **`book-rds-subnet-group`**
   - Tại mục **Description**, nhập **`book-rds-subnet-group`**
   - Tại mục **VPC**, chọn **lamp-stack-vpc (vpc-Oacb9059f41ab5a37)**

   ![Create DB Subnet Group](/images/4-DeployRDSAndS3/4.1-CreateDBSG/0003-createdbsubnetgroup.png?featherlight=false&width=90pc)

   Tiếp tục,

   - Tại mục **Availability Zones**, chọn 2 AZ là **us-east-1a** và **us-east-1b**
   - Tại mục **Subnets**, chọn 2 subnet là **subnet-07e1efe93fc1dfbdc (10.0.5.0/24)** và **subnet-Od218c71f1b18d748 (10.0.6.0/24)**

   ![Create DB Subnet Group](/images/4-DeployRDSAndS3/4.1-CreateDBSG/0004-createdbsubnetgroup.png?featherlight=false&width=90pc)

   Cuối cùng,

   - Kiểm tra trong **Subnets selected** lần nửa xem các trường thông tin được chọn đã đúng chưa.
   - Hoàn thành việc tạo Subnet Group bằng cách nhấn **Create**

   ![Create DB Subnet Group](/images/4-DeployRDSAndS3/4.1-CreateDBSG/0005-createdbsubnetgroup.png?featherlight=false&width=90pc)

4. Tạo DB Subnet Sroup thành công như ảnh:

   ![Create DB Subnet Group](/images/4-DeployRDSAndS3/4.1-CreateDBSG/0006-createdbsubnetgroup.png?featherlight=false&width=90pc)
