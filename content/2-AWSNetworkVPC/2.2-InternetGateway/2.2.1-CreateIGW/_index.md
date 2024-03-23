---
title: "Create Internet Gateway"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.2.1 </b> "
---

#### Create Internet Gateway

1. In the **VPC** interface:

   - Select **Internet gateways**
   - Click on **Create internet gateway**

   ![Create Internet Gateway](/workshop1-FCJ2024/images/2.2-InternetGateway/2.2.1-CreateIGW/0001-createigw.png?featherlight=false&width=90pc)

2. In the **Create internet gateway** interface:

   - In the **Name tag** field, enter **`lamp-stack-igw`**
   - In the **Tags** section:
     - Enter **`Name`** for **Key**
     - Optionally, enter **`lamp-stack-igw`** for **Value**
   - Finally, click on **Create internet gateway**

   ![Create Internet Gateway](/workshop1-FCJ2024/images/2.2-InternetGateway/2.2.1-CreateIGW/0002-createigw.png?featherlight=false&width=90pc)

3. We have successfully created the **Internet Gateway**, but it is currently in a **Detached** state as it has not been attached to any VPC yet.

   ![Create Internet Gateway](/workshop1-FCJ2024/images/2.2-InternetGateway/2.2.1-CreateIGW/0003-createigw.png?featherlight=false&width=90pc)
   ![Create Internet Gateway](/workshop1-FCJ2024/images/2.2-InternetGateway/2.2.1-CreateIGW/0004-createigw.png?featherlight=false&width=90pc)
