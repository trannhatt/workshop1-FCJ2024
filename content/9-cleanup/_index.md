---
title: "Cleanup Resources"
date: "2024-03-23"
weight: 9
chapter: false
pre: " <b> 9. </b> "
---

#### Clean up CloudFront

1. Access the **CloudFront** interface:

   - Select **Distributions**
   - Choose **E2H26TUZ72XRKT**
   - Select **Disable**

   ![Clean CloudFront](/images/9-Clean/0001-cleancloudfront.png?featherlight=false&width=90pc)

2. In the **Disable distribution** section:

   - Choose **Disable**

   ![Clean CloudFront](/images/9-Clean/0002-cleancloudfront.png?featherlight=false&width=90pc)

3. Once the **Status** is **Disabled**:

   - Select **E2H26TUZ72XRKT** again
   - Choose **Delete**

   ![Clean CloudFront](/images/9-Clean/0003-cleancloudfront.png?featherlight=false&width=90pc)

4. In the **Delete distribution** section:

   - Choose **Delete**

   ![Clean CloudFront](/images/9-Clean/0004-cleancloudfront.png?featherlight=false&width=90pc)

5. Cleanup of CloudFront is completed.

   ![Clean CloudFront](/images/9-Clean/0005-cleancloudfront.png?featherlight=false&width=90pc)

#### Clean up RDS Instance

6. Access the **Amazon RDS** interface:

   - Select **Databases**
   - Choose **book-rds-database**
   - From the **Actions** dropdown menu, select **Delete**

   ![Clean RDS](/images/9-Clean/0006-cleanrds.png?featherlight=false&width=90pc)

   - Uncheck **Create final snapshot** and **Retain automated backups**
   - Check **I acknowledge that upon instance deletion, automated backups, including system snapshots and point-in-time recovery, will no longer be available.**
   - In the **confirm deletion** field, enter **`delete me`**
   - Choose **Delete**

   ![Clean RDS](/images/9-Clean/0007-cleanrds.png?featherlight=false&width=90pc)

   - Wait for a while for the Database deletion to complete.

   ![Clean RDS](/images/9-Clean/0008-cleanrds.png?featherlight=false&width=90pc)

7. In the **Amazon RDS** interface:

   - Select **Subnet groups**
   - Choose **book-rds-subnet-group**
   - Select **Delete**

   ![Clean RDS](/images/9-Clean/0009-cleanrds.png?featherlight=false&width=90pc)

8. In the **Delete book-rds-subnet-group DB subnet group** section:

   - Choose **Delete**

   ![Clean RDS](/images/9-Clean/0010-cleanrds.png?featherlight=false&width=90pc)

   - Subnet groups cleanup is completed.

   ![Clean RDS](/images/9-Clean/0011-cleanrds.png?featherlight=false&width=90pc)

#### Clean up Auto Scaling Group

9. Access the **EC2** interface:

   - Select **Auto Scaling Groups**
   - Choose 2 Auto Scaling Groups **bastion-host-asg** and **bookstore-asg**
   - From the **Actions** dropdown menu, select **Delete**

   ![Clean ASG](/images/9-Clean/0012-cleanasg.png?featherlight=false&width=90pc)

10. In the **Delete 2 Auto Scaling groups** section:

    - In the **confirm deletion** field, enter **`delete 2`**
    - Choose **Delete**

    ![Clean ASG](/images/9-Clean/0013-cleanasg.png?featherlight=false&width=90pc)

    - Auto Scaling Group cleanup is completed.

    ![Clean ASG](/images/9-Clean/0014-cleanasg.png?featherlight=false&width=90pc)

#### Clean Application Load Balancer and Target Group

11. Access the **EC2** interface:

    - Select **Load Balancers**
    - Choose **lamp-stack-alb**
    - Click on the **Actions** dropdown menu and select **Delete load balancer**

    ![Clean ALB](/images/9-Clean/0016-cleanalb.png?featherlight=false&width=90pc)

12. In the **Delete load balancer** section:

    - In the **confirm** field, enter **`confirm`**
    - Click **Delete**

    ![Clean ALB](/images/9-Clean/0017-cleanalb.png?featherlight=false&width=90pc)

