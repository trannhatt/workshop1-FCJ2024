---
title: "Tạo RDS Instance"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.2 </b> "
---

#### Tạo RDS Instance

2. Tại giao diện **Amazon RDS**

   - Chọn **Databases**
   - Chọn **Create database**

   ![Create RDS Instance](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.2-RDSIntance/0001-createrdsintance.png?featherlight=false&width=90pc)

3. Tại giao diện **Create database**

   - Tại mục **Choose a database creation method**, chọn **Standard create**

   ![Create RDS Instance](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.2-RDSIntance/0002-createrdsintance.png?featherlight=false&width=90pc)

   - Tại mục **Engine options**, chọn **MySQL**

   ![Create RDS Instance](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.2-RDSIntance/0003-createrdsintance.png?featherlight=false&width=90pc)

   - Trong phần **Edition**, để tất cả các trường thông tin là mặc định

   ![Create RDS Instance](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.2-RDSIntance/0004-createrdsintance.png?featherlight=false&width=90pc)

   Tiếp tục,

   - Tại mục **Templates**, chọn **Dev/Test**
   - Tại mục **Availability and durability**, chọn **Multi-AZ DB instance**

   ![Create RDS Instance](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.2-RDSIntance/0005-createrdsintance.png?featherlight=false&width=90pc)

   Trong phần **Settings**,

   - Tại mục **DB instance identifier**, nhập **`book-rds-database`**
   - Tại mục **Master username**, nhập **`admin`**

   ![Create RDS Instance](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.2-RDSIntance/0006-createrdsintance.png?featherlight=false&width=90pc)

   - Tại mục **Master password**, nhập password cho cơ sở dữ liệu của bạn và nhập lại trong **Confirm master password**

   Trong phần **Instance configuration**,

   - Tại mục **DB instance class**, chọn **Burstable classes (includes t classes)** và chọn **db.t3.micro**

   ![Create RDS Instance](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.2-RDSIntance/0007-createrdsintance.png?featherlight=false&width=90pc)

   Trong phần **Storage**,

   - Tại mục **Allocated storage**, nhập **`22`**
   - Tại mục **Storage autoscaling**, chọn **Enable storage autoscaling**

   ![Create RDS Instance](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.2-RDSIntance/0008-createrdsintance.png?featherlight=false&width=90pc)

   Trong phần **Connectivity**,

   - Tại mục **Compute resource**, chọn **Don't connect to an EC2 compute resource**
   - Tại mục **Network type**, chọn **IPv4**

   ![Create RDS Instance](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.2-RDSIntance/0009-createrdsintance.png?featherlight=false&width=90pc)

   Tiếp tục,

   - Tại mục **Virtual private cloud (VPC)**, chọn **lamp-stack-vpc (vpc-Oacb9059f41ab5a37)**
   - Tại mục **DB subnet group**, chọn **book-rds-subnet-group**
   - Tại mục **Public access**, chọn **No**

   ![Create RDS Instance](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.2-RDSIntance/0010-createrdsintance.png?featherlight=false&width=90pc)

   - Tại mục **VPC security group (firewall)**, chọn **Choose existing**
   - Tại mục **Existing VPC security groups**, chọn **DatabaseSecurityGroup**
   - Tại mục **Certificate authority**, chọn **rds-ca-rsa2048-g1 (default)**

   ![Create RDS Instance](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.2-RDSIntance/0011-createrdsintance.png?featherlight=false&width=90pc)

   Trong phần **Database authentication**, chúng ta vẫn để mặc định là **Password authentication**

   Trong phần **Monitoring**, chọn **Enable Enhanced Monitoring**

   ![Create RDS Instance](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.2-RDSIntance/0012-createrdsintance.png?featherlight=false&width=90pc)

   Tiếp tục, trong phần **Database options**,

   - Tại mục **Initial database name**, nhập **`e_bookstore`**
   - Tại mục **Backup**, chọn **Enable automated backups**

   ![Create RDS Instance](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.2-RDSIntance/0013-createrdsintance.png?featherlight=false&width=90pc)

   - Gửi nguyên các giá trị mặc định ở các mục còn lại

   ![Create RDS Instance](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.2-RDSIntance/0014-createrdsintance.png?featherlight=false&width=90pc)

   Cuối cùng, chọn **Create database**

   ![Create RDS Instance](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.2-RDSIntance/0015-createrdsintance.png?featherlight=false&width=90pc)

4. Chúng ta đã hoàn thành việc tạo cơ sở dữ liệu

   ![Create RDS Instance](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.2-RDSIntance/0016-createrdsintance.png?featherlight=false&width=90pc)
