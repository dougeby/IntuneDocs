---
# required metadata

title: How to add Windows store apps to Microsoft Intune
titleSuffix:
description: Learn about adding Windows store apps to Microsoft Intune.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# How to add Windows store apps to Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Before you can assign, monitor, configure, or protect apps, you must add them to Intune. The following steps allow you to add a Windows store app to Microsoft Intune.

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** pane, choose **Mobile apps**.
4. In the **Mobile apps** workload, choose **Manage** > **Apps**.
5. Above the list of apps, choose **Add**.
6. In the **Add app** pane, choose an **App type** of **Windows** and choose **App information**.
7. In the **App information** pane, configure the following information. Once you are done, click **OK**. Depending on the app you have chosen, some of the values in this pane might have been automatically filled-in:
	- **Name** - Enter the name of the app as it will be displayed in the company portal. Make sure all app names that you use are unique. If the same app name exists twice, only one of the apps will be displayed to users in the company portal.
	- **Description** - Enter a description for the app to be displayed to users in the company portal.
	- **Publisher** - Enter the name of the publisher of the app.
	- **Appstore URL** - Enter the app store URL of the app you want to create.
	- **Category (optional)** - Select one or more of the built-in app categories, or a category you created, which makes it easier for users to find the app when they browse the company portal.
	- **Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.
	- **Information URL** - Optionally, enter the URL of a website that contains information about this app. The URL will be displayed to users in the company portal.
	- **Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app. The URL will be displayed to users in the company portal.
	- **Developer** - Optionally, enter the name of the app developer.
	- **Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.
	- **Notes** - Enter any notes you would like to associate with this app.
	- **Logo** - Upload an icon to be associated with the app. This icon that is displayed with the app when users browse the company portal.
8. When you are done, on the **Add app** pane, choose **Add**.

The app you have created will be displayed in the apps list where you can assign it to the groups you choose. 

## Next steps

- [How to assign apps to groups](apps-deploy.md)