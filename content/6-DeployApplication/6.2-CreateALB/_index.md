---
title: "Create Application Load Balancer"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 6.2 </b> "
---

#### Create Application Load Balancer

1. In the **EC2** dashboard,

   - Select **Load Balancers**
   - Click on **Create load balancer**

   ![Create ALB](/images/6-DeployApplication/6.2-CreateALB/0001-createalb.png?featherlight=false&width=90pc)

2. In the **Application Load Balancer** section,

   - Click **Create**

   ![Create ALB](/images/6-DeployApplication/6.2-CreateALB/0002-createalb.png?featherlight=false&width=90pc)

   Next,

   - In the **Load balancer name** field, enter **`lamp-stack-alb`**
   - Leave the **Scheme** and **IP address type** to default

   ![Create ALB](/images/6-DeployApplication/6.2-CreateALB/0003-createalb.png?featherlight=false&width=90pc)

3. In the **Network mapping** section,

   - Under **VPC**, select **lamp-stack-vpc**
   - In **Mappings**,
     - Choose **us-east-1a (use1-az6)**. Subnet: **subnet-09781d02f50504e98**, named **pub-sub-1a**
     - Choose **us-east-1b (use1-az1)**. Subnet: **subnet-03078b6edceb59c7e**, named **pub-sub-2b**

   ![Create ALB](/images/6-DeployApplication/6.2-CreateALB/0004-createalb.png?featherlight=false&width=90pc)

4. In the **Security groups** section,

   - Select **ALBSecurityGroup** under **Security groups**

   ![Create ALB](/images/6-DeployApplication/6.2-CreateALB/0005-createalb.png?featherlight=false&width=90pc)

5. In the **Listeners and routing** section,

   - Under **Default action**, select **lamp-stack-tg**

   ![Create ALB](/images/6-DeployApplication/6.2-CreateALB/0006-createalb.png?featherlight=false&width=90pc)

   Next,

   - In **Load balancer tags - optional**:
     - Enter **`Name`** for **Key**
     - Optionally, enter **`lamp-stack-alb`** for **Value**

   ![Create ALB](/images/6-DeployApplication/6.2-CreateALB/0007-createalb.png?featherlight=false&width=90pc)

6. Finally, click **Create load balancer** to complete the creation of the Application Load Balancer.

   ![Create ALB](/images/6-DeployApplication/6.2-CreateALB/0008-createalb.png?featherlight=false&width=90pc)

7. You have successfully created the Application Load Balancer.

   ![Create ALB](/images/6-DeployApplication/6.2-CreateALB/0009-createalb.png?featherlight=false&width=90pc)

8. You can copy the **DNS name** from the image above to access the application via ALB.

   ![Create ALB](/images/6-DeployApplication/6.2-CreateALB/0010-createalb.png?featherlight=false&width=90pc)

   ![Create ALB](/images/6-DeployApplication/6.2-CreateALB/0011-createalb.png?featherlight=false&width=90pc)
