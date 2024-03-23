---
title: "Create and Configure Main Route Table"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.4.2 </b> "
---

#### Create and Configure Main Route Table

1. When we create a VPC, a default Route Table is created, and it is private. We will refer to it as the **Main Route Table**. In the **Route tables** interface:

   - Select **rtb-05a6febb5380e833f** as mentioned
   - Click on **Subnet associations**
   - Select **Edit subnet associations**

   ![Configure Main Route Table](/workshop1-FCJ2024/images/2.4-RouteTable/2.4.2-MainPrivateRT/0001-mainrt.png?featherlight=false&width=90pc)

   - Under **Available subnets**, select the private subnets including **pri-sub-3a**, **pri-sub-4b**, **pri-sub-5a**, and **pri-sub-6b**
   - Finally, click **Save associations**

   ![Configure Main Route Table](/workshop1-FCJ2024/images/2.4-RouteTable/2.4.2-MainPrivateRT/0002-mainrt.png?featherlight=false&width=90pc)

   - The result after association will look like this:

   ![Configure Main Route Table](/workshop1-FCJ2024/images/2.4-RouteTable/2.4.2-MainPrivateRT/0003-mainrt.png?featherlight=false&width=90pc)
