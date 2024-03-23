---
title: "Create CloudFront and Web ACL"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 6.6 </b> "
---

#### Create CloudFront

1. Click on the search bar

   - Type **`cloudfront`**
   - Under **Services**, select **CloudFront**

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0001-createcloudfront.png?featherlight=false&width=90pc)

2. In the **CloudFront** interface

   - Click **Create a CloudFront distribution**

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0002-createcloudfront.png?featherlight=false&width=90pc)

3. In the **Origin** section

   - Under **Origin domain**, select **lamp-stack-alb-541405871.us-east-1.elb.amazonaws.com**
   - Under **Protocol**, select **HTTP Only**

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0003-createcloudfront.png?featherlight=false&width=90pc)

   - Leave other fields as default

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0004-createcloudfront.png?featherlight=false&width=90pc)

4. In the **Default cache behavior** section

   - Under **Compress objects automatically**, select **Yes**
   - Under **Viewer protocol policy**, select **HTTP and HTTPS**
   - Under **Allowed HTTP methods**, select **GET, HEAD, OPTIONS, PUT, POST, PATCH, DELETE**

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0005-createcloudfront.png?featherlight=false&width=90pc)

   - Under **Cache key and origin requests**, select **Cache policy and origin request policy (recommended)**
   - Leave other fields as default

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0006-createcloudfront.png?featherlight=false&width=90pc)

   - Leave other fields as default
   - Click **Create distribution** to finish creating the CloudFront Distribution

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0007-createcloudfront.png?featherlight=false&width=90pc)

5. CloudFront Distribution creation is successful.

   - Copy the content under **Distribution domain name** and paste it into your browser.

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0008-createcloudfront.png?featherlight=false&width=90pc)

   - The image below shows the Web application running with the new domain from CloudFront.

   ![Create CloudFront](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0009-createcloudfront.png?featherlight=false&width=90pc)

#### Create Web ACL

6. Click on the search bar

   - Type **`waf`**
   - Under **Services**, select **WAF & Shield**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0001-createwaf.png?featherlight=false&width=90pc)

7. In the **WAF & Shield** interface

   - Click **Getting started**
   - Click **Create web ACL**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0002-createwaf.png?featherlight=false&width=90pc)

8. In the **Describe web ACL and associate it to AWS resources** section

   - Under **Resource type**, select **Amazon CloudFront distributions**
   - Under **Name**, enter **`bookstore-app`**
   - Under **Description - optional**, enter **`protect my application`**
   - Under **CloudWatch metric name**, enter **`bookstore-app`**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0003-createwaf.png?featherlight=false&width=90pc)

   - Under **Associated AWS resources - optional**, click **Add AWS resources**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0004-createwaf.png?featherlight=false&width=90pc)

   - Under **Resource type**, select **CloudFront Distribution** and select the resource created in the previous step **E2H26TUZ72XRKT - d22fsOdgzskx5x.cloudfront.net**
   - Click **Add**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0005-createwaf.png?featherlight=false&width=90pc)

   - Click **Next** to proceed

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0006-createwaf.png?featherlight=false&width=90pc)

9. In the **Add rules and rule groups** section

   - Under **Rules**, click **Add rules** and select **Add managed rule groups**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0007-createwaf.png?featherlight=false&width=90pc)

   - Select **AWS managed rule groups**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0008-createwaf.png?featherlight=false&width=90pc)

   Under **Free rule groups**, select **Add to web ACL** for the following sections:

   - **Amazon IP reputation list**
   - **Anonymous IP list**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0009-createwaf.png?featherlight=false&width=90pc)

   - **SQL database**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0010-createwaf.png?featherlight=false&width=90pc)

   - Click **Add rule**

   ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0011-createwaf.png?featherlight=false&width=90pc)

10. Leave the remaining settings as default, then select **Create web ACL** to complete the creation of the Web ACL.

    ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0014-createwaf.png?featherlight=false&width=90pc)

11. We have successfully created the Web ACL.

    ![Create WAF](/workshop1-FCJ2024/images/6-DeployApplication/6.6-CreateCloudFrontandWAF/0015-createwaf.png?featherlight=false&width=90pc)
