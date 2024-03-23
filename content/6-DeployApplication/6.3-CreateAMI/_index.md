---
title: "Create AMI"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 6.3 </b> "
---

#### Create AMI

1. In the **EC2** dashboard,

   - Select **Instances**
   - Choose **lamp-stack-setup-server**
   - Click on the **Actions** tab, select **Image and templates**
   - Choose **Create image**

   ![Create AMI](/images/6-DeployApplication/6.3-Create%20AMI/0001-createami.png?featherlight=false&width=90pc)

2. In the **Create image** interface,

   - In the **Image name** field, enter **`Bookstore AMI`**
   - In the **Image description** field, enter **`Bookstore AMI`**

   ![Create AMI](/images/6-DeployApplication/6.3-Create%20AMI/0002-createami.png?featherlight=false&width=90pc)

   Then,

   - In the **Tags - optional** section:
     - Check **Tag image and snapshots together**
     - Enter **`Name`** in the **Key** field
     - Optionally, enter **`Bookstore AMI`** in the **Value** field

   ![Create AMI](/images/6-DeployApplication/6.3-Create%20AMI/0003-createami.png?featherlight=false&width=90pc)

3. Finally, click **Create** to complete the AMI creation process.

   ![Create AMI](/images/6-DeployApplication/6.3-Create%20AMI/0004-createami.png?featherlight=false&width=90pc)

4. You have successfully created the AMI.

   ![Create AMI](/images/6-DeployApplication/6.3-Create%20AMI/0005-createami.png?featherlight=false&width=90pc)
