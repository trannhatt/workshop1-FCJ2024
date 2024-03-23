---
title: "Cập nhật Database vào RDS Instance"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5.5 </b> "
---

#### Cập nhật Database vào RDS Instance

1. Đầu tiên chúng ta phải vào giao diện **Amazon RDS**, truy cập vào Database của ứng dụng và copy **Endpoint** như ảnh

   ![Update Database](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.5-UpdateDBtoRDSInstance/0001-update-db.png?featherlight=false&width=90pc)

2. Trong EC2 Setup Server, chúng ta sẽ truy cập vào RDS để cập nhật Database bằng lệnh sau

```
mysql -h book-rds-database.corloppcovr8.us-east-1.rds.amazonaws.com -P 3306 -u admin -p
```

{{% notice note %}}
Lưu ý: **book-rds-database.corloppcovr8.us-east-1.rds.amazonaws.com** là **RDS endpoint** của bạn đã copy ở bước 1.
{{% /notice %}}

![Update Database](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.5-UpdateDBtoRDSInstance/0002-update-db.png?featherlight=false&width=90pc)

3. Nhập lệnh để kiểm tra tất cả cơ sở dữ liệu đang có, chúng ta thấy có **e_bookstore** là cơ sở dữ liệu của ứng dụng mà chúng ta đã tạo từ trước trong quá trình tao RDS Instance.

```
show databases;
```

![Update Database](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.5-UpdateDBtoRDSInstance/0003-update-db.png?featherlight=false&width=90pc)

4. Tiếp theo, chúng ta sẽ chọn cơ sở dữ liệu này để làm việc trên đó, bằng cách nhập lệnh

```
USE e_bookstore;
```

5. Chúng ta sẽ thực thi các câu lệnh SQL từ tệp **CreateDB.sql** trong đường dẫn **/var/www/html/sql/** vào trong RDS. Tệp **CreateDB.sql** sẽ tạo các bảng, chỉ mục và các thủ tục.

```
SOURCE /var/www/html/sql/CreateDB.sql
```

![Update Database](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.5-UpdateDBtoRDSInstance/0005-update-db.png?featherlight=false&width=90pc)

6. Tiếp tục thực thi các câu lệnh SQL từ tệp **insertDB.sql** trong đường dẫn **/var/www/html/sql/**. Tệp **insertDB.sql** chèn các bản ghi mới vào các bảng đã tồn tại trong cơ sở dữ liệu.

![Update Database](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.5-UpdateDBtoRDSInstance/0006-update-db.png?featherlight=false&width=90pc)

#### Cấu hình tệp db_conn.php

7. Trong EC2 Setup Server, chúng ta sẽ truy cập vào tệp **db_conn.php** trong Source code đã tải về từ S3. Tại thư mục **/var/www/html** nhập

```
sudo nano db_conn.php
```

![Update Database](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.5-UpdateDBtoRDSInstance/0007-update-db.png?featherlight=false&width=90pc)

8. Chỉnh sửa các giá trị như sau,

   - Tại biến **sName** mang giá trị **`book-rds-database.corloppcovr8.us-east-1.rds.amazonaws.com`** là **RDS endpoint** của bạn đã copy ở bước 1.
   - Tại biến **uName** mang giá trị **`admin`** là tên đăng nhập vào Database.
   - Tại biến **pass** mang giá trị **`12345678`** là mật khẩu của bạn.
   - Tại biến **db_name** mang giá trị **`e_bookstore`** là cơ sở dữ liệu của ứng dụng.

![Update Database](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.5-UpdateDBtoRDSInstance/0008-update-db.png?featherlight=false&width=90pc)

Sau đó lưu và thoát tệp.
