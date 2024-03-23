---
title: "Create and Configure Public Route Table"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.4.1 </b> "
---

#### Create and Configure Public Route Table

1. In the **VPC** interface:

   - Select **Route tables**
   - Click on **Create route table**

   ![Create Route Table](/images/2.4-RouteTable/2.4.1-PublicRT/0001-creatert.png?featherlight=false&width=90pc)

2. In the **Create route table** interface:

   - In the **Name - optional** field, enter **`lamp-stack-pub-rt`**
   - For **VPC**, select **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**
   - In the **Tags** section:
     - Enter **`Name`** for **Key**
     - Optionally, enter **`lamp-stack-pub-rt`** for **Value**
   - Finally, click on **Create route table**

   ![Create Route Table](/images/2.4-RouteTable/2.4.1-PublicRT/0002-creatert.png?featherlight=false&width=90pc)

3. Next, we will add the Internet Gateway to the newly created Public Route Table:

   - Click on the **Routes** tab
   - Select **Edit routes**

   ![Create Route Table](/images/2.4-RouteTable/2.4.1-PublicRT/0003-creatert.png?featherlight=false&width=90pc)

   - Under **Destination**, select **0.0.0.0/0**
   - Under **Target**, select **Internet Gateway**
   - Then choose **igw-oc134f10ab513a4cd**, which is the IGW we created earlier.
   - Finally, click **Save changes**

   ![Create Route Table](/images/2.4-RouteTable/2.4.1-PublicRT/0004-creatert.png?featherlight=false&width=90pc)

{{% notice note %}}
Note: Before selecting **0.0.0.0/0** under **Destination**, we need to click **Add route**.
{{% /notice %}}

- After adding the route to the Internet, the result will look like this:

![Create Route Table](/images/2.4-RouteTable/2.4.1-PublicRT/0005-creatert.png?featherlight=false&width=90pc)

4. Now we will associate the 2 Public Subnets we created earlier with this Route Table:

   - Click on **Subnet associations**
   - Select **Edit subnet associations**

   ![Create Route Table](/images/2.4-RouteTable/2.4.1-PublicRT/0006-creatert.png?featherlight=false&width=90pc)

   - Under **Available subnets**, select **pub-sub-2b** and **pub-sub-1a**
   - Finally, click **Save associations**

   ![Create Route Table](/images/2.4-RouteTable/2.4.1-PublicRT/0007-creatert.png?featherlight=false&width=90pc)

   - The result after association will look like this:

   ![Create Route Table](/images/2.4-RouteTable/2.4.1-PublicRT/0008-creatert.png?featherlight=false&width=90pc)
