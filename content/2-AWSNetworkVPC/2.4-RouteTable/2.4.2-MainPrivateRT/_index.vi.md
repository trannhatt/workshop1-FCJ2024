---
title: "Tạo và cấu hình Main Route Table"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.4.2 </b> "
---

#### Tạo và cấu hình Main Route Table

1. Khi chúng ta tạo VPC, sẽ có một Route Table mặc định được tạo và nó private, chúng ta sẽ gọi là **Main Route Table**. Tại giao diện **Route tabless**

   - Chọn **rtb-05a6febb5380e833f** như đã nêu
   - Chọn mục **Subnet associations**
   - Chọn **Edit subnet associations**

   ![Configure Main Route Table](/workshop1-FCJ2024/images/2.4-RouteTable/2.4.2-MainPrivateRT/0001-mainrt.png?featherlight=false&width=90pc)

   - Tại mục **Available subnets**, chọn các private subnet bao gồm **pri-sub-3a**, **pri-sub-4b**, **pri-sub-5a** và **pri-sub-6b**
   - Cuối cùng, chọn **Save associations**

   ![Configure Main Route Table](/workshop1-FCJ2024/images/2.4-RouteTable/2.4.2-MainPrivateRT/0002-mainrt.png?featherlight=false&width=90pc)

   - Kết quả sau khi liên kết như sau

   ![Configure Main Route Table](/workshop1-FCJ2024/images/2.4-RouteTable/2.4.2-MainPrivateRT/0003-mainrt.png?featherlight=false&width=90pc)
