---
title: "Create 6 Subnets"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.3.1 </b> "
---

#### Create 6 Subnets

1. In the **VPC** interface:

   - Select **Subnets**
   - Click on **Create subnet**

   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0001-createsubnet.png?featherlight=false&width=90pc)

2. In the **Create subnet** interface:

   - Under **VPC ID**, select **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**, which is your recently created VPC

   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0002-createsubnet.png?featherlight=false&width=90pc)

   Then, under **Subnet settings**, we will create 6 subnets as follows:

   - Create Public Subnet 1:
     - In the **Subnet name** field, enter **`pub-sub-1a`**
     - For **Availability Zone**, select **US East (N. Virginia) / us-east-1a**
     - For **IPv4 subnet CIDR block**, enter **`10.0.1.0/24`**
     - Under **Tags**:
       - Enter **`Name`** for **Key**
       - Optionally, enter **`pub-sub-1a`** for **Value**

   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0003-createsubnet.png?featherlight=false&width=90pc)

   - Create Public Subnet 2:
     - In the **Subnet name** field, enter **`pub-sub-2b`**
     - For **Availability Zone**, select **US East (N. Virginia) / us-east-1b**
     - For **IPv4 subnet CIDR block**, enter **`10.0.2.0/24`**
     - Under **Tags**:
       - Enter **`Name`** for **Key**
       - Optionally, enter **`pub-sub-2b`** for **Value**

   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0004-createsubnet.png?featherlight=false&width=90pc)

   - Create Private Subnet 3:
     - In the **Subnet name** field, enter **`pri-sub-3a`**
     - For **Availability Zone**, select **US East (N. Virginia) / us-east-1a**
     - For **IPv4 subnet CIDR block**, enter **`10.0.3.0/24`**
     - Under **Tags**:
       - Enter **`Name`** for **Key**
       - Optionally, enter **`pri-sub-3a`** for **Value**

   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0005-createsubnet.png?featherlight=false&width=90pc)

   - Create Private Subnet 4:
     - In the **Subnet name** field, enter **`pri-sub-4b`**
     - For **Availability Zone**, select **US East (N. Virginia) / us-east-1b**
     - For **IPv4 subnet CIDR block**, enter **`10.0.4.0/24`**
     - Under **Tags**:
       - Enter **`Name`** for **Key**
       - Optionally, enter **`pri-sub-4b`** for **Value**

   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0006-createsubnet.png?featherlight=false&width=90pc)

   - Create Private Subnet 5:
     - In the **Subnet name** field, enter **`pri-sub-5a`**
     - For **Availability Zone**, select **US East (N. Virginia) / us-east-1a**
     - For **IPv4 subnet CIDR block**, enter **`10.0.5.0/24`**
     - Under **Tags**:
       - Enter **`Name`** for **Key**
       - Optionally, enter **`pri-sub-5a`** for **Value**

   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0007-createsubnet.png?featherlight=false&width=90pc)

   - Create Private Subnet 6:
     - In the **Subnet name** field, enter **`pri-sub-6b`**
     - For **Availability Zone**, select **US East (N. Virginia) / us-east-1b**
     - For **IPv4 subnet CIDR block**, enter **`10.0.6.0/24`**
     - Under **Tags**:
       - Enter **`Name`** for **Key**
       - Optionally, enter **`pri-sub-6b`** for **Value**

   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0008-createsubnet.png?featherlight=false&width=90pc)

3. The subnets have been successfully created as follows:

   ![Create Subnet](/workshop1-FCJ2024/images/2.3-Subnet/2.3.1-CreateSubnet/0010-createsubnet.png?featherlight=false&width=90pc)
