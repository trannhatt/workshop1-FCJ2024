---
title: "Tạo Bastion Host trong Public Subnet"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 5.1 </b> "
---

#### Tạo Bastion Host trong Public Subnet

1. Chúng ta nhấn chọn thanh tìm kiếm

   - Nhập **`ec2`**
   - Tại mục **Services** chọn **EC2**

   ![Create Bastion Host](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.1-CreateBastionHost/0001-createbastionhost.png?featherlight=false&width=90pc)

2. Tại giao diện **EC2**

   - Chọn **Instances**
   - Sau đó chọn **Launch instances**

   ![Create Bastion Host](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.1-CreateBastionHost/0002-createbastionhost.png?featherlight=false&width=90pc)

3. Trong giao diện **Launch an instance**

   - Tại mục **Name**, nhập **`Bastion Host`**

   ![Create Bastion Host](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.1-CreateBastionHost/0003-createbastionhost.png?featherlight=false&width=90pc)

   - Trong phần **Application and OS Images (Amazon Machine Image)**, chọn **AmazonLinux**

   ![Create Bastion Host](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.1-CreateBastionHost/0004-createbastionhost.png?featherlight=false&width=90pc)

   Tiếp tục,

   - Tại mục **Instance type**, chọn **t2.micro**
   - Tại mục **Key pair (login)**, chọn **bastion-lamp-stack**

{{% notice note %}}
Lưu ý: Nếu bạn chưa có Key pair chọn **Create new key pair**
{{% /notice %}}

![Create Bastion Host](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.1-CreateBastionHost/0005-createbastionhost.png?featherlight=false&width=90pc)

4. Trong phần **Network settings**

   - Tại mục **VPC - required**, chọn **vpc-Oacb9059f41ab5a37**
   - Tại mục **Subnet**, chọn **pub-sub-1a**
   - Tại mục **Auto-assign public IP**, chọn **Enable**
   - Tại mục **Firewall (security groups)**, chọn **Select existing security group** và chọn **SSHSecurityGroup**

5. Cuối cùng chọn **Launch instance** để hoàn tất việc tạo máy chủ Bastion Host

![Create Bastion Host](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.1-CreateBastionHost/0006-createbastionhost.png?featherlight=false&width=90pc)
