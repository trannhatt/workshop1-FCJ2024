---
title: "Deploy Application"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

#### Deploy Application

In this section, we will create an Application Load Balancer to distribute traffic and route requests from users to EC2 application servers. Creating an AMI and Launch Template simplifies the deployment process, while the Auto Scaling Group automatically scales up or down the number of EC2 instances based on the load. Finally, we will create a CloudFront distribution and Web ACL to enhance the security and performance of the application.

#### Contents

1. [Create Target Group](6.1-createtargetgroup/)
2. [Create Application Load Balancer](6.2-createalb/)
3. [Create AMI](6.3-createami/)
4. [Create Launch Template](6.4-createlaunchtemp/)
5. [Create Auto Scaling Group](6.5-createasg/)
6. [Create CloudFront and Web ACL](5.5-updatedbtordsinstance/)
