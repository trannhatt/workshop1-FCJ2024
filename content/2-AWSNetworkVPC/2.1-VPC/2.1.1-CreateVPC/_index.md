---
title: "Create VPC"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.1.1 </b> "
---

#### Create VPC

1. In the **AWS console** interface:

   - Click on the search bar and type **`VPC`**
   - Under **Services**, select **VPC**

   ![Create VPC](/workshop1-FCJ2024/images/2.1-VPC/2.1.1-CreateVPC/0001-createvpc.png?featherlight=false&width=90pc)

2. In the **VPC** interface:

   - Choose **Your VPCs**
   - Click **Create VPC**

   ![Create VPC](/workshop1-FCJ2024/images/2.1-VPC/2.1.1-CreateVPC/0002-createvpc.png?featherlight=false&width=90pc)

3. In the **Create VPC** interface:

   - Under **Resources to create**, select **VPC only**
   - Under **Name tag - optional**, enter **`lamp-stack-vpc`**
   - Under **IPv4 CIDR block**, choose **IPV4 CIDR manual input**
   - Enter **`10.0.0.0/16`** under **IPv4 CIDR**

   ![Create VPC](/workshop1-FCJ2024/images/2.1-VPC/2.1.1-CreateVPC/0003-createvpc.png?featherlight=false&width=90pc)

   Continue,

   - Under **IPv6 CIDR block**, select **No IPv6 CIDR block**
   - Under **Tags**:
     - Enter **`Name`** for **Key**
     - Optionally, enter **`lamp-stack-vpc`** for **Value**
   - Finally, click **Create VPC**

   ![Create VPC](/workshop1-FCJ2024/images/2.1-VPC/2.1.1-CreateVPC/0004-createvpc.png?featherlight=false&width=90pc)

4. You have successfully created the **VPC**
   ![Create VPC](/workshop1-FCJ2024/images/2.1-VPC/2.1.1-CreateVPC/0005-createvpc.png?featherlight=false&width=90pc)
   ![Create VPC](/workshop1-FCJ2024/images/2.1-VPC/2.1.1-CreateVPC/0007-createvpc.png?featherlight=false&width=90pc)
