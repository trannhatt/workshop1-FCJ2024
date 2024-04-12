<h1 align="center">
  <img alt="pipeline diagram" src="arch.png" width="70%"/><br/>
BUILD A THREE-TIER ARCHITECTURE FOR DEPLOY LAMP STACK APPLICATION ON AWS
</h1>
<p align="center"><br/>Focusing on the application of <b>DevOps</b> tools.</p>

<p align="center"><a href="https://aws.amazon.com/" target="_blank"><img src="https://img.shields.io/badge/-Amazon%20AWS-FF9900?logo=amazon-aws&logoColor=white" alt="AWS" /></a></p>

<p align="center">
    <b>The language used is</b>
    <a href="README.md">English</a>
</p>

# Workshop Overview 

In this workshop, you will learn about building a three-tier architecture with high availability and fault tolerance to deploy a **LAMP STACK** application on **AWS**. We will leverage various **AWS** services using the **management console**.

# Link Gitpage: 

https://trannhatt.github.io/workshop1-FCJ2024/

#### Description

1. Within the **VPC**, there are both public and private subnets distributed across 2 availability zones.
2. An **Internet Gateway** is used to allow communication between instances within the VPC and the Internet.
3. We utilize **2 Availability Zones** to ensure high availability and fault tolerance.
4. Other resources such as **Nat Gateway**, **Bastion Host**, and **Application Load Balancer** reside in **Public Subnets**.
5. Web servers and database servers are placed in **Private Subnets** to protect them.
6. **Nat Gateway** enables instances in private app subnets and private data subnets to access the internet.
7. We employ **MYSQL database** and **EC2 Instances** to host the website.
8. **Application Load Balancer** is used to distribute web traffic across **Auto Scaling Groups** of EC2 instances in multiple AZs.
9. **Auto Scaling Group** ensures the website is highly available, scalable, fault-tolerant, and flexible.
10. **AWS S3** is utilized for storing web application source code, and **IAM Role** is created to grant EC2 permission to download the source code from AWS S3.
11. We will deploy our website on one EC2 instance first, then use this instance to create an **AMI**.
12. Utilize **AWS WAF (Web Application Firewall)** to protect the application, and use **CloudFront** service to enhance performance and reduce latency when users access the website.
13. **Route 53** can be used to register the domain name and create a record set.

#### Availability Zone

An **Availability Zone** (AZ) is a subset of data centers within a Region and is defined based on geographical location. Within an AZ, there can be one or more subnets, but a subnet can only reside in a single AZ and cannot span across multiple AZs.

#### Subnet

A **Subnet** is a segment of the IP address range that you use when you create an Amazon VPC, providing a direct network segment for AWS resources to operate within it, such as Amazon EC2, Amazon RDS, etc. Subnets are also defined by a CIDR block and must be within the VPC's CIDR.

Subnets are categorized as **Public**, **Private**, or **VPN-only**.

- **Public subnets** have a route table (discussed later) that routes traffic within the subnet to the VPC IGW (also discussed later).
- **Private subnets** lack this route table for routing traffic to the VPC IGW.
- **VPN-only subnets** are those that have a route table routing traffic to the VPG of Amazon VPC (discussed later).

Regardless of the subnet type, the internal IP address range of the subnet is always private (meaning it cannot be directly connected to from outside the Internet).

#### Route Table

A **Route Table**, also known as a routing table, provides routing instructions and is assigned to subnets.
For example, when you create a VPC with a 10.10.0.0/16 network class and 2 subnets 10.10.1.0/24,10.10.2.0/24 then each subnets will be assigned 1 default route table by default.
Inside the route table will have route entry **destination**:10.10.0.0/16 **target**:local. This route entry shows that the resources created within the same VPC can connect to each other.

#### Internet Gateway

An **Internet Gateway (IGW)** is an Amazon VPC component that enables AWS resources within the VPC, specifically EC2, to communicate with the Internet. The IGW can scale horizontally, ensuring redundancy and high availability. It acts as a target in the Amazon VPC's route table, allowing traffic to be routed out to the Internet by translating the EC2's network address into the assigned Public IP address.

#### NAT Gateway

By default, EC2s running in a Private subnet do not have the ability to communicate with the Internet through the **IGW**. Hence the problem arises when that EC2 needs to access the Internet for applying security updates, downloading patches, or updating application software.
Capturing that need, AWS provides 2 methods to allow EC2s inside Private subnets to access the Internet, that is **NAT Instance** and **NAT Gateway**. For ordinary cases, we should use **NAT Gateway** instead of **NAT Instance**. **NAT Gateway** ensures higher availability and higher bandwidth, while requiring less administrative effort than **NAT Instance**.

#### Load Balancer

A **Load Balancer** is a tool that can distribute exchanged data traffic to AWS resources (specifically in this lab are **EC2 Instances**) within the **Target Group**.

#### Target Group

A **Target Group** is a group of AWS resource components that will receive distributed data traffic transmitted by the **Load Balancer**.

#### Amazon CloudFront

**Amazon CloudFront** is a **content delivery network (CDN)** service built to ensure high performance, security for users.

#### Amazon RDS

**Amazon RDS** is a managed database service that enables you to automate provisioning, operating, and scaling a relational database on AWS's cloud computing platform.

#### AWS WAF (Web Application Firewall)

**AWS WAF (Web Application Firewall)** is a network security service that helps protect your web applications from common web exploits, safeguard important data, and ensure application availability.






