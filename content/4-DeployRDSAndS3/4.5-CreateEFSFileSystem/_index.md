---
title: "Create EFS File System"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 4.5 </b> "
---

#### Create EFS File System

1. Click on the search bar

   - Type **`efs`**
   - Under **Services**, select **EFS**

   ![Create EFS File System](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0001-createefs.png?featherlight=false&width=90pc)

2. In the **Elastic File System** interface

   - Click **Create file system**

   ![Create EFS File System](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0002-createefs.png?featherlight=false&width=90pc)

3. In the **Create file system** section

   - Select **Customize**

   ![Create EFS File System](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0003-createefs.png?featherlight=false&width=90pc)

4. In the **File system settings** section

   - Under **Name - optional**, enter **`bookstore-efs`**
   - For **File system type**, choose **Regional**
   - Enable automatic backups under **Automatic backups**

   ![Create EFS File System](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0004-createefs.png?featherlight=false&width=90pc)

   - Leave other options at default values and click **Next** to proceed

   ![Create EFS File System](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0005-createefs.png?featherlight=false&width=90pc)

   ![Create EFS File System](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0006-createefs.png?featherlight=false&width=90pc)

5. In the **Network access** section

   - Under **Virtual Private Cloud (VPC)**, select **vpc-Oacb9059f41ab5a37**
   - For **Mount targets**,
     - Choose **us-east-1a** for **Availability zone** and **EFSSecurityGroup** for **Security groups**
     - Choose **us-east-1b** for **Availability zone** and **EFSSecurityGroup** for **Security groups**

{{% notice note %}}
Note: To add a new Target, click on **Add mount target**
{{% /notice %}}

![Create EFS File System](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0007-createefs.png?featherlight=false&width=90pc)

- Click **Next** to proceed

  ![Create EFS File System](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0008-createefs.png?featherlight=false&width=90pc)

6. In the **Review and create** section, click **Create File System** to complete the EFS File System creation.

   ![Create EFS File System](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0009-createefs.png?featherlight=false&width=90pc)

#### DNS name

7. Make sure to note down the value in **DNS name** for later use in attaching the drive to the web server.

   ![Create EFS File System](/workshop1-FCJ2024/images/4-DeployRDSAndS3/4.5-CreateEFSFileSystem/0010-createefs.png?featherlight=false&width=90pc)
