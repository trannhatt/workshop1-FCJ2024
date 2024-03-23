---
title: "Build a Three-Tier AWS Network VPC"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

#### Build a Three-Tier AWS Network VPC

In this section, we will build a Three-Tier AWS Network VPC as follows:

- The **VPC** will be created in 2 availability zones with 1 public subnet and 2 private subnets in each AZ.
- 1 **Internet Gateway** will be used to allow communication between instances within the VPC and the Internet.
- We will utilize 2 **Availability Zones** to ensure high availability and fault tolerance.
- Resources such as Nat Gateway, Bastion Host, and Application Load Balancer will be deployed in **Public subnets**.
- We will place web servers and database servers in the **Private Subnets** to protect them.
- The **Public Route Table** will be associated with the public subnets and route traffic to the Internet through the Internet Gateway.
- The **Main Route Table** will be associated with the private subnets.

#### Contents

1. [Create and Configure VPC](2.1-vpc/)
2. [Create and Attach Internet Gateway (IGW) to VPC](2.2-internetgateway/)
3. [Create and Configure Subnets](2.3-subnet/)
4. [Create and Configure Route Tables](2.4-routetable/)
