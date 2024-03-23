---
title: "Tạo Launch Template"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 6.4 </b> "
---

#### Tạo Launch Template

1. Tại giao diện **EC2**

   - Chọn **Launch Templates**
   - Chọn **Create launch template**

   ![Create Launch Template](/images/6-DeployApplication/6.4-CreateLaunchTemp/0001-createlt.png?featherlight=false&width=90pc)

2. Trong phần **Launch template name and description**

   - Tại mục **Launch template name - required**, nhập **`Bookstore-launch-template`**
   - Tại mục **Template version description**, nhập **`Launch Template For ASG`**
   - Tại mục **Auto Scaling guidance**, chọn **Provide guidance to help me set up a template that I can use with EC2 Auto Scaling**
   - Tại mục **Template tags**:
     - **Key** nhập **`Name`**
     - **Value - optional** nhập **`Bookstore-launch-template`**

   ![Create Launch Template](/images/6-DeployApplication/6.4-CreateLaunchTemp/0002-createlt.png?featherlight=false&width=90pc)

3. Trong phần **Application and OS Images (Amazon Machine Image) - required**

   - Tại mục **My AMIs**, chọn **Owned by me**
   - Tại mục **Amazon Machine Image (AMI)**, chọn **Bookstore AMI** là AMI chúng ta mới vừa tạo ở bước trước.

   ![Create Launch Template](/images/6-DeployApplication/6.4-CreateLaunchTemp/0003-createlt.png?featherlight=false&width=90pc)

4. Trong phần **Instance type**

   - Tại mục **Instance type**, chọn **t2.micro**

5. Trong phần **Key pair (login)**

   - Tại mục **Key pair name**, chúng ta có thể không cần chọn key pair **Don't include in launch template**

   ![Create Launch Template](/images/6-DeployApplication/6.4-CreateLaunchTemp/0004-createlt.png?featherlight=false&width=90pc)

6. Trong phần **Network settings**

   - Tại mục **Firewall (security groups)**, chọn **Select existing security group**
   - Tại mục **Common security groups**, chọn **WebserverSecurityGroup**
   - Chọn **Create launch template**

   ![Create Launch Template](/images/6-DeployApplication/6.4-CreateLaunchTemp/0005-createlt.png?featherlight=false&width=90pc)

7. Như vậy chúng ta đã tạo Launch Template thành công.

   ![Create Launch Template](/images/6-DeployApplication/6.4-CreateLaunchTemp/0006-createlt.png?featherlight=false&width=90pc)
