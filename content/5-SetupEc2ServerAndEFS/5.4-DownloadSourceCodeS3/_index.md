---
title: "Download Source Code from S3 to EC2 Setup Server"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 5.4 </b> "
---

#### Attach IAM Role to EC2 Setup Server

1. In the **Instances** interface:

   - Select **lamp-stack-setup-server**.
   - Click on **Actions** dropdown menu.
   - Choose **Security**.
   - Select **Modify IAM role**.

   ![Attach IAM to EC2](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.4-DownloadSourceCodeS3/0001-downloadfile.png?featherlight=false&width=90pc)

2. In the **Modify IAM role** interface:

   - Under **IAM role**, select **WS1-IAM-role-S3**.
   - Click **Update IAM role**.

   ![Attach IAM to EC2](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.4-DownloadSourceCodeS3/0002-downloadfile.png?featherlight=false&width=90pc)

#### Download Source Code from S3 to EC2 Setup Server

3. On the EC2 Setup Server, we will download the application's Source code from the S3 Bucket by executing the command:

```
sudo aws s3 sync s3://book-application-bucket /var/www/html
```

Afterwards, access the directory **/var/www/html** to verify that the Source download process was successful.

```
cd /var/www/html
ls -l
```

![Attach IAM to EC2](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.4-DownloadSourceCodeS3/0004-downloadfile.png?featherlight=false&width=90pc)

{{% notice note %}}
Note: Replace **book-application-bucket** with the name of the Bucket you created in the previous step.
{{% /notice %}}

4. Next, we will unzip the downloaded zip file from S3 and copy it into the html directory.

```
sudo unzip FCJ2024-sourcecode-wsl.zip
sudo cp -R FCJ2024-sourcecode-ws1/* /var/www/html/
```

![Attach IAM to EC2](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.4-DownloadSourceCodeS3/0006-downloadfile.png?featherlight=false&width=90pc)
