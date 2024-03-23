---
title: "Create NAT Gateway"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.1 </b> "
---

#### Create the First NAT Gateway in the Public Subnet in AZ us-east-1a

1. In the **VPC** interface:

   - Select **NAT gateways**
   - Click on **Create NAT gateway**

   ![Create NAT gateway](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.1-CreateNATGW/0001-createnatgw.png?featherlight=false&width=90pc)

2. In the **Create NAT gateway** interface:

   - In the **Name - optional** field, enter **`lamp-stack-nat-pub-sub-1a`**
   - For **Subnet**, select **subnet-09781d02f50504e98 (pub-sub-1a)**
   - Check **Allocate Elastic IP**

   ![Create NAT gateway](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.1-CreateNATGW/0002-createnatgw.png?featherlight=false&width=90pc)

   Continuing,

   - In the **Tags** section:
     - Enter **`Name`** for **Key**
     - Optionally, enter **`lamp-stack-nat-pub-sub-1a`** for **Value**
   - Finally, click on **Create NAT gateway**

   ![Create NAT gateway](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.1-CreateNATGW/0003-createnatgw.png?featherlight=false&width=90pc)

   - This successfully creates the NAT Gateway.

   ![Create NAT gateway](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.1-CreateNATGW/0004-createnatgw.png?featherlight=false&width=90pc)

#### Create the Second NAT Gateway in the Public Subnet in AZ us-east-1b

3. Now, let's create a NAT Gateway in the other Availability Zone.

   In the **Create NAT gateway** interface:

   - Click on **Create NAT gateway**

   ![Create NAT gateway](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.1-CreateNATGW/0005-createnatgw.png?featherlight=false&width=90pc)

   Continuing in the **Create NAT gateway** interface:

   - In the **Name - optional** field, enter **`lamp-stack-nat-pub-sub-2b`**
   - For **Subnet**, select **subnet-03078b6edceb59c7e (pub-sub-2b)**
   - Check **Allocate Elastic IP**

   ![Create NAT gateway](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.1-CreateNATGW/0006-createnatgw.png?featherlight=false&width=90pc)

   Continuing,

   - In the **Tags** section:
     - Enter **`Name`** for **Key**
     - Optionally, enter **`lamp-stack-nat-pub-sub-2b`** for **Value**
   - Finally, click on **Create NAT gateway**

   ![Create NAT gateway](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.1-CreateNATGW/0007-createnatgw.png?featherlight=false&width=90pc)

4. Now, we have successfully created the second NAT Gateway. Both gateways are in **Available** state.

   ![Create NAT gateway](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.1-CreateNATGW/0008-createnatgw.png?featherlight=false&width=90pc)
