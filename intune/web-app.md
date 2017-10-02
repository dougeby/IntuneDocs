---
# required metadata

title: How to add web apps to IntunetitleSuffix: "Azure portal"
description: Learn about adding web apps to Intune."
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# How to add web apps to Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Manage apps**.
4. In the **Mobile apps** workload, choose **Manage** > **Apps**.
5. Above the list of apps, choose **Add**.
6. In the **Add App** blade, choose **App Information**.
7. In the **Edit App** blade, configure the following information. Once you are done, click **Add**:
	- **App URL** - Enter the URL of the web site that hosts the app you want to assign.
	- **App Name** - Enter the name of the app as it will be displayed in the company portal.
	- **App Description** - Enter a description for the app. This will be displayed to end users in the company portal.
	- **Publisher** - Enter the name of the publisher of this app.
	- **Category (optional)** - Select one or more of the built-in app categories, or a category you created. This will make it easier for users to find the app when they browse the company portal.
	- **Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.
	- **Require a managed browser to open this link** - When you assign a link to a website or web app to users, they will be able to open it only in the Intune managed browser. This browser must be installed on their device.
	- **Upload Icon** - Upload an icon that will be associated with the app. This is the icon that will be displayed with the app when users browse the company portal.
8. When you are done, on the **Add App** blade, choose **Save**.

The app you have created will be displayed in the apps list where you can assign it to the groups you choose. For help, see [How to assign apps to groups](apps-deploy.md).