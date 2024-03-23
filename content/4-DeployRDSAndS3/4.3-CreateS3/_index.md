---
title: "Create S3 Bucket and Upload Source Code"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.3 </b> "
---

#### Create S3 Bucket

1. Start by clicking on the search bar

   - Type **`s3`**
   - Under **Services**, select **S3**

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0001-creates3.png?featherlight=false&width=90pc)

2. In the **Amazon S3** interface,

   - Choose **Create bucket**

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0002-creates3.png?featherlight=false&width=90pc)

3. In the **Create bucket** interface,

   - Under **AWS Region**, select **US East (N. Virginia) us-east-1**
   - For **Bucket type**, choose **General purpose**
   - In **Bucket name**, enter **`book-application-bucket`**

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0003-creates3.png?featherlight=false&width=90pc)

   Next,

   - For **Object Ownership**, select **ACLs disabled (recommended)**

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0004-creates3.png?featherlight=false&width=90pc)

   - Leave the remaining fields with default values and finally select **Create bucket**

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0005-creates3.png?featherlight=false&width=90pc)

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0006-creates3.png?featherlight=false&width=90pc)

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0007-creates3.png?featherlight=false&width=90pc)

4. Bucket creation completed as shown in the image

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0008-creates3.png?featherlight=false&width=90pc)

#### Upload Source code to S3 Bucket

5. Access the newly created Bucket and select **Upload**

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0009-creates3.png?featherlight=false&width=90pc)

6. Choose the Source code of the LAMP-Stack project

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0010-creates3.png?featherlight=false&width=90pc)

7. Completion of the upload process

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0012-creates3.png?featherlight=false&width=90pc)

   ![Create S3](/images/4-DeployRDSAndS3/4.3-CreateS3/0013-creates3.png?featherlight=false&width=90pc)
