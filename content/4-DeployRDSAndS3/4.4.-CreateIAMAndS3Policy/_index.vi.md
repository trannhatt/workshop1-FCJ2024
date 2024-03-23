---
title: "Tạo IAM Role với S3 Policy"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4.4 </b> "
---

#### Tạo IAM Role với S3 Policy

1. Chúng ta nhấn chọn thanh tìm kiếm

   - Nhập **`iam`**
   - Tại mục **Services** chọn **IAM**

   ![Create IAM Role](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.4.-CreateIAMAndS3Policy/0001-createiam.png?featherlight=false&width=90pc)

2. Tại giao diện **Identity and Access Management (IAM)**

   - Chọn **Roles**
   - Sau đó chọn **Create role**

   ![Create IAM Role](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.4.-CreateIAMAndS3Policy/0002-createiam.png?featherlight=false&width=90pc)

3. Trong phần **Select trusted entity**

   - Tại mục **Trusted entity type**, chọn **AWS service**

   ![Create IAM Role](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.4.-CreateIAMAndS3Policy/0003-createiam.png?featherlight=false&width=90pc)

   Tiếp tục,

   - Tại mục **Service or use case**, chọn **EC2**
   - Sau đó chọn **Next** để qua bước tiếp theo

   ![Create IAM Role](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.4.-CreateIAMAndS3Policy/0004-createiam.png?featherlight=false&width=90pc)

4. Trong phần **Add permissions**

   - Chọn thanh tìm kiếm và tìm **`AmazonS3FullAccess`**
   - Chọn vào **Policy name** vừa tìm được
   - Chọn **Next** để qua bước tiếp theo

   ![Create IAM Role](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.4.-CreateIAMAndS3Policy/0005-createiam.png?featherlight=false&width=90pc)

5. Trong phần **Name, review, and create**

   - Tại mục **Role name**, nhập **`WS1-IAM-role-S3`**
   - Tại mục **Description**, nhập **`Allows EC2 instances to call AWS services on your behalf.`**

   ![Create IAM Role](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.4.-CreateIAMAndS3Policy/0006-createiam.png?featherlight=false&width=90pc)

   Cuối cùng, chọn **Create role** để hoàn thành việc tạo IAM Role.

   ![Create IAM Role](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.4.-CreateIAMAndS3Policy/0008-createiam.png?featherlight=false&width=90pc)
