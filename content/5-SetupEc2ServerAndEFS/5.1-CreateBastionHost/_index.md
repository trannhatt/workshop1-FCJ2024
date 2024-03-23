---
title: "Create Bastion Host in Public Subnet"
date: "2024-03-23"
weight: 1
chapter: false
pre: " <b> 5.1 </b> "
---

#### Create Bastion Host in Public Subnet

1. Click on the search bar

   - Type **`ec2`**
   - Under **Services**, select **EC2**

   ![Create Bastion Host](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.1-CreateBastionHost/0001-createbastionhost.png?featherlight=false&width=90pc)

2. In the **EC2 Dashboard**

   - Choose **Instances**
   - Then select **Launch instances**

   ![Create Bastion Host](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.1-CreateBastionHost/0002-createbastionhost.png?featherlight=false&width=90pc)

3. In the **Launch an instance** wizard:

   - Under **Name**, enter **`Bastion Host`**

   ![Create Bastion Host](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.1-CreateBastionHost/0003-createbastionhost.png?featherlight=false&width=90pc)

   - Under **Application and OS Images (Amazon Machine Image)**, select **AmazonLinux**

   ![Create Bastion Host](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.1-CreateBastionHost/0004-createbastionhost.png?featherlight=false&width=90pc)

   Then,

   - Under **Instance type**, choose **t2.micro**
   - Under **Key pair (login)**, select **bastion-lamp-stack**

{{% notice note %}}
Note: If you don't have a Key pair, select **Create new key pair**
{{% /notice %}}

![Create Bastion Host](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.1-CreateBastionHost/0005-createbastionhost.png?featherlight=false&width=90pc)

4. In the **Network settings** section:

   - Under **VPC - required**, select **vpc-Oacb9059f41ab5a37**
   - Under **Subnet**, choose **pub-sub-1a**
   - Under **Auto-assign public IP**, select **Enable**
   - Under **Firewall (security groups)**, select **Select existing security group** and choose **SSHSecurityGroup**

5. Finally, click **Launch instance** to complete the creation of the Bastion Host.

   ![Create Bastion Host](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.1-CreateBastionHost/0006-createbastionhost.png?featherlight=false&width=90pc)
