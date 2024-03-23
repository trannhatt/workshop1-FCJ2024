---
title: "Configure the EC2 Setup Server"
date: "2024-03-23"
weight: 3
chapter: false
pre: " <b> 5.3 </b> "
---

#### Access the EC2 Setup Server through Bastion Host

1. In the **EC2 instance** interface, select **Bastion Host** and then click **Connect**.

   - Choose **EC2 Instance Connect**.
   - Then click **Connect**.

   ![Bastion to EC2](/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0001-bastiontoserver.png?featherlight=false&width=90pc)

2. You'll see that you have successfully accessed the Bastion Host.

   ![Bastion to EC2](/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0002-bastiontoserver.png?featherlight=false&width=90pc)

3. Type **`ping google.com`** to check the internet connection, the result is as shown in the images below.

   ![Bastion to EC2](/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0003-bastiontoserver.png?featherlight=false&width=90pc)

   ![Bastion to EC2](/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0004-bastiontoserver.png?featherlight=false&width=90pc)

4. Type **`sudo nano ssh-key.pem`** to create an SSH key to access the EC2 Setup Server.

   ![Bastion to EC2](/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0005-bastiontoserver.png?featherlight=false&width=90pc)

5. The content of the **ssh-key.pem** file will be in the key pair file that we selected while creating the EC2 Setup Server. We'll copy it here, then save and exit the file.

   ![Bastion to EC2](/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0006-bastiontoserver.png?featherlight=false&width=90pc)

6. Type **`sudo chmod 400 ssh-key.pem`** to allow reading the contents of this file, but not writing to it or executing it.

   ![Bastion to EC2](/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0008-bastiontoserver.png?featherlight=false&width=90pc)

7. Finally, type **`sudo ssh -i "ssh-key.pem" ec2-user@10.0.3.239`** to access the EC2 Setup Server.

{{% notice note %}}
Note: **10.0.3.239** is the private IPv4 address of the EC2 Setup Server. So, make sure to replace it with your server's IP address!
{{% /notice %}}

![Bastion to EC2](/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0009-bastiontoserver.png?featherlight=false&width=90pc)

8. Type **`ping google.com`** again to check the internet connection, the result is as shown below.

   ![Bastion to EC2](/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/00010-bastiontoserver.png?featherlight=false&width=90pc)

#### Update Version and Install Necessary Software on EC2 Setup Server

9. Next, we will proceed to update the version and install essential software, including Apache, PHP, and MySQL.

```
sudo yum update -y
sudo yum install php -y
sudo yum install php-mysqli -y
sudo yum install mariadb105 -y
```

![Install Software](/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0001-installsoftware.png?featherlight=false&width=90pc)

10. Once completed, we will activate these services and configure them to start automatically after system reboot.

```
sudo systemctl start httpd
sudo systemctl enable httpd
sudo systemctl start php-fpm
sudo systemctl enable php-fpm
```

![Install Software](/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0002-installsoftware.png?featherlight=false&width=90pc)

11. Then, we will create some permissions to access the Apache directory.

```
sudo usermod -a -G apache ec2-user
sudo chown -R ec2-user:apache /var/www/html
sudo chown -R apache:apache /var/www/html
```

![Install Software](/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0003-installsoftware.png?featherlight=false&width=90pc)

#### Attach EFS shared drive to the Web server

12. First, we will open the file **/etc/fstab** in the Nano editor with root user privileges.

    - Enter **`sudo nano /etc/fstab`**

    ![Install Software](/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0001-mountefs.png?featherlight=false&width=90pc)

13. Append the following line to the end of the file, then save and exit the file.

```
fs-061c0cc037d521abf.efs.us-east-1.amazonaws.com:/ /var/www/html/ nfs defaults,\_netdev 0 0
```

{{% notice note %}}
Note: Make sure to replace **fs-061c0cc037d521abf.efs.us-east-1.amazonaws.com** with the DNS of your EFS directory. If you're unsure where to find it, refer to the content at the end of section [4.5](http://localhost:1313/vi/4-deployrdsands3/4.5-createefsfilesystem/#dns-name).
{{% /notice %}}

![Install Software](/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0002-mountefs.png?featherlight=false&width=90pc)

14. Finally, we enter the following command once again:

```
sudo mount -t nfs4 -o nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport fs-061c0cc037d521abf.efs.us-east-1.amazonaws.com:/ /var/www/html/
```

![Install Software](/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0003-mountefs.png?featherlight=false&width=90pc)

15. Checking the result, we can see that the EFS drive has been successfully mounted.

    ![Install Software](/images/5-SetupEc2ServerAndEFS/5.3-ConfigureEC2/0004-mountefs.png?featherlight=false&width=90pc)
