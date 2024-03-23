---
title: "Tạo EFS File System"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 4.5 </b> "
---

#### Tạo EFS File System

1. Chúng ta nhấn chọn thanh tìm kiếm

   - Nhập **`efs`**
   - Tại mục **Services** chọn **EFS**

   ![Create EFS File System](/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0001-createefs.png?featherlight=false&width=90pc)

2. Tại giao diện **Elastic File System**

   - Chọn **Create file system**

   ![Create EFS File System](/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0002-createefs.png?featherlight=false&width=90pc)

3. Trong phần **Create file system**

   - Chọn **Customize**

   ![Create EFS File System](/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0003-createefs.png?featherlight=false&width=90pc)

4. Trong phần **File system settings**

   - Tại mục **Name - optional**, nhập **`bookstore-efs`**
   - Tại mục **File system type**, chọn **Regional**
   - Tại mục **Automatic backups**, chọn **Enable automatic backups**

   ![Create EFS File System](/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0004-createefs.png?featherlight=false&width=90pc)

- Các mục còn lại để giá trị mặc định và chọn **Next** để qua bước tiếp theo

  ![Create EFS File System](/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0005-createefs.png?featherlight=false&width=90pc)

  ![Create EFS File System](/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0006-createefs.png?featherlight=false&width=90pc)

5. Trong phần **Network access**

   - Tại mục **Virtual Private Cloud (VPC)**, chọn **vpc-Oacb9059f41ab5a37**
   - Tại phần **Mount targets**,
     - Tại mục **Availability zone** chọn **us-east-1a** và tại mục **Security groups** chọn **EFSSecurityGroup**
     - Tại mục **Availability zone** chọn **us-east-1b** và tại mục **Security groups** chọn **EFSSecurityGroup**

{{% notice note %}}
Lưu ý: Để thêm một Target mới, chúng ta chọn **Add mount target**
{{% /notice %}}

![Create EFS File System](/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0007-createefs.png?featherlight=false&width=90pc)

- Chọn **Next** để qua bước tiếp theo

  ![Create EFS File System](/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0008-createefs.png?featherlight=false&width=90pc)

6. Trong phần **Review and create**, chọn **Create File System** để hoàn thành việc tạo EFS File System.

   ![Create EFS File System](/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0009-createefs.png?featherlight=false&width=90pc)

#### DNS name

7. Chúng ta cần lưu lại giá trị trong **DNS name** để sau này dùng để gắn ổ đĩa vào máy chủ Web.

   ![Create EFS File System](/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0010-createefs.png?featherlight=false&width=90pc)
