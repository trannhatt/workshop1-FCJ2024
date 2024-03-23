---
title: "Creating RDS Instance"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.2 </b> "
---

#### Creating RDS Instance

2. In the **Amazon RDS** dashboard,

   - Select **Databases**
   - Choose **Create database**

   ![Create RDS Instance](/images/4-DeployRDSAndS3/4.2-RDSIntance/0001-createrdsintance.png?featherlight=false&width=90pc)

3. In the **Create database** interface,

   - Under **Choose a database creation method**, select **Standard create**

   ![Create RDS Instance](/images/4-DeployRDSAndS3/4.2-RDSIntance/0002-createrdsintance.png?featherlight=false&width=90pc)

   - Under **Engine options**, select **MySQL**

   ![Create RDS Instance](/images/4-DeployRDSAndS3/4.2-RDSIntance/0003-createrdsintance.png?featherlight=false&width=90pc)

   - Under **Edition**, keep all fields as default

   ![Create RDS Instance](/images/4-DeployRDSAndS3/4.2-RDSIntance/0004-createrdsintance.png?featherlight=false&width=90pc)

   Next,

   - Under **Templates**, choose **Dev/Test**
   - Under **Availability and durability**, select **Multi-AZ DB instance**

   ![Create RDS Instance](/images/4-DeployRDSAndS3/4.2-RDSIntance/0005-createrdsintance.png?featherlight=false&width=90pc)

   In the **Settings** section,

   - For **DB instance identifier**, enter **`book-rds-database`**
   - For **Master username**, enter **`admin`**

   ![Create RDS Instance](/images/4-DeployRDSAndS3/4.2-RDSIntance/0006-createrdsintance.png?featherlight=false&width=90pc)

   - For **Master password**, enter your database password and confirm it in **Confirm master password**

   In the **Instance configuration** section,

   - Under **DB instance class**, select **Burstable classes (includes t classes)** and choose **db.t3.micro**

   ![Create RDS Instance](/images/4-DeployRDSAndS3/4.2-RDSIntance/0007-createrdsintance.png?featherlight=false&width=90pc)

   In the **Storage** section,

   - For **Allocated storage**, enter **`22`**
   - For **Storage autoscaling**, select **Enable storage autoscaling**

   ![Create RDS Instance](/images/4-DeployRDSAndS3/4.2-RDSIntance/0008-createrdsintance.png?featherlight=false&width=90pc)

   In the **Connectivity** section,

   - Under **Compute resource**, select **Don't connect to an EC2 compute resource**
   - Under **Network type**, select **IPv4**

   ![Create RDS Instance](/images/4-DeployRDSAndS3/4.2-RDSIntance/0009-createrdsintance.png?featherlight=false&width=90pc)

   - Under **Virtual private cloud (VPC)**, select **lamp-stack-vpc (vpc-Oacb9059f41ab5a37)**
   - Under **DB subnet group**, choose **book-rds-subnet-group**
   - Under **Public access**, select **No**

   ![Create RDS Instance](/images/4-DeployRDSAndS3/4.2-RDSIntance/0010-createrdsintance.png?featherlight=false&width=90pc)

   - Under **VPC security group (firewall)**, choose **Choose existing**
   - Under **Existing VPC security groups**, select **DatabaseSecurityGroup**
   - Under **Certificate authority**, choose **rds-ca-rsa2048-g1 (default)**

   ![Create RDS Instance](/images/4-DeployRDSAndS3/4.2-RDSIntance/0011-createrdsintance.png?featherlight=false&width=90pc)

   In the **Database authentication** section, leave it as **Password authentication**

   Under **Monitoring**, select **Enable Enhanced Monitoring**

   ![Create RDS Instance](/images/4-DeployRDSAndS3/4.2-RDSIntance/0012-createrdsintance.png?featherlight=false&width=90pc)

   Continuing, in the **Database options** section,

   - For **Initial database name**, enter **`e_bookstore`**
   - For **Backup**, select **Enable automated backups**

   ![Create RDS Instance](/images/4-DeployRDSAndS3/4.2-RDSIntance/0013-createrdsintance.png?featherlight=false&width=90pc)

   - Leave the rest of the fields with their default values

   ![Create RDS Instance](/images/4-DeployRDSAndS3/4.2-RDSIntance/0014-createrdsintance.png?featherlight=false&width=90pc)

   Finally, select **Create database**

   ![Create RDS Instance](/images/4-DeployRDSAndS3/4.2-RDSIntance/0015-createrdsintance.png?featherlight=false&width=90pc)

4. We have successfully created the database.

   ![Create RDS Instance](/images/4-DeployRDSAndS3/4.2-RDSIntance/0016-createrdsintance.png?featherlight=false&width=90pc)
