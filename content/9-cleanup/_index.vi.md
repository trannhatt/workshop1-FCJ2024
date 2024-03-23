---
title: "Dọn dẹp tài nguyên"
date: "`r Sys.Date()`"
weight: 9
chapter: false
pre: " <b> 9. </b> "
---

#### Dọn dẹp CloudFront

1. Truy cập giao diện **CloudFront**

   - Chọn **Distributions**
   - Chọn **E2H26TUZ72XRKT**
   - Chọn **Disable**

   ![Clean CloudFront](/workshop1-FCJ2024/images/9-Clean/0001-cleancloudfront.png?featherlight=false&width=90pc)

2. Trong phần **Disable distribution?**

   - Chọn **Disable**

   ![Clean CloudFront](/workshop1-FCJ2024/images/9-Clean/0002-cleancloudfront.png?featherlight=false&width=90pc)

3. Khi trường **Status** là **Disabled**

   - Chọn lại **E2H26TUZ72XRKT**
   - Chọn **Delete**

   ![Clean CloudFront](/workshop1-FCJ2024/images/9-Clean/0003-cleancloudfront.png?featherlight=false&width=90pc)

4. Trong phần **Delete distribution?**

   - Chọn **Delete**

   ![Clean CloudFront](/workshop1-FCJ2024/images/9-Clean/0004-cleancloudfront.png?featherlight=false&width=90pc)

5. Hoàn thành việc dọn dẹp CloudFront

   ![Clean CloudFront](/workshop1-FCJ2024/images/9-Clean/0005-cleancloudfront.png?featherlight=false&width=90pc)

#### Dọn dẹp RDS Instance

6. Truy cập giao diện **Amazon RDS**

   - Chọn **Databases**
   - Chọn **book-rds-database**
   - Chọn thanh **Actions** đổ xuống các nội dung và chọn **Delete**

   ![Clean RDS](/workshop1-FCJ2024/images/9-Clean/0006-cleanrds.png?featherlight=false&width=90pc)

   - Chúng ta sẽ bỏ chọn **Create final snapshot** và **Retain automated backups**
   - Chọn **I acknowledge that upon instance deletion, automated backups, including system snapshots and point-in-time recovery, will no longer be available.**
   - Trong mục **confirm deletion**, nhập **`delete me`**
   - Chọn **Delete**

   ![Clean RDS](/workshop1-FCJ2024/images/9-Clean/0007-cleanrds.png?featherlight=false&width=90pc)

   - Đợi một lúc để hoàn tất việc xoá Database

   ![Clean RDS](/workshop1-FCJ2024/images/9-Clean/0008-cleanrds.png?featherlight=false&width=90pc)

7. Tại giao diện **Amazon RDS**

   - Chọn **Subnet groups**
   - Chọn **book-rds-subnet-group**
   - Chọn **Delete**

   ![Clean RDS](/workshop1-FCJ2024/images/9-Clean/0009-cleanrds.png?featherlight=false&width=90pc)

8. Trong phần **Delete book-rds-subnet-group DB subnet group?**

   - Chọn **Delete**

   ![Clean RDS](/workshop1-FCJ2024/images/9-Clean/0010-cleanrds.png?featherlight=false&width=90pc)

   - Hoàn thành việc dọn dẹp Subnet groups

   ![Clean RDS](/workshop1-FCJ2024/images/9-Clean/0011-cleanrds.png?featherlight=false&width=90pc)

#### Dọn dẹp Auto Scaling Group

9. Truy cập giao diện **EC2**

   - Chọn **Auto Scaling Groups**
   - Chọn 2 Auto Scaling Group **bastion-host-asg** và **bookstore-asg**
   - Chọn thanh **Actions** sẽ đổ nội dung xuống và chọn **Delete**

   ![Clean ASG](/workshop1-FCJ2024/images/9-Clean/0012-cleanasg.png?featherlight=false&width=90pc)

10. Trong phần **Delete 2 Auto Scaling groups**

    - Tại mục **confirm deletion**, nhập **`delete 2`**
    - Chọn **Delete**

    ![Clean ASG](/workshop1-FCJ2024/images/9-Clean/0013-cleanasg.png?featherlight=false&width=90pc)

    - Hoàn thành việc dọn dẹp Auto Scaling Group

    ![Clean ASG](/workshop1-FCJ2024/images/9-Clean/0014-cleanasg.png?featherlight=false&width=90pc)

#### Dọn dẹp Application Load Balancer và Target Group

11. Truy cập giao diện **EC2**

    - Chọn **Load Balancers**
    - Chọn **lamp-stack-alb**
    - Chọn thanh **Actions** sẽ đổ nội dung xuống và chọn **Delete load balancer**

    ![Clean ALB](/workshop1-FCJ2024/images/9-Clean/0016-cleanalb.png?featherlight=false&width=90pc)

12. Trong phần **Delete load balancer**

    - Tại mục **confirm**, nhập **`confirm`**
    - Chọn **Delete**

    ![Clean ALB](/workshop1-FCJ2024/images/9-Clean/0017-cleanalb.png?featherlight=false&width=90pc)

13. Tiếp theo, cũng tại giao diện **EC2**

    - Chọn **Target Groups**
    - Chọn **lamp-stack-tg**
    - Chọn thanh **Actions** sẽ đổ nội dung xuống và chọn **Delete**

    ![Clean ALB](/workshop1-FCJ2024/images/9-Clean/0018-cleanalb.png?featherlight=false&width=90pc)

