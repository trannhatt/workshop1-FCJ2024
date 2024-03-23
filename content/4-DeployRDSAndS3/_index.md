---
title: "Database and Storage Service Deployment"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

#### Database and Storage Service Deployment

In this section, we will configure important services such as databases and storage. Firstly, we will create a **DB Subnet Group** for the database to ensure a secure network environment. Next, we will create an **RDS Instance** and adjust technical settings as required. Then, we will create an **S3 Bucket** to store the application source code and upload necessary files. To manage access permissions to the S3 bucket, we need to create an **IAM role** with appropriate policies. Finally, we will deploy an **EFS file system** to store and share data among EC2 instances.

#### Contents

1. [Create DB Subnet Group](4.1-CreateDBSG/)
2. [Create RDS Instance](4.2-RDSIntance/)
3. [Create S3 Bucket and Upload Source Code](4.3-CreateS3/)
4. [Create IAM Role and S3 Policy](4.4.-CreateIAMAndS3Policy/)
5. [Create EFS File System](4.5-CreateEFSFileSystem/)
