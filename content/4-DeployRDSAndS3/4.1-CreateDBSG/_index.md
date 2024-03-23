---
title: "Create DB Subnet Group"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1 </b> "
---

#### Creating DB Subnet Group

1. Navigate to the search bar.

   - Enter **`rds`**
   - Under **Services**, select **RDS**

   ![Create DB Subnet Group](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.1-CreateDBSG/0001-createdbsubnetgroup.png?featherlight=false&width=90pc)

2. In the **Amazon RDS** dashboard,

   - Choose **Subnet groups**
   - Select **Create DB subnet group**

   ![Create DB Subnet Group](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.1-CreateDBSG/0002-createdbsubnetgroup.png?featherlight=false&width=90pc)

3. In the **Create DB subnet group** interface,

   - In **Name**, enter **`book-rds-subnet-group`**
   - In **Description**, enter **`book-rds-subnet-group`**
   - For **VPC**, select **lamp-stack-vpc (vpc-Oacb9059f41ab5a37)**

   ![Create DB Subnet Group](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.1-CreateDBSG/0003-createdbsubnetgroup.png?featherlight=false&width=90pc)

   Next,

   - Under **Availability Zones**, select 2 AZs: **us-east-1a** and **us-east-1b**
   - Under **Subnets**, select 2 subnets: **subnet-07e1efe93fc1dfbdc (10.0.5.0/24)** and **subnet-Od218c71f1b18d748 (10.0.6.0/24)**

   ![Create DB Subnet Group](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.1-CreateDBSG/0004-createdbsubnetgroup.png?featherlight=false&width=90pc)

   Finally,

   - Double-check the selected subnets under **Subnets selected**.
   - Complete the creation of the subnet group by clicking **Create**

   ![Create DB Subnet Group](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.1-CreateDBSG/0005-createdbsubnetgroup.png?featherlight=false&width=90pc)

4. DB Subnet Group created successfully as shown:

   ![Create DB Subnet Group](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.1-CreateDBSG/0006-createdbsubnetgroup.png?featherlight=false&width=90pc)
