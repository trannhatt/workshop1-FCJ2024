---
title: "Create Security Groups"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 3.3 </b> "
---

#### Create Security Groups for Application Load Balancer

1. Click on the search bar

   - Type **`ec2`**
   - Under **Services**, select **EC2**

   ![Create Security Groups](/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0001-createsg.png?featherlight=false&width=90pc)

2. In the **EC2** dashboard,

   - Select **Security Groups**
   - Click **Create security group**

   ![Create Security Groups](/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0002-createsg.png?featherlight=false&width=90pc)

3. Configure the first **Security Group** for the Application Load Balancer (ALB)

   - Enter **Security Group name**: **`ALBSecurityGroup`**
   - Enter **Description**: **`This is the security group that we will add to the application load balancer`**
   - Select the appropriate **VPC**: **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**

   ![Create Security Groups](/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0003-createsg.png?featherlight=false&width=90pc)

4. Configure **Inbound rules**

   - Select **Type**: **HTTP** and **Source**: **Anywhere-IPv4 (0.0.0.0/0)**
   - Click **Add rule** to add another rule
   - Select **Type**: **HTTPS** and **Source**: **Anywhere-IPv4 (0.0.0.0/0)**

   ![Create Security Groups](/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0004-createsg.png?featherlight=false&width=90pc)

5. Review **Outbound rules** and click **Create security group**

   ![Create Security Groups](/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0005-createsg.png?featherlight=false&width=90pc)

#### Creating Security Groups for Bastion Host in the Public Subnet

6. Configure the second **Security Group** for the Bastion Host

   - Enter **Security Group name**: **`SSHSecurityGroup`**
   - Enter **Description**: **`This is the security group that I will use to Bastion to ssh into my EC2 instance in the private subnet`**
   - Select the appropriate **VPC**: **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**

   ![Create Security Groups](/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0006-createsg.png?featherlight=false&width=90pc)

7. Configure **Inbound rules**

   - Select **Type**: **SSH** and **Source**: **Custom (0.0.0.0/0)**
   - Review **Outbound rules** and click **Create security group**

   ![Create Security Groups](/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0010-createsg.png?featherlight=false&width=90pc)

#### Creating Security Group for Servers in the Private Subnet

8. Configure the third **Security Group** for the Web servers

   - Enter **Security Group name**: **`WebserverSecurityGroup`**
   - Enter **Description**: **`This is the security group that we will add to the web servers in the private app subnets`**
   - Select the appropriate **VPC**: **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**

   ![Create Security Groups](/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0008-createsg.png?featherlight=false&width=90pc)

9. Configure **Inbound rules**

   - Select **Type**: **SSH** and **Source**: **Custom (sg-0e83ad52ce033e305)**. **sg-0e83ad52ce033e305** is the ID of SSH Security Group.
   - Select **Type**: **HTTP** and **Source**: **Custom (sg-027df2808d1cc8947)**. **sg-027df2808d1cc8947** is the ID of ALB Security Group.
   - Select **Type**: **HTTPS** and **Source**: **Custom (sg-027f2808d1cc8947)**. **sg-027df2808d1cc8947** is the ID of ALB Security Group.

   ![Create Security Groups](/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0009-createsg.png?featherlight=false&width=90pc)

10. Check **Outbound rules** and select **Create security group**
    ![Create Security Groups](/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0010-createsg.png?featherlight=false&width=90pc)

#### Creating Security Groups for RDS Instance

11. Configure the **Security group** for the RDS Instance containing the database.

    - In **Security Group name**, enter **`DatabaseSecurityGroup`**
    - In **Description**, enter **`This is the security group that I will add to the RDS instance in the private data subnet`**
    - For **VPC**, select **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**

    ![Create Security Groups](/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0011-createsg.png?featherlight=false&width=90pc)

12. Next, configure **Inbound rules**.

    - Select **Type**: **MYSQL/Aurora** and **Source**: **Custom (sg-050c7d7dfdd96977c)**. **sg-050c7d7dfdd96977c** is the ID of the Web Server Security Group.

    ![Create Security Groups](/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0012-createsg.png?featherlight=false&width=90pc)

13. Check **Outbound rules** and select **Create security group**
    ![Create Security Groups](/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0013-createsg.png?featherlight=false&width=90pc)

#### Creating Security Groups to Allow NFS Access to Web Server Processing in the Private Subnet

14. Configure the **Security group** to allow NFS access to web server processing.

    - In **Security Group name**, enter **`EFSSecurityGroup`**
    - In **Description**, enter **`Allow NFS access Private App Instances`**
    - For **VPC**, select **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**

    ![Create Security Groups](/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0016-createsg.png?featherlight=false&width=90pc)

15. Next, configure **Inbound rules**.

    - Select **Type**: **NFS** and **Source**: **Custom (sg-050c7d7dfdd96977c)**. **sg-050c7d7dfdd96977c** is the ID of the Web Server Security Group.

    ![Create Security Groups](/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0017-createsg.png?featherlight=false&width=90pc)

16. Check **Outbound rules** and select **Create security group**
    ![Create Security Groups](/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0018-createsg.png?featherlight=false&width=90pc)