14. Trong phần **Delete target group?**

    - Chọn **Yes, delete**

    ![Clean ALB](/workshop1-FCJ2024/images/9-Clean/0019-cleanalb.png?featherlight=false&width=90pc)

#### Dọn dẹp Launch Template và AMI

Chúng ta sẽ lần lượt dọn dẹp Launch Template của Bastion Host và của máy chủ ứng dụng Web

15. Truy cập giao diện **EC2**

    - Chọn **Launch Templates**
    - Chọn **bastion-host-launch-template**
    - Chọn thanh **Actions** sẽ đổ nội dung xuống và chọn **Delete template**

    ![Clean Launch Template & AMI](/workshop1-FCJ2024/images/9-Clean/0020-cleanltami.png?featherlight=false&width=90pc)

    Tiếp tục,

    - Chọn **Launch Templates**
    - Chọn **Bookstore-launch-template**
    - Chọn thanh **Actions** sẽ đổ nội dung xuống và chọn **Delete template**

    ![Clean Launch Template & AMI](/workshop1-FCJ2024/images/9-Clean/0021-cleanltami.png?featherlight=false&width=90pc)

16. Tiếp theo, cũng tại giao diện **EC2**

    - Chọn **AMIs**
    - Trong phần **Amazon Machine Images (AMis)**, chọn cả 2 **Bookstore AMI** và **Bastion Host AMI**
    - Chọn thanh **Actions** sẽ đổ nội dung xuống và chọn **Deregister AMI**

    ![Clean Launch Template & AMI](/workshop1-FCJ2024/images/9-Clean/0023-cleanltami.png?featherlight=false&width=90pc)

17. Trong phần **Deregister AMI**

    - Chọn **Deregister AMI**

    ![Clean Launch Template & AMI](/workshop1-FCJ2024/images/9-Clean/0024-cleanltami.png?featherlight=false&width=90pc)

#### Dọn dẹp NAT Gateway

Chúng ta sẽ lần lượt dọn dẹp 2 NAT Gateway

18. Truy cập giao diện **VPC**

    - Chọn **NAT gateways**
    - Chọn **lamp-stack-nat-pub-sub-1a**
    - Chọn thanh **Actions** sẽ đổ nội dung xuống và chọn **Delete NAT gateway**

    ![Clean NAT](/workshop1-FCJ2024/images/9-Clean/0025-cleannat.png?featherlight=false&width=90pc)

    Trong phần **Delete NAT gateway**,

    - Tại mục **confirm deletion**, nhập **`delete`**
    - Chọn **Delete**

    ![Clean NAT](/workshop1-FCJ2024/images/9-Clean/0026-cleannat.png?featherlight=false&width=90pc)

    Tiếp tục,

    - Chọn **lamp-stack-nat-pub-sub-2b**
    - Chọn thanh **Actions** sẽ đổ nội dung xuống và chọn **Delete NAT gateway**

    ![Clean NAT](/workshop1-FCJ2024/images/9-Clean/0027-cleannat.png?featherlight=false&width=90pc)

    Trong phần **Delete NAT gateway**,

    - Tại mục **confirm deletion**, nhập **`delete`**
    - Chọn **Delete**

    ![Clean NAT](/workshop1-FCJ2024/images/9-Clean/0028-cleannat.png?featherlight=false&width=90pc)

#### Dọn dẹp EFS File System

19. Truy cập giao diện **Elastic File System**

    - Chọn vào file system của dự án.
    - Chọn **Network**
    - Chọn **Manage**

    ![Clean EFS](/workshop1-FCJ2024/images/9-Clean/0029-cleanvpc.png?featherlight=false&width=90pc)

    Tiếp theo, trong phần **Mount targets**

    - Chọn **Remove** cả 2 targets
    - Chọn **Save**

    ![Clean EFS](/workshop1-FCJ2024/images/9-Clean/0030-cleanvpc.png?featherlight=false&width=90pc)

20. Ra ngoài giao diện **File systems**

    - Chọn **bookstore-efs**
    - Chọn **Delete**

    ![Clean EFS](/workshop1-FCJ2024/images/9-Clean/0031-cleanvpc.png?featherlight=false&width=90pc)

    Trong phần **Delete file system**,

    - Nhập **`fs-061c0cc037d521abf`**, là ID File System của bạn
    - Chọn **Confirm**

    ![Clean EFS](/workshop1-FCJ2024/images/9-Clean/0032-cleanvpc.png?featherlight=false&width=90pc)

#### Dọn dẹp VPC

21. Truy cập giao diện **VPC**

    - Chọn **Your VPCs**
    - Chọn **lamp-stack-vpc**
    - Chọn thanh **Actions** sẽ đổ xuống nội dung và chọn **Delete VPC**

    ![Clean VPC](/workshop1-FCJ2024/images/9-Clean/0033-cleanvpc.png?featherlight=false&width=90pc)

22. Trong phần **Delete VPC**,

    - Nhập **`delete`**
    - Chọn **Delete**

    ![Clean VPC](/workshop1-FCJ2024/images/9-Clean/0034-cleanvpc.png?featherlight=false&width=90pc)
