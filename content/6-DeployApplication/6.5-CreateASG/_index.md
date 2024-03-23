---
title: "Create Autoscaling Group"
date: "2024-03-23"
weight: 5
chapter: false
pre: " <b> 6.5 </b> "
---

#### Create Autoscaling Group

1. In the **EC2** interface:

   - Select **Auto Scaling Groups**
   - Choose **Create Auto Scaling group**

   ![Create ASG](/workshop1-FCJ2024/images/6-DeployApplication/6.5-CreateASG/0001-createasg.png?featherlight=false&width=90pc)

2. In the **Choose launch template or configuration** section:

   - In the **Auto Scaling group name** field, enter **`bookstore-asg`**
   - Under **Launch template**, select **Bookstore-launch-template**, which was created in the previous step.

   ![Create ASG](/workshop1-FCJ2024/images/6-DeployApplication/6.5-CreateASG/0002-createasg.png?featherlight=false&width=90pc)

   - Click **Next** to proceed.

   ![Create ASG](/workshop1-FCJ2024/images/6-DeployApplication/6.5-CreateASG/0003-createasg.png?featherlight=false&width=90pc)

3. In the **Choose instance launch options** section:

   ![Create ASG](/workshop1-FCJ2024/images/6-DeployApplication/6.5-CreateASG/0004-createasg.png?featherlight=false&width=90pc)

   - Under **VPC**, select **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**
   - Under **Availability Zones and subnets**, select **us-east-1a | subnet-05c2f5e92fd59e436 (pri-sub-3а)** and **us-east-1b | subnet-08f6c0fba219ec914 (pri-sub- X4b)**

   ![Create ASG](/workshop1-FCJ2024/images/6-DeployApplication/6.5-CreateASG/0005-createasg.png?featherlight=false&width=90pc)

   - Click **Next** to proceed.

4. In the **Configure advanced options** section:

   - Under **Load balancing**, select **Attach to an existing load balancer**
   - Under **Attach to an existing load balancer**, choose **Choose from your load balancer target groups**
   - Under **Existing load balancer target groups**, select **lamp-stack-tg | HTTP**

   ![Create ASG](/workshop1-FCJ2024/images/6-DeployApplication/6.5-CreateASG/0006-createasg.png?featherlight=false&width=90pc)

   - Leave the remaining fields as default.

   ![Create ASG](/workshop1-FCJ2024/images/6-DeployApplication/6.5-CreateASG/0007-createasg.png?featherlight=false&width=90pc)

   - Under **Monitoring**, select **Enable group metrics collection within CloudWatch**
   - Click **Next** to proceed.

   ![Create ASG](/workshop1-FCJ2024/images/6-DeployApplication/6.5-CreateASG/0008-createasg.png?featherlight=false&width=90pc)

5. In the **Configure group size and scaling - optional** section:

   - In the **Desired capacity** field, enter **`2`**

   ![Create ASG](/workshop1-FCJ2024/images/6-DeployApplication/6.5-CreateASG/0009-createasg.png?featherlight=false&width=90pc)

   - In the **Min desired capacity** field, enter **`2`**
   - In the **Max desired capacity** field, enter **`4`**
   - Under **Automatic scaling - optional**, select **Target tracking scaling policy**

   ![Create ASG](/workshop1-FCJ2024/images/6-DeployApplication/6.5-CreateASG/0010-createasg.png?featherlight=false&width=90pc)

   - In the **Instance warmup** field, enter **`300`**

   ![Create ASG](/workshop1-FCJ2024/images/6-DeployApplication/6.5-CreateASG/0011-createasg.png?featherlight=false&width=90pc)

   - Click **Next** to proceed.

   ![Create ASG](/workshop1-FCJ2024/images/6-DeployApplication/6.5-CreateASG/0012-createasg.png?featherlight=false&width=90pc)

6. In the **Add notifications** section, we will add a notification for incidents regarding the Web application instances:

   - In the **Send a notification to** field, enter **`cloud-watch-alarm-bookstore-topic`**
   - In the **With these recipients** field, enter **`0521.20nn@gmail.com`**, your desired email address for notifications.
   - Under **Event types**, select all relevant event types.
   - Click **Next** to proceed.

   ![Create ASG](/workshop1-FCJ2024/images/6-DeployApplication/6.5-CreateASG/0013-createasg.png?featherlight=false&width=90pc)

7. In the **Add tags - optional** section:

   - Under **Tags**:
     - Enter **`Name`** for **Key**
     - Optionally, enter **`bookstore-asg`** for **Value**
   - Click **Next** to proceed.

   ![Create ASG](/workshop1-FCJ2024/images/6-DeployApplication/6.5-CreateASG/0014-createasg.png?featherlight=false&width=90pc)

8. In the **Review** section, review the provided information once more:

   - Click **Create Auto Scaling group** to complete the process.

   ![Create ASG](/workshop1-FCJ2024/images/6-DeployApplication/6.5-CreateASG/0015-createasg.png?featherlight=false&width=90pc)

9. Thus, we have successfully created the Autoscaling Group.

   ![Create ASG](/workshop1-FCJ2024/images/6-DeployApplication/6.5-CreateASG/0016-createasg.png?featherlight=false&width=90pc)

10. Accessing the **EC2 Instance** interface, we can see that 2 Web application servers are now active.

    ![Create ASG](/workshop1-FCJ2024/images/6-DeployApplication/6.5-CreateASG/0017-createasg.png?featherlight=false&width=90pc)
