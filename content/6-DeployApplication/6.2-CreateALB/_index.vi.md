---
title: "Tạo Application Load Balancer"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 6.2 </b> "
---

#### Tạo Application Load Balancer

1. Tại giao diện **EC2**

   - Chọn **Load Balancers**
   - Chọn **Create load balancer**

   ![Create ALB](/workshop1-FCJ2024/images/6-DeployApplication/6.2-CreateALB/0001-createalb.png?featherlight=false&width=90pc)

2. Trong phần **Application Load Balancer**

   - Chọn **Create**

   ![Create ALB](/workshop1-FCJ2024/images/6-DeployApplication/6.2-CreateALB/0002-createalb.png?featherlight=false&width=90pc)

   Tiếp tục,

   - Tại mục **Load balancer name**, nhập **`lamp-stack-alb`**
   - Tại mục **Scheme** và **IP address type**, chúng ta sẽ để mặc định

   ![Create ALB](/workshop1-FCJ2024/images/6-DeployApplication/6.2-CreateALB/0003-createalb.png?featherlight=false&width=90pc)

3. Trong phần **Network mapping**

   - Tại mục **VPC**, chọn **lamp-stack-vpc**
   - Tại mục **Mappings**,
     - Chọn **us-east-1a (use1-az6)**. Subnet: **subnet-09781d02f50504e98**, là **pub-sub-1a**
     - Chọn **us-east-1b (use1-az1)**. Subnet: **subnet-03078b6edceb59c7e**, là **pub-sub-2b**

   ![Create ALB](/workshop1-FCJ2024/images/6-DeployApplication/6.2-CreateALB/0004-createalb.png?featherlight=false&width=90pc)

4. Trong phần **Security groups**

   - Tại mục **Security groups**, chọn **ALBSecurityGroup**

   ![Create ALB](/workshop1-FCJ2024/images/6-DeployApplication/6.2-CreateALB/0005-createalb.png?featherlight=false&width=90pc)

5. Trong phần **Listeners and routing**

   - Tại mục **Default action**, chọn **lamp-stack-tg**

   ![Create ALB](/workshop1-FCJ2024/images/6-DeployApplication/6.2-CreateALB/0006-createalb.png?featherlight=false&width=90pc)

   Tiếp tục,

   - Tại mục **Load balancer tags - optional**:
     - **Key** nhập **`Name`**
     - **Value - optional** nhập **`lamp-stack-alb`**

   ![Create ALB](/workshop1-FCJ2024/images/6-DeployApplication/6.2-CreateALB/0007-createalb.png?featherlight=false&width=90pc)

6. Cuối cùng, chọn **Create load balancer** để hoàn tất việt tạo Application Load Balancer

   ![Create ALB](/workshop1-FCJ2024/images/6-DeployApplication/6.2-CreateALB/0008-createalb.png?featherlight=false&width=90pc)

7. Như vậy chúng ta đã tạo Application Load Balancer thành công.

   ![Create ALB](/workshop1-FCJ2024/images/6-DeployApplication/6.2-CreateALB/0009-createalb.png?featherlight=false&width=90pc)

8. Chúng ta có thể copy **DNS name** ở ảnh trên để truy cập vào ứng dụng thông qua ALB

   ![Create ALB](/workshop1-FCJ2024/images/6-DeployApplication/6.2-CreateALB/0010-createalb.png?featherlight=false&width=90pc)

   ![Create ALB](/workshop1-FCJ2024/images/6-DeployApplication/6.2-CreateALB/0011-createalb.png?featherlight=false&width=90pc)
