---
title: "Tạo và cấu hình Private Route Table"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3.2 </b> "
---

#### Tạo và cấu hình Private Route Table

1. Tại giao diện **VPC**

   - Chọn **Route tables**
   - Chọn **Create route table**

   ![Create Private Route Table](/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0001-createprirt.png?featherlight=false&width=90pc)

2. Trong giao diện **Create route table**

   - Tại **Name - optional**, nhập **`lamp-stack-pri-rt-1`**
   - Tại **VPC**, chọn **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**
   - Tại mục **Tags**:
     - **Key** nhập **`Name`**
     - **Value - optional** nhập **`lamp-stack-pri-rt-1`**
   - Cuối cùng, chọn **Create route table**

   ![Create Private Route Table](/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0002-createprirt.png?featherlight=false&width=90pc)

3. Bây giờ chúng ta sẽ liên kết 2 Private Subnet ở AZ us-east-1a đã tạo trước đó vào Private Route Table này.

   - Chọn mục **Subnet associations**
   - Chọn **Edit subnet associations**

   ![Create Private Route Table](/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0003-createprirt.png?featherlight=false&width=90pc)

   - Tại mục **Available subnets**, chọn **pri-sub-3a** và **pri-sub-5a**
   - Cuối cùng, chọn **Save associations**

   ![Create Private Route Table](/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0004-createprirt.png?featherlight=false&width=90pc)

4. Tiếp theo, chúng ta sẽ thêm NAT Gateway ở AZ us-east-1a vào Private Route Table vừa tạo

   - Chọn mục **Routes**
   - Chọn **Edit routes**

   ![Create Private Route Table](/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0005-createprirt.png?featherlight=false&width=90pc)

   - Tại mục **Destination**, chọn **0.0.0.0/0**
   - Tại mục **Target**, chọn **NAT Gateway**
   - Sau đó chọn **nat-01aa9ae6861e6759a (lamp-stack-nat-pub-sub-1a)** là NAT chúng ta tạo ở phần trước.
   - Cuối cùng, chọn **Save changes**

   ![Create Private Route Table](/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0006-createprirt.png?featherlight=false&width=90pc)

{{% notice note %}}
Lưu ý: Trước khi chọn **0.0.0.0/0** tại mục **Destination** thì chúng ta phải chọn **Add route**
{{% /notice %}}

5. Chúng ta tiếp tục tạo Private Route Table thứ 2. Trong giao diện **Create route table**

   - Tại **Name - optional**, nhập **`lamp-stack-pri-rt-2`**
   - Tại **VPC**, chọn **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**
   - Tại mục **Tags**:
     - **Key** nhập **`Name`**
     - **Value - optional** nhập **`lamp-stack-pri-rt-2`**
   - Cuối cùng, chọn **Create route table**

   ![Create Private Route Table](/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0007-createprirt.png?featherlight=false&width=90pc)

6. Tiếp theo, chúng ta sẽ thêm NAT Gateway ở AZ us-east-1b vào Private Route Table thứ 2 vừa tạo

   - Chọn mục **Routes**
   - Chọn **Edit routes**

   ![Create Private Route Table](/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0008-createprirt.png?featherlight=false&width=90pc)

   - Tại mục **Destination**, chọn **0.0.0.0/0**
   - Tại mục **Target**, chọn **NAT Gateway**
   - Sau đó chọn **nat-052de2c3601c08459 (lamp-stack-nat-pub-sub-2b)** là NAT thứ 2 chúng ta tạo ở phần trước.
   - Cuối cùng, chọn **Save changes**

   ![Create Private Route Table](/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0009-createprirt.png?featherlight=false&width=90pc)

{{% notice note %}}
Lưu ý: Trước khi chọn **0.0.0.0/0** tại mục **Destination** thì chúng ta phải chọn **Add route**
{{% /notice %}}

7. Bây giờ chúng ta sẽ liên kết 2 Private Subnet ở AZ us-east-1b đã tạo trước đó vào Private Route Table thứ 2 này.

   - Chọn mục **Subnet associations**
   - Chọn **Edit subnet associations**

   ![Create Private Route Table](/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0010-createprirt.png?featherlight=false&width=90pc)

   - Tại mục **Available subnets**, chọn **pri-sub-4b** và **pri-sub-6b**
   - Cuối cùng, chọn **Save associations**

   ![Create Private Route Table](/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0011-createprirt.png?featherlight=false&width=90pc)

8. Kết quả sau khi tạo 2 Private Route Table như ảnh:

   ![Create Private Route Table](/images/3-CreateNATGWAndSG/3.2-CreatePrivateRT/0012-createprirt.png?featherlight=false&width=90pc)
