---
title: "Tạo NAT Gateway"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.1 </b> "
---

#### Tạo NAT Gateway đầu tiên trong public subnet ở AZ us-east-1a

1. Tại giao diện **VPC**

   - Chọn **NAT gateways**
   - Chọn **Create NAT gateway**

   ![Create NAT gateway](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.1-CreateNATGW/0001-createnatgw.png?featherlight=false&width=90pc)

2. Trong giao diện **Create NAT gateway**

   - Tại **Name - optional**, nhập **`lamp-stack-nat-pub-sub-1a`**
   - Tại **Subnet**, chọn **subnet-09781d02f50504e98 (pub-sub-1a)**
   - Chọn **Allocate Elastic IP**

   ![Create NAT gateway](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.1-CreateNATGW/0002-createnatgw.png?featherlight=false&width=90pc)

   Tiếp tục,

   - Tại mục **Tags**:
     - **Key** nhập **`Name`**
     - **Value - optional** nhập **`lamp-stack-nat-pub-sub-1a`**
   - Cuối cùng, chọn **Create NAT gateway**

   ![Create NAT gateway](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.1-CreateNATGW/0003-createnatgw.png?featherlight=false&width=90pc)

   - Như vậy chúng ta đã tạo NAT Gateway thành công.

   ![Create NAT gateway](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.1-CreateNATGW/0004-createnatgw.png?featherlight=false&width=90pc)

#### Tạo NAT Gateway thứ 2 trong public subnet ở AZ us-east-1b

3. Chúng ta sẽ tạo NAT Gateway ở AZ còn lại.

   Tại giao diện **Create NAT gateway**

   - Chọn **Create NAT gateway**

   ![Create NAT gateway](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.1-CreateNATGW/0005-createnatgw.png?featherlight=false&width=90pc)

   Trong giao diện **Create NAT gateway**,

   - Tại **Name - optional**, nhập **`lamp-stack-nat-pub-sub-2b`**
   - Tại **Subnet**, chọn **subnet-03078b6edceb59c7e (pub-sub-2b)**
   - Chọn **Allocate Elastic IP**

   ![Create NAT gateway](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.1-CreateNATGW/0006-createnatgw.png?featherlight=false&width=90pc)

   Tiếp tục,

   - Tại mục **Tags**:
     - **Key** nhập **`Name`**
     - **Value - optional** nhập **`lamp-stack-nat-pub-sub-2b`**
   - Cuối cùng, chọn **Create NAT gateway**

   ![Create NAT gateway](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.1-CreateNATGW/0007-createnatgw.png?featherlight=false&width=90pc)

4. Như vậy, chúng ta đã tạo NAT Gateway 2 thành công. Tại mục **State** đều ở trạng thái **Available**

   ![Create NAT gateway](/workshop1-FCJ2024/images/3-CreateNATGWAndSG/3.1-CreateNATGW/0008-createnatgw.png?featherlight=false&width=90pc)
