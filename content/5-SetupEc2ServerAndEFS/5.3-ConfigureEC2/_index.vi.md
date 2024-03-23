---
title: "Cấu hình cho EC2 Setup Server"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 5.3 </b> "
---

#### Truy cập vào EC2 Setup Server thông qua Bastion Host

1. Tại giao diện **EC2 instance** chọn **Bastion Host** và sau đó chọn **Connect**

   - Chọn **EC2 Instance Connect**
   - Sau đó chọn **Connect**

   ![Bastion to EC2](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0001-bastiontoserver.png?featherlight=false&width=90pc)

2. Chúng ta thấy đã truy cập vào Bastion Host thành công

   ![Bastion to EC2](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0002-bastiontoserver.png?featherlight=false&width=90pc)

3. Nhập **`ping google.com`** để kiểm tra kết nối mạng internet, kết quả như ảnh

   ![Bastion to EC2](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0003-bastiontoserver.png?featherlight=false&width=90pc)

   ![Bastion to EC2](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0004-bastiontoserver.png?featherlight=false&width=90pc)

4. Nhập **`sudo nano ssh-key.pem`**, chúng ta sẽ tạo SSH Key để truy cập vào EC2 Setup Server.

   ![Bastion to EC2](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0005-bastiontoserver.png?featherlight=false&width=90pc)

5. Nội dung trong file **ssh-key.pem** sẽ nằm trong file key-pair mà chúng ta đã chọn trong lúc tạo EC2 Setup Server. Chúng ta sẽ copy vào đây, sau đó lưu và thoát truy cập file.

   ![Bastion to EC2](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0006-bastiontoserver.png?featherlight=false&width=90pc)

6. Nhập **`sudo chmod 400 ssh-key.pem`** để được phép đọc nội dung của tệp này, nhưng không cho phép ghi hoặc thực thi.

   ![Bastion to EC2](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0008-bastiontoserver.png?featherlight=false&width=90pc)

7. Cuối cùng nhập **`sudo "ssh-key.pem" ec2-user@10.0.3.239`** để truy cập vào EC2 Setup Server.

{{% notice note %}}
Lưu ý: **10.0.3.239** là địa chỉ private IPv4 của EC2 Setup Server. Vì vậy bạn hãy thay địa chỉ đó của bạn vào nhé!
{{% /notice %}}
![Bastion to EC2](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0009-bastiontoserver.png?featherlight=false&width=90pc)

8. Nhập **`ping google.com`** để kiểm tra kết nối mạng internet, kết quả như ảnh

   ![Bastion to EC2](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/00010-bastiontoserver.png?featherlight=false&width=90pc)

#### Cập nhật phiên bản và cài phần mềm cần thiết trên EC2 Setup Server

9. Tiếp theo, chúng ta sẽ tiến hành cập nhật phiên bản và cài đặt phần mềm thiết yếu, bao gồm Apache, PHP và MySQL.

```
sudo yum update -y
sudo yum install php -y
sudo yum install php-mysqli -y
sudo yum install mariadb105 -y
```

![Install Software](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0001-installsoftware.png?featherlight=false&width=90pc)

10. Sau khi hoàn tất, chúng ta sẽ kích hoạt các dịch vụ này và định cấu hình để chúng tự động khởi động sau khi hệ thống khởi động lại.

```
sudo systemctl start httpd
sudo systemctl enable httpd
sudo systemctl start php-fpm
sudo systemctl enable php-fpm
```

![Install Software](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0002-installsoftware.png?featherlight=false&width=90pc)

11. Sau đó, chúng tôi sẽ tạo một số permits để truy cập thư mục Apache.

```
sudo usermod -a -G apache ec2-user
sudo chown -R ec2-user:apache /var/www/html
sudo chown -R apache:apache /var/www/html
```

![Install Software](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0003-installsoftware.png?featherlight=false&width=90pc)

#### Gắn EFS shared drive vào máy chủ Web

12. Đầu tiên chúng ta sẽ mở tệp **/etc/fstab** trong trình soạn thảo Nano với quyền người dùng root.

    - Nhập **`sudo nano /etc/fstab`**

    ![Install Software](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0001-mountefs.png?featherlight=false&width=90pc)

13. Nối dòng sau vào cuối tệp sau đó lưu và thoát tệp

```
fs-061c0cc037d521abf.efs.us-east-1.amazonaws.com:/ /var/www/html/ nfs defaults,\_netdev 0 0
```

{{% notice note %}}
Lưu ý: Đảm bảo thay thế **fs-061c0cc037d521abf.efs.us-east-1.amazonaws.com** bằng DNS của thư mục EFS của bạn. Nếu bạn không chắc chắn tìm thấy nó ở đâu, hãy tham khảo nội dung cuối của phần [4.5](http://localhost:1313/vi/4-deployrdsands3/4.5-createefsfilesystem/#dns-name)
{{% /notice %}}

![Install Software](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0002-mountefs.png?featherlight=false&width=90pc)

14. Cuối cùng, chúng ta nhập lệnh sau đây một lần nửa

```
sudo mount -t nfs4 -o nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport fs-061c0cc037d521abf.efs.us-east-1.amazonaws.com:/ /var/www/html/
```

![Install Software](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0003-mountefs.png?featherlight=false&width=90pc)

15. Kiểm tra kết quả, chúng ta thấy ổ đĩa EFS đã gắn vào thành công

    ![Install Software](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0004-mountefs.png?featherlight=false&width=90pc)
