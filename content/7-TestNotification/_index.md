---
title: "Check Notifications"
date: "`r Sys.Date()`"
weight: 7
chapter: false
pre: " <b> 7. </b> "
---

#### Check Notifications

Let's assume an EC2 Web Server encounters an issue by being terminated, and let's observe receiving the notification about this incident via the provided email.

1. In the **EC2** dashboard:

   - Select **Instances**
   - Choose a Web Server instance **bookstore-asg**
   - From the **Instance state** dropdown, select **Terminate instance**

   ![Test Notification](/images/7-TestNotification/0001-testnotifi.png?featherlight=false&width=90pc)

2. In the **Terminate instance?** prompt, select **Terminate**

   ![Test Notification](/images/7-TestNotification/0002-testnotifi.png?featherlight=false&width=90pc)

3. Wait for a moment, then check the registered email. You will find an email sent with the following content:

   ![Test Notification](/images/7-TestNotification/0003-testnotifi.png?featherlight=false&width=90pc)
