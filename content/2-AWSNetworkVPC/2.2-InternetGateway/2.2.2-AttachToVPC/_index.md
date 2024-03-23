---
title: "Attach Internet Gateway to VPC"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.2.2 </b> "
---

#### Attach Internet Gateway to VPC

1. At the newly created IGW **lamp-stack-igw**

   - Click on the **Actions** dropdown menu and select **Attach to VPC**

   ![Attach to VPC](/images/2.2-InternetGateway/2.2.2-AttachToVPC/0001-attachtovpc.png?featherlight=false&width=90pc)

2. In the **Attach to VPC** interface

   - Under **Available VPCs**, select **vpc-Oacb9059f41ab5a37 - lamp-stack-vpc**
   - Click **Attach internet gateway**

   ![Attach to VPC](/images/2.2-InternetGateway/2.2.2-AttachToVPC/0002-attachtovpc.png?featherlight=false&width=90pc)

{{% notice note %}}
Note: **vpc-Oacb9059f41ab5a37** is your **VPC ID**.
{{% /notice %}}

3. We have successfully attached the **Internet Gateway** to the **VPC**. The **State** will now show **Attached**.

   ![Attach to VPC](/images/2.2-InternetGateway/2.2.2-AttachToVPC/0003-attachtovpc.png?featherlight=false&width=90pc)
   ![Attach to VPC](/images/2.2-InternetGateway/2.2.2-AttachToVPC/0004-attachtovpc.png?featherlight=false&width=90pc)
