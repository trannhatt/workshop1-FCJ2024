---
title: "Tạo Target Group"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 6.1 </b> "
---

#### Tạo Target Group

1. Nhấn chọn thanh tìm kiếm

   - Nhập **`ec2`**
   - Tại mục **Services** chọn **EC2**

   ![Create Target Group](/workshop1-FCJ2024/images/6-DeployApplication/6.1-CreateTargetGroup/0001-createtg.png?featherlight=false&width=90pc)

2. Tại giao diện **EC2**

   - Chọn **Target Groups**
   - Chọn **Create target group**

   ![Create Target Group](/workshop1-FCJ2024/images/6-DeployApplication/6.1-CreateTargetGroup/0002-createtg.png?featherlight=false&width=90pc)

3. Trong phần **Specify group details**

   - Tại mục **Choose a target type**, chọn **Instances**

   ![Create Target Group](/workshop1-FCJ2024/images/6-DeployApplication/6.1-CreateTargetGroup/0003-createtg.png?featherlight=false&width=90pc)

   Tiếp tục,

   - Tại mục **Target group name**, nhập **`lamp-stack-tg`**
   - Tại mục **VPC**, chọn **lamp-stack-vpc**

   ![Create Target Group](/workshop1-FCJ2024/images/6-DeployApplication/6.1-CreateTargetGroup/0004-createtg.png?featherlight=false&width=90pc)

   - Các trường thông tin tiếp theo để mặc định

   ![Create Target Group](/workshop1-FCJ2024/images/6-DeployApplication/6.1-CreateTargetGroup/0005-createtg.png?featherlight=false&width=90pc)

   - Tại mục **Success codes**, nhập **`200,301,302`**

   ![Create Target Group](/workshop1-FCJ2024/images/6-DeployApplication/6.1-CreateTargetGroup/0006-createtg.png?featherlight=false&width=90pc)

   - Tại mục **Tags**:
     - **Key** nhập **`Name`**
     - **Value - optional** nhập **`lamp-stack-tg`**
   - Chọn **Next**

   ![Create Target Group](/workshop1-FCJ2024/images/6-DeployApplication/6.1-CreateTargetGroup/0007-createtg.png?featherlight=false&width=90pc)

4. Trong phần **Register targets**

   - Tại mục **Available instances**, chọn **lamp-stack-setup-server**
   - Chọn **Include as pending below**

   ![Create Target Group](/workshop1-FCJ2024/images/6-DeployApplication/6.1-CreateTargetGroup/0008-createtg.png?featherlight=false&width=90pc)

   - Kiểm tra lại trong phần **Review targets**
   - Chọn **Create target group** để hoàn thành việc tạo Target group.

   ![Create Target Group](/workshop1-FCJ2024/images/6-DeployApplication/6.1-CreateTargetGroup/0009-createtg.png?featherlight=false&width=90pc)

5. Như vậy chúng ta đã tạo Target Group thành công.

   ![Create Target Group](/workshop1-FCJ2024/images/6-DeployApplication/6.1-CreateTargetGroup/0010-createtg.png?featherlight=false&width=90pc)
