---
title: "Setup and Configure Servers"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

#### Setup and Configure Servers

In this section, we will proceed with the process of setting up and configuring servers. Firstly, we will create a **Bastion Host** in the Public Subnet, allowing secure access to the application servers in the Private Subnet. Next, an **EC2 Setup Server** will be created in the Private Subnet to prepare for the application deployment. Once configured, we will download source code from an **S3 Bucket** onto the EC2 Setup Server and update the database into the **RDS Instance**.

#### Contents

1. [Create Bastion Host in Public Subnet](5.1-CreateBastionHost/)
2. [Create EC2 Setup Server in Private Subnet](5.2-CreateEC2SetupServer/)
3. [Configure EC2 Setup Server](5.3-ConfigureEC2/)
4. [Download Files from S3 onto EC2 Setup Server](5.4-DownloadSourceCodeS3/)
5. [Update Database into RDS Instance](5.5-UpdateDBtoRDSInstance/)
