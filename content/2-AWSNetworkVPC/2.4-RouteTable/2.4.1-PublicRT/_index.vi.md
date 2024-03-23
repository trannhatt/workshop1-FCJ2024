---
title: "Tạo và cấu hình Public Route Table"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.4.1 </b> "
---

#### Tạo và cấu hình Public Route Table

1. Tại giao diện **VPC**

   - Chọn **Route tabless**
   - Chọn **Create route table**

   ![Create Route Table](/workshop1-FCJ2024/images/2.4-RouteTable/2.4.1-PublicRT/0001-creatert.png?featherlight=false&width=90pc)

2. Trong giao diện **Create route table**

   - Tại **Name - optional**, nhập **`lamp-stack-pub-rt`**
   - Tại **VPC**, chọn **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**
   - Tại mục **Tags**:
     - **Key** nhập **`Name`**
     - **Value - optional** nhập **`lamp-stack-pub-rt`**
   - Cuối cùng, chọn **Create route table**

   ![Create Route Table](/workshop1-FCJ2024/images/2.4-RouteTable/2.4.1-PublicRT/0002-creatert.png?featherlight=false&width=90pc)

3. Tiếp theo, chúng ta sẽ thêm Internet Gateway vào Public Route Table vừa tạo

   - Chọn mục **Routes**
   - Chọn **Edit routes**

   ![Create Route Table](/workshop1-FCJ2024/images/2.4-RouteTable/2.4.1-PublicRT/0003-creatert.png?featherlight=false&width=90pc)

   - Tại mục **Destination**, chọn **0.0.0.0/0**
   - Tại mục **Target**, chọn **Internet Gateway**
   - Sau đó chọn **igw-oc134f10ab513a4cd** là IGW chúng ta tạo ở phần trước.
   - Cuối cùng, chọn **Save changes**

   ![Create Route Table](/workshop1-FCJ2024/images/2.4-RouteTable/2.4.1-PublicRT/0004-creatert.png?featherlight=false&width=90pc)

{{% notice note %}}
Lưu ý: Trước khi chọn **0.0.0.0/0** tại mục **Destination** thì chúng ta phải chọn **Add route**
{{% /notice %}}

- Như vậy, chúng ta đã thêm 1 **Route** đên Internet từ ** Public Route Table**, kết quả sau khi thêm như sau

![Create Route Table](/workshop1-FCJ2024/images/2.4-RouteTable/2.4.1-PublicRT/0005-creatert.png?featherlight=false&width=90pc)

4. Bây giờ chúng ta sẽ liên kết 2 Public Subnet đã tạo trước đó vào Route Table này.

   - Chọn mục **Subnet associations**
   - Chọn **Edit subnet associations**

   ![Create Route Table](/workshop1-FCJ2024/images/2.4-RouteTable/2.4.1-PublicRT/0006-creatert.png?featherlight=false&width=90pc)

   - Tại mục **Available subnets**, chọn **pub-sub-2b** và **pub-sub-1a**
   - Cuối cùng, chọn **Save associations**

   ![Create Route Table](/workshop1-FCJ2024/images/2.4-RouteTable/2.4.1-PublicRT/0007-creatert.png?featherlight=false&width=90pc)

   - Kết quả sau khi liên kết như sau

   ![Create Route Table](/workshop1-FCJ2024/images/2.4-RouteTable/2.4.1-PublicRT/0008-creatert.png?featherlight=false&width=90pc)
