---
title: "Update Database to RDS Instance"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5.5 </b> "
---

#### Update Database to RDS Instance

1. First, we need to go to the **Amazon RDS** interface, access the Database of the application, and copy the **Endpoint** as shown in the image below:

   ![Update Database](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.5-UpdateDBtoRDSInstance/0001-update-db.png?featherlight=false&width=90pc)

2. In the EC2 Setup Server, we will access RDS to update the Database using the following command:

```
mysql -h book-rds-database.corloppcovr8.us-east-1.rds.amazonaws.com -P 3306 -u admin -p
```

{{% notice note %}}
Note: **book-rds-database.corloppcovr8.us-east-1.rds.amazonaws.com** is your **RDS endpoint** that you copied in step 1.
{{% /notice %}}

![Update Database](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.5-UpdateDBtoRDSInstance/0002-update-db.png?featherlight=false&width=90pc)

3. Enter the command to check all existing databases. We can see **e_bookstore** is the database of the application that we created earlier during the RDS Instance setup.

```
show databases;
```

![Update Database](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.5-UpdateDBtoRDSInstance/0003-update-db.png?featherlight=false&width=90pc)

4. Next, we will select this database to work on it by entering the command:

```
USE e_bookstore;
```

5. We will execute SQL statements from the file **CreateDB.sql** located at **/var/www/html/sql/** into the RDS. The **CreateDB.sql** file will create tables, indexes, and procedures.

```
SOURCE /var/www/html/sql/CreateDB.sql
```

![Update Database](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.5-UpdateDBtoRDSInstance/0005-update-db.png?featherlight=false&width=90pc)

6. Proceed to execute SQL statements from the file **insertDB.sql** located at **/var/www/html/sql/**. The **insertDB.sql** file inserts new records into existing tables in the database.

![Update Database](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.5-UpdateDBtoRDSInstance/0006-update-db.png?featherlight=false&width=90pc)

#### Configuring the db_conn.php file

7. In the EC2 Setup Server, we will access the **db_conn.php** file in the Source code downloaded from S3. Navigate to the directory **/var/www/html** and enter:

```
sudo nano db_conn.php
```

![Update Database](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.5-UpdateDBtoRDSInstance/0007-update-db.png?featherlight=false&width=90pc)

8. Edit the values as follows:

- At the variable **sName** with the value **`book-rds-database.corloppcovr8.us-east-1.rds.amazonaws.com`** which is your **RDS endpoint** copied in step 1.
- At the variable **uName** with the value **`admin`** which is the Database login username.
- At the variable **pass** with the value **`12345678`** which is your password.
- At the variable **db_name** with the value **`e_bookstore`** which is the database of the application.

![Update Database](/workshop1-FCJ2024/images/5-SetupEc2ServerAndEFS/5.5-UpdateDBtoRDSInstance/0008-update-db.png?featherlight=false&width=90pc)

Then save and exit the file.
