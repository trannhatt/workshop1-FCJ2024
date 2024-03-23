---
title: "Tạo Cloudfront và Web ACL"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 6.6 </b> "
---

#### Tạo Cloudfront

1. Nhấn chọn thanh tìm kiếm

   - Nhập **`cloudfront`**
   - Tại mục **Services** chọn **cloudFront**

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0001-createcloudfront.png?featherlight=false&width=90pc)

2. Tại giao diện **CloudFront**

   - Chọn **Create a CloudFront distribution**

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0002-createcloudfront.png?featherlight=false&width=90pc)

3. Trong phần **Origin**

   - Tại mục **Origin domain** chọn **lamp-stack-alb-541405871.us-east-1.elb.amazonaws.com**
   - Tại mục **Protocol**, chọn **HTTP Only**

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0003-createcloudfront.png?featherlight=false&width=90pc)

   - Các trường thông tin còn lại để mặc định như ảnh

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0004-createcloudfront.png?featherlight=false&width=90pc)

4. Trong phần **Default cache behavior**

   - Tại mục **Compress objects automatically**, chọn **Yes**
   - Tại mục **Viewer protocol policy**, chọn **HTTP and HTTPS**
   - Tại mục **Allowed HTTP methods**, chọn **GET, HEAD, OPTIONS, PUT, POST, PATCH, DELETE**

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0005-createcloudfront.png?featherlight=false&width=90pc)

   - Tại mục **Cache key and origin requests**, chọn **Cache policy and origin request policy (recommended)**
   - Các trường thông tin còn lại để như ảnh

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0006-createcloudfront.png?featherlight=false&width=90pc)

   - Các trường thông tin còn lại để mặc định như ảnh
   - Chọn **Create distribution** để hoàn tất việc tạo CloudFront Distribution

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0007-createcloudfront.png?featherlight=false&width=90pc)

5. Như vậy chúng ta đã tạo CloudFront Distribution thành công.

   - Tại mục **Distribution domain name**, copy nội dung và dán vào trình duyệt.

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0008-createcloudfront.png?featherlight=false&width=90pc)

   - Ảnh bên dưới cho thấy ứng dụng Web đã hoạt động với tên miền mới từ CloudFront.

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0009-createcloudfront.png?featherlight=false&width=90pc)

#### Tạo Web ACL

6. Nhấn chọn thanh tìm kiếm

   - Nhập **`waf`**
   - Tại mục **Services** chọn **WAF & Shield**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0001-createwaf.png?featherlight=false&width=90pc)

7. Tại giao diện **WAF & Shield**

   - Chọn **Getting started**
   - Chọn **Create web ACL**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0002-createwaf.png?featherlight=false&width=90pc)

8. Trong phần **Describe web ACL and associate it to AWS resources**

   - Tại mục **Resource type** chọn **Amazon CloudFront distributions**
   - Tại mục **Name**, nhập **`bookstore-app`**
   - Tại mục **Description - optional**, nhập **`protect my application`**
   - Tại mục **CloudWatch metric name**, nhập **`bookstore-app`**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0003-createwaf.png?featherlight=false&width=90pc)

   - Tại mục **Associated AWS resources - optional**, chọn **Add AWS resources**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0004-createwaf.png?featherlight=false&width=90pc)

   - Tại mục **Resource type**, chọn **CloudFront Distribution** và chọn Resource chúng ta đã tạo ở bước trước **E2H26TUZ72XRKT - d22fsOdgzskx5x.cloudfront.net**
   - Chọn **Add**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0005-createwaf.png?featherlight=false&width=90pc)

   - Chọn **Next** để qua phần tiếp theo

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0006-createwaf.png?featherlight=false&width=90pc)

9. Trong phần **Add rules and rule groups**

   - Tại mục **Rules**, chọn **Add rules** và chọn **Add managed rule groups**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0007-createwaf.png?featherlight=false&width=90pc)

   - Chọn **AWS managed rule groups**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0008-createwaf.png?featherlight=false&width=90pc)

   Trong **Free rule groups**, chọn **Add to web ACL** của các phần

   - **Amazon IP reputation list**
   - **Anonymous IP list**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0009-createwaf.png?featherlight=false&width=90pc)

   - **SQL database**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0010-createwaf.png?featherlight=false&width=90pc)

   - Chọn **Add rule**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0011-createwaf.png?featherlight=false&width=90pc)

10. Các nội dung còn lại để mặc định, chọn **Create web ACL** để hoàn tất việc tạo Web ACL

    ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0014-createwaf.png?featherlight=false&width=90pc)

11. Chúng ta đã tạo Web ACL thành công

    ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0015-createwaf.png?featherlight=false&width=90pc)
