---
title: "Create Target Group"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 6.1 </b> "
---

#### Create Target Group

1. Click on the search bar

   - Type **`ec2`**
   - Under **Services**, select **EC2**

   ![Create Target Group](/images/6-DeployApplication/6.1-CreateTargetGroup/0001-createtg.png?featherlight=false&width=90pc)

2. In the **EC2** interface

   - Choose **Target Groups**
   - Click **Create target group**

   ![Create Target Group](/images/6-DeployApplication/6.1-CreateTargetGroup/0002-createtg.png?featherlight=false&width=90pc)

3. In the **Specify group details** section

   - Under **Choose a target type**, select **Instances**

   ![Create Target Group](/images/6-DeployApplication/6.1-CreateTargetGroup/0003-createtg.png?featherlight=false&width=90pc)

   Next,

   - For **Target group name**, enter **`lamp-stack-tg`**
   - For **VPC**, choose **lamp-stack-vpc**

   ![Create Target Group](/images/6-DeployApplication/6.1-CreateTargetGroup/0004-createtg.png?featherlight=false&width=90pc)

   - Leave the remaining fields at their default values

   ![Create Target Group](/images/6-DeployApplication/6.1-CreateTargetGroup/0005-createtg.png?featherlight=false&width=90pc)

   - For **Success codes**, enter **`200,301,302`**

   ![Create Target Group](/images/6-DeployApplication/6.1-CreateTargetGroup/0006-createtg.png?featherlight=false&width=90pc)

   - For **Tags**:
     - **Key**: **`Name`**
     - **Value - optional**: **`lamp-stack-tg`**
   - Click **Next**

   ![Create Target Group](/images/6-DeployApplication/6.1-CreateTargetGroup/0007-createtg.png?featherlight=false&width=90pc)

4. In the **Register targets** section

   - Under **Available instances**, select **lamp-stack-setup-server**
   - Click **Include as pending below**

   ![Create Target Group](/images/6-DeployApplication/6.1-CreateTargetGroup/0008-createtg.png?featherlight=false&width=90pc)

   - Review the **Review targets** section
   - Click **Create target group** to complete the creation of the target group

   ![Create Target Group](/images/6-DeployApplication/6.1-CreateTargetGroup/0009-createtg.png?featherlight=false&width=90pc)

5. Now, the Target Group has been successfully created.

   ![Create Target Group](/images/6-DeployApplication/6.1-CreateTargetGroup/0010-createtg.png?featherlight=false&width=90pc)
