---
title: "Tạo Security Groups"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 3.3 </b> "
---

#### Tạo Security Group cho Application Load Balancer

1. Chúng ta nhấn chọn thanh tìm kiếm

   - Nhập **`ec2`**
   - Tại mục **Services** chọn **EC2**

   ![Create Security Groups](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0001-createsg.png?featherlight=false&width=90pc)

2. Trong giao diện **EC2**

   - Chọn **Security Group**
   - Chọn **Create security group**

   ![Create Security Groups](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0002-createsg.png?featherlight=false&width=90pc)

3. Thực hiện cấu hình **Security group** đầu tiên cho Application Load Balancer

   - Tại **Security Group name**, nhập **`ALBSecurityGroup`**
   - Tại **Description**, nhập **`This is the security group that we will add to the application load balancer`**
   - Tại **VPC**, chọn **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**

   ![Create Security Groups](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0003-createsg.png?featherlight=false&width=90pc)

4. Tiếp theo, chúng ta sẽ thực hiện cấu hình **Inbound rules**

   - Chọn **Type**: **HTTP** và **Source**: **Anywhere-IPv4 (0.0.0.0/0)**
   - Chọn **Add rule** để thêm 1 rule mới
   - Chọn **Type**: **HTTPS** và **Source**: **Anywhere-IPv4 (0.0.0.0/0)**

   ![Create Security Groups](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0004-createsg.png?featherlight=false&width=90pc)

5. Kiểm tra **Outbound rules** và chọn **Create security group**

   ![Create Security Groups](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0005-createsg.png?featherlight=false&width=90pc)

#### Tạo Security Groups cho máy chủ Bastion Host nằm trong Public Subnet

6. Thực hiện cấu hình **Security group** thứ 2 cho máy chủ Bastion Host

   - Tại **Security Group name**, nhập **`SSHSecurityGroup`**
   - Tại **Description**, nhập **`This is the security group that I will use to Bastion to ssh into my EC2 instance in the private subnet`**
   - Tại **VPC**, chọn **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**

   ![Create Security Groups](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0006-createsg.png?featherlight=false&width=90pc)

7. Tiếp theo, chúng ta sẽ thực hiện cấu hình **Inbound rules**

   - Chọn **Type**: **SSH** và **Source**: **Custom (0.0.0.0/0)**
   - Kiểm tra **Outbound rules** và chọn **Create security group**

   ![Create Security Groups](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0010-createsg.png?featherlight=false&width=90pc)

#### Tạo Security Group cho máy chủ nằm trong Private subnet

8. Thực hiện cấu hình **Security group** thứ 3 cho máy chủ ứng dụng Web

   - Tại **Security Group name**, nhập **`WebserverSecurityGroup`**
   - Tại **Description**, nhập **`This is the security group that we will add to the web servers in the private app subnets`**
   - Tại **VPC**, chọn **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**

   ![Create Security Groups](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0008-createsg.png?featherlight=false&width=90pc)

9. Tiếp theo, chúng ta sẽ thực hiện cấu hình **Inbound rules**

   - Chọn **Type**: **SSH** và **Source**: **Custom (sg-0e83ad52ce033e305)**. **sg-0e83ad52ce033e305** là ID của SSH Security Group.
   - Chọn **Type**: **HTTP** và **Source**: **Custom (sg-027df2808d1cc8947)**. **sg-027df2808d1cc8947** là ID của ALB Security Group.
   - Chọn **Type**: **HTTPS** và **Source**: **Custom (sg-027f2808d1cc8947)**. **sg-027df2808d1cc8947** là ID của ALB Security Group.

   ![Create Security Groups](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0009-createsg.png?featherlight=false&width=90pc)

10. Kiểm tra **Outbound rules** và chọn **Create security group**
    ![Create Security Groups](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0010-createsg.png?featherlight=false&width=90pc)

#### Tạo Security Groups cho RDS Instance

11. Thực hiện cấu hình **Security group** thứ 4 cho RDS Instance chứa cơ sở dữ liệu

    - Tại **Security Group name**, nhập **`DatabaseSecurityGroup`**
    - Tại **Description**, nhập **`This is the security group that I will add to the RDS instance in the private data subnet`**
    - Tại **VPC**, chọn **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**

    ![Create Security Groups](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0011-createsg.png?featherlight=false&width=90pc)

12. Tiếp theo, chúng ta sẽ thực hiện cấu hình **Inbound rules**

    - Chọn **Type**: **MYSQL/Aurora** và **Source**: **Custom (sg-050c7d7dfdd96977c)**. **sg-050c7d7dfdd96977c** là ID của Web Server Security Group.

    ![Create Security Groups](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0012-createsg.png?featherlight=false&width=90pc)

13. Kiểm tra **Outbound rules** và chọn **Create security group**
    ![Create Security Groups](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0013-createsg.png?featherlight=false&width=90pc)

#### Tạo Security Groups cho phép NFS truy cập xử lý máy chủ Web trong private subnet

14. Thực hiện cấu hình **Security group** thứ 5 cho phép NFS truy cập xử lý máy chủ Web

    - Tại **Security Group name**, nhập **`EFSSecurityGroup`**
    - Tại **Description**, nhập **`Allow NFS access Private App Instances`**
    - Tại **VPC**, chọn **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**

    ![Create Security Groups](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0016-createsg.png?featherlight=false&width=90pc)

15. Tiếp theo, chúng ta sẽ thực hiện cấu hình **Inbound rules**

    - Chọn **Type**: **NFS** và **Source**: **Custom (sg-050c7d7dfdd96977c)**. **sg-050c7d7dfdd96977c** là ID của Web Server Security Group.

    ![Create Security Groups](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0017-createsg.png?featherlight=false&width=90pc)

16. Kiểm tra **Outbound rules** và chọn **Create security group**
    ![Create Security Groups](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.3-CreateSecurityGroup/0018-createsg.png?featherlight=false&width=90pc)
