---
# required metadata

title: How to add Android store apps to Intune
titleSuffix: "Azure portal"
description: Learn about adding Android store apps to Intune."
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/13/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# How to add Android store apps to Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Before you assign an app to a device or a group of users, you must first add the app to Microsoft Intune. The following steps allow you to add an Android store app to Intune from the Azure portal.

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Microsoft Intune** blade, choose **Mobile apps**.
4. In the **Mobile apps** workload, choose **Apps** under the **Manage** section.
5. Above the list of apps, choose **Add**.
6. On the **Add App** blade, select **Android** under the available **Store app** types.
7. Select **Configure** to configure the app information the following information:  Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:
	- **Name** - Enter the name of the app as it will be displayed in the company portal. Make sure all app names that you use are unique. If the same app name exists twice, only one of the apps will be displayed to users in the company portal.
	- **Description** - Enter a description for the app. This description will be displayed to users in the company portal.
	- **Publisher** - Enter the name of the publisher of the app.
	- **Appstore URL** - Enter the app store URL of the app you want to create.
	- **Minimum operating system** - From the list, choose the minimum operating system version on which the app can be installed. If you assign the app to a device with an earlier operating system, it will not be installed.
	- **Category** (optional) - Select one or more of the built-in app categories, or a category you created. This will make it easier for users to find the app when they browse the company portal.
	- **Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.
	- **Information URL** (optional) - Enter the URL of a website that contains information about this app. The URL will be displayed to users in the company portal.
	- **Privacy URL** (optional) - Enter the URL of a website that contains privacy information for this app. The URL will be displayed to users in the company portal.
	- **Developer** (optional) - Enter the name of the app developer.
	- **Owner** (optional) - Enter a name for the owner of this app, for example, **HR department**.
	- **Notes** (optional) - Enter any notes you would like to associate with this app.
	- **Logo** (optional) - Upload an icon that will be associated with the app. This icon is displayed with the app when users browse the company portal.
8. Click **OK** when you have completed setting the app information.
9. Click **Add** to add the app.

The app you've created is displayed in the apps list where you can assign it to the groups you choose. 

##Next steps

- [How to assign apps to groups](apps-deploy.md)