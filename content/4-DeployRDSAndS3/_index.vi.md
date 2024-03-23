---
title: "Triển khai cơ sở dữ liệu và dịch vụ lưu trữ"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

#### Triển khai cơ sở dữ liệu và dịch vụ lưu trữ

Trong phần này, chúng ta sẽ tiến hành cấu hình các dịch vụ quan trọng như cơ sở dữ liệu và dịch vụ lưu trữ. Đầu tiên, chúng ta sẽ tạo **DB Subnet Sroup** cho cơ sở dữ liệu để đảm bảo môi trường mạng an toàn. Tiếp theo, chúng ta sẽ tạo **RDS Instance** và điều chỉnh các cài đặt kỹ thuật theo yêu cầu. Sau đó, chúng ta sẽ tạo **S3 Bucket** để lưu trữ mã nguồn của ứng dụng và tải lên các tệp cần thiết. Để quản lý quyền truy cập vào bucket S3, chúng ta cần tạo **IAM role** thiết lập policy tương ứng. Cuối cùng, chúng ta sẽ triển khai một hệ thống tệp **EFS** để lưu trữ và chia sẻ dữ liệu giữa các máy EC2.

#### Nội dung

1. [Tạo DB Subnet Group](4.1-CreateDBSG/)
2. [Tạo RDS Instance](4.2-RDSIntance/)
3. [Tạo S3 Bucket và Upload Source Code](4.3-CreateS3/)
4. [Tạo IAM Role và S3 Policy](4.4.-CreateIAMAndS3Policy/)
5. [Tạo EFS File System](4.5-CreateEFSFileSystem/)
