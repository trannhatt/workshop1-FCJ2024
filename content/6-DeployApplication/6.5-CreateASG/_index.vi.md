---
title: "Tạo Autoscaling Group"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 6.5 </b> "
---

#### Tạo Autoscaling Group

1. Tại giao diện **EC2**

   - Chọn **Auto Scaling Groups**
   - Chọn **Create Auto Scaling group**

   ![Create ASG](/images/6-DeployApplication/6.5-CreateASG/0001-createasg.png?featherlight=false&width=90pc)

2. Trong phần **Choose launch template or configuration**

   - Tại mục **Auto Scaling group name**, nhập **`bookstore-asg`**
   - Tại mục **Launch templaten**, chọn **Bookstore-launch-template** là Template đã tạo ở bước trước

   ![Create ASG](/images/6-DeployApplication/6.5-CreateASG/0002-createasg.png?featherlight=false&width=90pc)

   - Chọn **Next** để sang bước tiếp theo.

   ![Create ASG](/images/6-DeployApplication/6.5-CreateASG/0003-createasg.png?featherlight=false&width=90pc)

3. Trong phần **Choose instance launch options**

   ![Create ASG](/images/6-DeployApplication/6.5-CreateASG/0004-createasg.png?featherlight=false&width=90pc)

   - Tại mục **VPC**, chọn **vpc-Oacb9059f41ab5a37 (lamp-stack-vpc)**
   - Tại mục **Availability Zones and subnets**, chọn **us-east-1a | subnet-05c2f5e92fd59e436 (pri-sub-3а)** và **us-east-1b | subnet-08f6c0fba219ec914 (pri-sub- X4b)**

   ![Create ASG](/images/6-DeployApplication/6.5-CreateASG/0005-createasg.png?featherlight=false&width=90pc)

   - Chọn **Next** để sang bước tiếp theo.

4. Trong phần **Configure advanced options**

   - Tại mục **Load balancing**, chọn **Attach to an existing load balancer**
   - Tại mục **Attach to an existing load balancer**, chọn **Choose from your load balancer target groups**
   - Tại mục **Existing load balancer target groups**, chọn **lamp-stack-tg | HTTP**

   ![Create ASG](/images/6-DeployApplication/6.5-CreateASG/0006-createasg.png?featherlight=false&width=90pc)

   - Các trường thông tin còn lại để mặc định như ảnh

   ![Create ASG](/images/6-DeployApplication/6.5-CreateASG/0007-createasg.png?featherlight=false&width=90pc)

   - Tại mục **Monitoring**, chọn **Enable group metrics collection within CloudWatch**
   - Chọn **Next** để sang bước tiếp theo.

   ![Create ASG](/images/6-DeployApplication/6.5-CreateASG/0008-createasg.png?featherlight=false&width=90pc)

5. Trong phần **Configure group size and scaling - optional**

   - Tại mục **Desired capacity**, nhập **`2`**

   ![Create ASG](/images/6-DeployApplication/6.5-CreateASG/0009-createasg.png?featherlight=false&width=90pc)

   - Tại mục **Min desired capacity**, nhập **`2`**
   - Tại mục **Max desired capacity**, nhập **`4`**
   - Tại mục **Automatic scaling - optional**, chọn **Target tracking scaling policy**

   ![Create ASG](/images/6-DeployApplication/6.5-CreateASG/0010-createasg.png?featherlight=false&width=90pc)

   - Tại mục **Instance warmup**, nhập **`300`**

   ![Create ASG](/images/6-DeployApplication/6.5-CreateASG/0011-createasg.png?featherlight=false&width=90pc)

   - Chọn **Next** để sang bước tiếp theo.

   ![Create ASG](/images/6-DeployApplication/6.5-CreateASG/0012-createasg.png?featherlight=false&width=90pc)

6. Trong phần **Add notifications**, chúng ta sẽ thêm một thông báo về sự cố của các Instance trong ứng dụng Web

   - Tại mục **Send a notification to**, nhập **`cloud-watch-alarm-bookstore-topic`**
   - Tại mục **With these recipients**, nhập **`0521.20nn@gmail.com`**, là mail của bạn muốn nhận thông báo.
   - Tại mục **Event types**, chọn tất cả các trường thông tin
   - Chọn **Next** để sang bước tiếp theo.

   ![Create ASG](/images/6-DeployApplication/6.5-CreateASG/0013-createasg.png?featherlight=false&width=90pc)

7. Trong phần **Add tags - optional**

   - Tại mục **Tags**:
     - **Key** nhập **`Name`**
     - **Value - optional** nhập **`bookstore-asg`**
   - Chọn **Next** để sang bước tiếp theo.

   ![Create ASG](/images/6-DeployApplication/6.5-CreateASG/0014-createasg.png?featherlight=false&width=90pc)

8. Tại phần **Review**, chúng ta sẽ kiểm tra lại lần nửa các thông tin vừa cung cấp

   - Chọn **Create Auto Scaling group** để hoàn tất quá trình.

   ![Create ASG](/images/6-DeployApplication/6.5-CreateASG/0015-createasg.png?featherlight=false&width=90pc)

9. Như vậy chúng ta đã tạo Autoscaling Group thành công.

   ![Create ASG](/images/6-DeployApplication/6.5-CreateASG/0016-createasg.png?featherlight=false&width=90pc)

10. Truy cập vào giao diện **EC2 Instance** chúng ta thấy 2 máy chủ ứng dụng Web đang hoạt động

    ![Create ASG](/images/6-DeployApplication/6.5-CreateASG/0017-createasg.png?featherlight=false&width=90pc)
