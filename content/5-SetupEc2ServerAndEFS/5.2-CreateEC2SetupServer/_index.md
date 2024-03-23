---
title: "Create EC2 Setup Server in Private Subnet"
date: "2024-03-23"
weight: 2
chapter: false
pre: " <b> 5.2 </b> "
---

#### Create EC2 Setup Server in Private Subnet

1. Click on the search bar

   - Type **`ec2`**
   - Under **Services**, select **EC2**

   ![Create EC2 Setup Server](/images/5-SetupEc2ServerAndEFS/5.2-CreateEC2SetupServer/0001-createec2setupserver.png?featherlight=false&width=90pc)

2. In the **EC2 Dashboard**

   - Choose **Instances**
   - Then select **Launch instances**

3. In the **Launch an instance** wizard:

   - Under **Name**, enter **`lamp-stack-setup-server`**

   ![Create EC2 Setup Server](/images/5-SetupEc2ServerAndEFS/5.2-CreateEC2SetupServer/0002-createec2setupserver.png?featherlight=false&width=90pc)

   - Under **Application and OS Images (Amazon Machine Image)**, select **AmazonLinux**

   ![Create EC2 Setup Server](/images/5-SetupEc2ServerAndEFS/5.2-CreateEC2SetupServer/0003-createec2setupserver.png?featherlight=false&width=90pc)

   Then,

   - Under **Instance type**, choose **t2.micro**
   - Under **Key pair (login)**, select **bastion-lamp-stack**

{{% notice note %}}
Note: If you don't have a Key pair, select **Create new key pair**
{{% /notice %}}

![Create EC2 Setup Server](/images/5-SetupEc2ServerAndEFS/5.1-CreateBastionHost/0005-createbastionhost.png?featherlight=false&width=90pc)

4. In the **Network settings** section:

   - Under **VPC - required**, select **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**
   - Under **Subnet**, choose **subnet-05c2f5e92fd59e436 (pri-sub-3a)**
   - Under **Auto-assign public IP**, select **Disable**
   - Under **Firewall (security groups)**, select **Select existing security group** and choose **WebserverSecurityGroup**, **DatabaseSecurityGroup**, and **ALBSecurityGroup**

   ![Create EC2 Setup Server](/images/5-SetupEc2ServerAndEFS/5.2-CreateEC2SetupServer/0005-createec2setupserver.png?featherlight=false&width=90pc)

   ![Create EC2 Setup Server](/images/5-SetupEc2ServerAndEFS/5.2-CreateEC2SetupServer/0006-createec2setupserver.png?featherlight=false&width=90pc)

5. In the **Configure storage** section, keep the default values.

   - Finally, click **Launch instance** to complete the creation of the EC2 Setup Server.

   ![Create EC2 Setup Server](/images/5-SetupEc2ServerAndEFS/5.2-CreateEC2SetupServer/0007-createec2setupserver.png?featherlight=false&width=90pc)

6. In the **Instances** section, you can see that the EC2 Setup Server has been successfully created.

   ![Create EC2 Setup Server](/images/5-SetupEc2ServerAndEFS/5.2-CreateEC2SetupServer/0009-createec2setupserver.png?featherlight=false&width=90pc)