13. Next, also in the **EC2** interface:

    - Select **Target Groups**
    - Choose **lamp-stack-tg**
    - Click on the **Actions** dropdown menu and select **Delete**

    ![Clean ALB](/images/9-Clean/0018-cleanalb.png?featherlight=false&width=90pc)

14. In the **Delete target group?** section:

    - Click **Yes, delete**

    ![Clean ALB](/images/9-Clean/0019-cleanalb.png?featherlight=false&width=90pc)

#### Clean Launch Template and AMI

We'll clean up Launch Templates for the Bastion Host and the web application server.

15. Access the **EC2** interface:

    - Select **Launch Templates**
    - Choose **bastion-host-launch-template**
    - Click on the **Actions** dropdown menu and select **Delete template**

    ![Clean Launch Template & AMI](/images/9-Clean/0020-cleanltami.png?featherlight=false&width=90pc)

    Proceed,

    - Select **Launch Templates**
    - Choose **Bookstore-launch-template**
    - Click on the **Actions** dropdown menu and select **Delete template**

    ![Clean Launch Template & AMI](/images/9-Clean/0021-cleanltami.png?featherlight=false&width=90pc)

16. Next, still in the **EC2** interface:

    - Select **AMIs**
    - In the **Amazon Machine Images (AMIs)** section, select both **Bookstore AMI** and **Bastion Host AMI**
    - Click on the **Actions** dropdown menu and select **Deregister AMI**

    ![Clean Launch Template & AMI](/images/9-Clean/0023-cleanltami.png?featherlight=false&width=90pc)

17. In the **Deregister AMI** section:

    - Click **Deregister AMI**

    ![Clean Launch Template & AMI](/images/9-Clean/0024-cleanltami.png?featherlight=false&width=90pc)

#### Clean NAT Gateway

We'll clean up the two NAT Gateways.

18. Access the **VPC** interface:

    - Select **NAT gateways**
    - Choose **lamp-stack-nat-pub-sub-1a**
    - Click on the **Actions** dropdown menu and select **Delete NAT gateway**

    ![Clean NAT](/images/9-Clean/0025-cleannat.png?featherlight=false&width=90pc)

    In the **Delete NAT gateway** section:

    - In the **confirm deletion** field, enter **`delete`**
    - Click **Delete**

    ![Clean NAT](/images/9-Clean/0026-cleannat.png?featherlight=false&width=90pc)

    Next,

    - Choose **lamp-stack-nat-pub-sub-2b**
    - Click on the **Actions** dropdown menu and select **Delete NAT gateway**

    ![Clean NAT](/images/9-Clean/0027-cleannat.png?featherlight=false&width=90pc)

    In the **Delete NAT gateway** section:

    - In the **confirm deletion** field, enter **`delete`**
    - Click **Delete**

    ![Clean NAT](/images/9-Clean/0028-cleannat.png?featherlight=false&width=90pc)

#### Clean EFS File System

19. Access the **Elastic File System** interface:

    - Select the project's file system.
    - Choose **Network**
    - Select **Manage**

    ![Clean EFS](/images/9-Clean/0029-cleanvpc.png?featherlight=false&width=90pc)

    Next, in the **Mount targets** section:

    - Select **Remove** for both targets
    - Click **Save**

    ![Clean EFS](/images/9-Clean/0030-cleanvpc.png?featherlight=false&width=90pc)

20. Back in the **File systems** interface:

    - Select **bookstore-efs**
    - Choose **Delete**

    ![Clean EFS](/images/9-Clean/0031-cleanvpc.png?featherlight=false&width=90pc)

    In the **Delete file system** section:

    - Enter **`fs-061c0cc037d521abf`**, your File System ID
    - Click **Confirm**

    ![Clean EFS](/images/9-Clean/0032-cleanvpc.png?featherlight=false&width=90pc)

#### Clean VPC

21. Access the **VPC** interface:

    - Select **Your VPCs**
    - Choose **lamp-stack-vpc**
    - Click on the **Actions** dropdown menu and select **Delete VPC**

    ![Clean VPC](/images/9-Clean/0033-cleanvpc.png?featherlight=false&width=90pc)

22. In the **Delete VPC** section:

    - Enter **`delete`**
    - Click **Delete**

    ![Clean VPC](/images/9-Clean/0034-cleanvpc.png?featherlight=false&width=90pc)
