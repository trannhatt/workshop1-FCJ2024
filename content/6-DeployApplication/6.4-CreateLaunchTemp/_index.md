---
title: "Create Launch Template"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 6.4 </b> "
---

#### Create Launch Template

1. In the **EC2** dashboard,

   - Select **Launch Templates**
   - Choose **Create launch template**

   ![Create Launch Template](/workshop1-FCJ2024/images/6-DeployApplication/6.4-CreateLaunchTemp/0001-createlt.png?featherlight=false&width=90pc)

2. In the **Launch template name and description** section,

   - In the **Launch template name - required** field, enter **`Bookstore-launch-template`**
   - In the **Template version description** field, enter **`Launch Template For ASG`**
   - Under **Auto Scaling guidance**, select **Provide guidance to help me set up a template that I can use with EC2 Auto Scaling**
   - In the **Template tags** section:
     - Enter **`Name`** in the **Key** field
     - Optionally, enter **`Bookstore-launch-template`** in the **Value** field

   ![Create Launch Template](/workshop1-FCJ2024/images/6-DeployApplication/6.4-CreateLaunchTemp/0002-createlt.png?featherlight=false&width=90pc)

3. In the **Application and OS Images (Amazon Machine Image) - required** section,

   - Under **My AMIs**, select **Owned by me**
   - Choose the recently created **Bookstore AMI** under **Amazon Machine Image (AMI)**.

   ![Create Launch Template](/workshop1-FCJ2024/images/6-DeployApplication/6.4-CreateLaunchTemp/0003-createlt.png?featherlight=false&width=90pc)

4. In the **Instance type** section,

   - Choose **t2.micro** under **Instance type**.

5. In the **Key pair (login)** section,

   - Optionally, you may skip selecting a key pair by choosing **Don't include in launch template**.

   ![Create Launch Template](/workshop1-FCJ2024/images/6-DeployApplication/6.4-CreateLaunchTemp/0004-createlt.png?featherlight=false&width=90pc)

6. In the **Network settings** section,

   - Under **Firewall (security groups)**, select **Select existing security group**
   - Choose **WebserverSecurityGroup** under **Common security groups**
   - Click **Create launch template**

   ![Create Launch Template](/workshop1-FCJ2024/images/6-DeployApplication/6.4-CreateLaunchTemp/0005-createlt.png?featherlight=false&width=90pc)

7. You have successfully created the Launch Template.

   ![Create Launch Template](/workshop1-FCJ2024/images/6-DeployApplication/6.4-CreateLaunchTemp/0006-createlt.png?featherlight=false&width=90pc)
