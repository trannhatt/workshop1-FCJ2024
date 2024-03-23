---
title: "Gắn Internet Gateway vào VPC"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.2.2 </b> "
---

#### Gắn Internet Gateway vào VPC

1. Tại IGW mới vừa tạo **lamp-stack-igw**

   - Chọn thanh **Actions** sẽ có các nội dung đổ xuống và chọn **Attach to VPC**

   ![Attach to VPC](/images/2.2-InternetGateway/2.2.2-AttachToVPC/0001-attachtovpc.png?featherlight=false&width=90pc)

2. Trong giao diện **Attach to VPC**

   - Tại mục **Available VPCs**, chọn **vpc-Oacb9059f41ab5a37 - lamp-stack-vpc**
   - Chọn **Attach internet gateway**

   ![Attach to VPC](/images/2.2-InternetGateway/2.2.2-AttachToVPC/0002-attachtovpc.png?featherlight=false&width=90pc)

{{% notice note %}}
Lưu ý: **vpc-Oacb9059f41ab5a37** là **VPC ID** của bạn.
{{% /notice %}}

3. Chúng ta đã gắn **Internet Gateway** vào **VPC** thành công, tại mục **State** sẽ có nội dung là **Attached**
   ![Attach to VPC](/images/2.2-InternetGateway/2.2.2-AttachToVPC/0003-attachtovpc.png?featherlight=false&width=90pc)
   ![Attach to VPC](/images/2.2-InternetGateway/2.2.2-AttachToVPC/0004-attachtovpc.png?featherlight=false&width=90pc)
