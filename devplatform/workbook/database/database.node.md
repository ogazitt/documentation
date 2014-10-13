---
layout: default-devplatform
title: "HP Helion Development Platform Workbook Node Database Sample"
permalink: /helion/devplatform/workbook/database/node/
product: devplatform

---
#Database Node Sample
This is the **second** sample in the series; if you have not already examined the [HelloWorld](/helion/devplatform/workbook/helloworld/node/) sample, please do that one first.

This is a simple Node.js app that uses MySQL. 
# Prerequisites

1. You must have a Stackato instance available. 
2. The  [Stackato command-line interface (CLI)] must be installed. 
3. You must have access to the web-based Administration console.

**MySQL**

If the MySQL service is not enabled on your cluster, or if you are not sure, follow these steps:

- Go to the Administrative console (e.g. *https://api.15.126.212.172.xip.io*, substitute your own instance's link)
- On the **Admin** tab, click **Cluster**.
- Click the **Settings** icon (a gear icon in the upper right corner)
- The **MySQL** check box should be checked. If it is not, check it.
- Click **Save**.

##Download the Application Files
[Download the Node files](https://gitlab.gozer.hpcloud.net/developer-experience/mysql-node/) from the code repository.

##Deploy the Application

To deploy the application, make sure you are logged in successfully for your desired target environment; for example, *https://api.yourapp.com*.

1. Open the  [Stackato command-line interface (CLI)].

2. *cd* into the app's root directory.
3. Execute `stackato push -n` 

##Run the Application

1. Open the Management Console. This is the web-based administrative interface.
2. Click **Applications**.
3. If the file push was successful, you should see the new app in the list of available applications. 
4. The status of the application should be **Online**. Click the name of the application to launch it. 
5. In the upper right-hand corner, click **View App**.
6. The result should be a page displaying some text after the app has connected the database and executed the query. 



[Exit Samples](/helion/devplatform/) | [Previous Sample](/helion/devplatform/workbook/helloworld/node/) | [Next Sample](/helion/devplatform/workbook/messaging/node/)