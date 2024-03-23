---
title: "Create and Configure Private Route Table"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3.2 </b> "
---

#### Create and Configure Private Route Table

1. In the **VPC** interface:

   - Select **Route tables**
   - Click **Create route table**

   ![Create Private Route Table](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0001-createprirt.png?featherlight=false&width=90pc)

2. In the **Create route table** interface:

   - For **Name - optional**, enter **`lamp-stack-pri-rt-1`**
   - For **VPC**, select **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**
   - Under **Tags**:
     - For **Key**, enter **`Name`**
     - For **Value - optional**, enter **`lamp-stack-pri-rt-1`**
   - Finally, click **Create route table**

   ![Create Private Route Table](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0002-createprirt.png?featherlight=false&width=90pc)

3. Now, let's associate the 2 Private Subnets in AZ us-east-1a that we created earlier with this Private Route Table.

   - Click on **Subnet associations**
   - Select **Edit subnet associations**

   ![Create Private Route Table](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0003-createprirt.png?featherlight=false&width=90pc)

   - Under **Available subnets**, select **pri-sub-3a** and **pri-sub-5a**
   - Finally, click **Save associations**

   ![Create Private Route Table](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0004-createprirt.png?featherlight=false&width=90pc)

4. Next, let's add the NAT Gateway in AZ us-east-1a to this Private Route Table that we just created.

   - Click on **Routes**
   - Select **Edit routes**

   ![Create Private Route Table](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0005-createprirt.png?featherlight=false&width=90pc)

   - For **Destination**, select **0.0.0.0/0**
   - For **Target**, select **NAT Gateway**
   - Then select **nat-01aa9ae6861e6759a (lamp-stack-nat-pub-sub-1a)**, which is the NAT Gateway we created in the previous step.
   - Finally, click **Save changes**

   ![Create Private Route Table](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0006-createprirt.png?featherlight=false&width=90pc)

{{% notice note %}}
Note: Before selecting **0.0.0.0/0** under **Destination**, we need to click **Add route**.
{{% /notice %}}

5. Let's continue by creating the second Private Route Table. In the **Create route table** interface:

   - For **Name - optional**, enter **`lamp-stack-pri-rt-2`**
   - For **VPC**, select **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**
   - Under **Tags**:
     - For **Key**, enter **`Name`**
     - For **Value - optional**, enter **`lamp-stack-pri-rt-2`**
   - Finally, click **Create route table**

   ![Create Private Route Table](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0007-createprirt.png?featherlight=false&width=90pc)

6. Next, we will add the NAT Gateway in AZ us-east-1b to the second Private Route Table that we just created.

   - Click on **Routes**
   - Select **Edit routes**

   ![Create Private Route Table](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0008-createprirt.png?featherlight=false&width=90pc)

   - For **Destination**, select **0.0.0.0/0**
   - For **Target**, select **NAT Gateway**
   - Then select **nat-052de2c3601c08459 (lamp-stack-nat-pub-sub-2b)**, which is the second NAT Gateway we created in the previous step.
   - Finally, click **Save changes**

   ![Create Private Route Table](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0009-createprirt.png?featherlight=false&width=90pc)

7. Now, let's associate the 2 Private Subnets in AZ us-east-1b that we created earlier with this second Private Route Table.

   - Click on **Subnet associations**
   - Select **Edit subnet associations**

   ![Create Private Route Table](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0010-createprirt.png?featherlight=false&width=90pc)

   - Under **Available subnets**, select **pri-sub-4b** and **pri-sub-6b**
   - Finally, click **Save associations**

   ![Create Private Route Table](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0011-createprirt.png?featherlight=false&width=90pc)

8. The result after creating the two Private Route Tables is shown below:

   ![Create Private Route Table](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0012-createprirt.png?featherlight=false&width=90pc)
