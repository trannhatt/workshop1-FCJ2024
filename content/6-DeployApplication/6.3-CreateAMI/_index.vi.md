---
title: "Tạo AMI"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 6.3 </b> "
---

#### Tạo AMI

1. Tại giao diện **EC2**

   - Chọn **Instances**
   - Chọn **lamp-stack-setup-server**
   - Chọn thanh **Actions** sẽ có các nội dung đổ xuống và chọn **Image and templates**
   - Chọn **Create image**

   ![Create AMI](/images/6-DeployApplication/6.3-Create%20AMI/0001-createami.png?featherlight=false&width=90pc)

2. Trong giao diện **Create image**

   - Tại mục **Image name**, nhập **`Bookstore AMI`**
   - Tại mục **Image description**, nhập **`Bookstore AMI`**

   ![Create AMI](/images/6-DeployApplication/6.3-Create%20AMI/0002-createami.png?featherlight=false&width=90pc)

   Tiếp tục,

   - Tại mục **Tags - optional**:
     - Chọn **Tag image and snapshots together**
     - **Key** nhập **`Name`**
     - **Value - optional** nhập **`Bookstore AMI`**

   ![Create AMI](/images/6-DeployApplication/6.3-Create%20AMI/0003-createami.png?featherlight=false&width=90pc)

3. Cuối cùng, chọn **Create** để hoàn tất việt tạo AMI

   ![Create AMI](/images/6-DeployApplication/6.3-Create%20AMI/0004-createami.png?featherlight=false&width=90pc)

4. Như vậy chúng ta đã tạo AMI thành công.

   ![Create AMI](/images/6-DeployApplication/6.3-Create%20AMI/0005-createami.png?featherlight=false&width=90pc)
