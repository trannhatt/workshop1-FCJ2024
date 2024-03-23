---
title: "Tải Source Code từ S3 vào EC2 Setup Server"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 5.4 </b> "
---

#### Gắn IAM Role vào EC2 Setup Server

1. Trong giao diện **Instances**

   - Chọn **lamp-stack-setup-server**
   - Chọn thanh **Actions** sẽ đổ xuống các hành động.
   - Chọn **Security**
   - Chọn **Modify IAM role**

   ![Attach IAM to EC2](/images/5-SetupEc2ServerAndEFS/5.4-DownloadSourceCodeS3/0001-downloadfile.png?featherlight=false&width=90pc)

2. Trong giao diện **Modify IAM role**

   - Tại mục **IAM role**, chọn **WS1-IAM-role-S3**
   - Chọn **Update IAM role**

   ![Attach IAM to EC2](/images/5-SetupEc2ServerAndEFS/5.4-DownloadSourceCodeS3/0002-downloadfile.png?featherlight=false&width=90pc)

#### Tải Source Code từ S3 vào EC2 Setup Server

3. Trong EC2 Setup Server, chúng ta sẽ tải Source code của ứng dụng từ S3 Bucket bằng cách nhập lệnh

```
sudo aws s3 sync s3://book-application-bucket /var/www/html
```

Sau đó truy cập vào thư mục **/var/www/html** để xác minh quá trình tải Source thành công

```
cd /var/www/html
ls -l
```

![Attach IAM to EC2](/images/5-SetupEc2ServerAndEFS/5.4-DownloadSourceCodeS3/0004-downloadfile.png?featherlight=false&width=90pc)

{{% notice note %}}
Lưu ý: thay **book-application-bucket** bằng tên của Bucket bạn tạo trong bước trước.
{{% /notice %}}

4. Tiếp theo, chúng ta sẽ giải nén tệp zip đã tải từ S3 và sao chép vào thư mục html.

```
sudo unzip FCJ2024-sourcecode-wsl.zip
sudo cp -R FCJ2024-sourcecode-ws1/* /var/www/html/
```

![Attach IAM to EC2](/images/5-SetupEc2ServerAndEFS/5.4-DownloadSourceCodeS3/0006-downloadfile.png?featherlight=false&width=90pc)
