---
title: "Tạo S3 Bucket và Upload Source Code"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.3 </b> "
---

#### Tạo S3 Bucket

1. Chúng ta nhấn chọn thanh tìm kiếm

   - Nhập **`s3`**
   - Tại mục **Services** chọn **S3**

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0001-creates3.png?featherlight=false&width=90pc)

2. Tại giao diện **Amazon S3**

   - Chọn **Create bucket**

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0002-creates3.png?featherlight=false&width=90pc)

3. Trong giao diện **Create bucket**

   - Tại mục **AWS Region**, chọn **US East (N. Virginia) us-east-1**
   - Tại mục **Bucket type**, chọn **General purpose**
   - Tại mục **Bucket name**, nhập **`book-application-bucket`**

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0003-creates3.png?featherlight=false&width=90pc)

   Tiếp tục,

   -Tại mục **Object Ownership**, chọn **ACLs disabled (recommended)**

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0004-creates3.png?featherlight=false&width=90pc)

   - Các trường thông tin còn lại chúng ta sẽ để giá trị mặc định như ảnh và cuối cùng chọn **Create bucket**

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0005-creates3.png?featherlight=false&width=90pc)

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0006-creates3.png?featherlight=false&width=90pc)

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0007-creates3.png?featherlight=false&width=90pc)

4. Hoàn thành việc tạo Bucket như ảnh

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0008-creates3.png?featherlight=false&width=90pc)

#### Upload Source code lên S3 Bucket

5. Chúng ta sẽ truy cập vào Bucket vừa tạo, chọn **Upload**

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0009-creates3.png?featherlight=false&width=90pc)

6. Chọn Source code của project sử dụng LAMP-Stack

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0010-creates3.png?featherlight=false&width=90pc)

7. Hoàn thành việc upload

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0012-creates3.png?featherlight=false&width=90pc)

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0013-creates3.png?featherlight=false&width=90pc)
