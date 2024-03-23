---
title: "Tạo EC2 Setup Server trong Private Subnet"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 5.2 </b> "
---

#### Tạo EC2 Setup Server trong Private Subnet

1. Chúng ta nhấn chọn thanh tìm kiếm

   - Nhập **`ec2`**
   - Tại mục **Services** chọn **EC2**

   ![Create EC2 Setup Server](/images/5-SetupEc2ServerAndEFS/5.2-CreateEC2SetupServer/0001-createec2setupserver.png?featherlight=false&width=90pc)

2. Tại giao diện **EC2**

   - Chọn **Instances**
   - Sau đó chọn **Launch instances**

3. Trong giao diện **Launch an instance**

   - Tại mục **Name**, nhập **`lamp-stack-setup-server`**

   ![Create EC2 Setup Server](/images/5-SetupEc2ServerAndEFS/5.2-CreateEC2SetupServer/0002-createec2setupserver.png?featherlight=false&width=90pc)

   - Trong phần **Application and OS Images (Amazon Machine Image)**, chọn **AmazonLinux**

   ![Create EC2 Setup Server](/images/5-SetupEc2ServerAndEFS/5.2-CreateEC2SetupServer/0003-createec2setupserver.png?featherlight=false&width=90pc)

   Tiếp tục,

   - Tại mục **Instance type**, chọn **t2.micro**
   - Tại mục **Key pair (login)**, chọn **bastion-lamp-stack**

{{% notice note %}}
Lưu ý: Nếu bạn chưa có Key pair chọn **Create new key pair**
{{% /notice %}}

![Create EC2 Setup Server](/images/5-SetupEc2ServerAndEFS/5.1-CreateBastionHost/0005-createbastionhost.png?featherlight=false&width=90pc)

4. Trong phần **Network settings**

   - Tại mục **VPC - required**, chọn **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**
   - Tại mục **Subnet**, chọn **subnet-05c2f5e92fd59e436** là pri-sub-3a
   - Tại mục **Auto-assign public IP**, chọn **Disablee**
   - Tại mục **Firewall (security groups)**, chọn **Select existing security group** và chọn **WebserverSecurityGroup**, **DatabaseSecurityGroup** và **ALBSecurityGroup**

   ![Create EC2 Setup Server](/images/5-SetupEc2ServerAndEFS/5.2-CreateEC2SetupServer/0005-createec2setupserver.png?featherlight=false&width=90pc)

   ![Create EC2 Setup Server](/images/5-SetupEc2ServerAndEFS/5.2-CreateEC2SetupServer/0006-createec2setupserver.png?featherlight=false&width=90pc)

5. Trong phần **Configure storage**, vẫn giữ các giá trị mặc định

   - Cuối cùng chọn **Launch instance** đê hoàn tất việc tạo EC2 Setup Server

   ![Create EC2 Setup Server](/images/5-SetupEc2ServerAndEFS/5.2-CreateEC2SetupServer/0007-createec2setupserver.png?featherlight=false&width=90pc)

6. Trong phần **Instances** Chúng ta thấy EC2 Setup Server đã được tạo thành công

   ![Create EC2 Setup Server](/images/5-SetupEc2ServerAndEFS/5.2-CreateEC2SetupServer/0009-createec2setupserver.png?featherlight=false&width=90pc)
