---
title: "Create IAM Role with S3 Policy"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4.4 </b> "
---

#### Create IAM Role with S3 Policy

1. Click on the search bar

   - Type **`iam`**
   - Under **Services**, select **IAM**

   ![Create IAM Role](/images/4-DeployRDSAndS3/4.4.-CreateIAMAndS3Policy/0001-createiam.png?featherlight=false&width=90pc)

2. In the **Identity and Access Management (IAM)** interface

   - Choose **Roles**
   - Then select **Create role**

   ![Create IAM Role](/images/4-DeployRDSAndS3/4.4.-CreateIAMAndS3Policy/0002-createiam.png?featherlight=false&width=90pc)

3. In the **Select trusted entity** section

   - Under **Trusted entity type**, choose **AWS service**

   ![Create IAM Role](/images/4-DeployRDSAndS3/4.4.-CreateIAMAndS3Policy/0003-createiam.png?featherlight=false&width=90pc)

   Next,

   - Under **Service or use case**, select **EC2**
   - Then click **Next** to proceed

   ![Create IAM Role](/images/4-DeployRDSAndS3/4.4.-CreateIAMAndS3Policy/0004-createiam.png?featherlight=false&width=90pc)

4. In the **Add permissions** section

   - Use the search bar and look for **`AmazonS3FullAccess`**
   - Click on the identified **Policy name**
   - Then click **Next** to proceed

   ![Create IAM Role](/images/4-DeployRDSAndS3/4.4.-CreateIAMAndS3Policy/0005-createiam.png?featherlight=false&width=90pc)

5. In the **Name, review, and create** section

   - Under **Role name**, enter **`WS1-IAM-role-S3`**
   - Under **Description**, enter **`Allows EC2 instances to call AWS services on your behalf.`**

   ![Create IAM Role](/images/4-DeployRDSAndS3/4.4.-CreateIAMAndS3Policy/0006-createiam.png?featherlight=false&width=90pc)

   Finally, click **Create role** to complete the IAM Role creation.

   ![Create IAM Role](/images/4-DeployRDSAndS3/4.4.-CreateIAMAndS3Policy/0008-createiam.png?featherlight=false&width=90pc)
