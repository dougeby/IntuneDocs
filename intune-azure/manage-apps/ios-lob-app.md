---
# required metadata

title: How to add iOS line-of-business (LOB) apps to Intune | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn about adding iOS line-of-business apps to Intune."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/30/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:
---

# How to add iOS line-of-business (LOB) apps to Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## Step 1 - Specify the software setup file

1. Sign into the Azure portal.
2. Choose **More Services** > **Other** > **Intune**.
3. On the Intune blade, choose **Manage apps**.
4. In the **Mobile apps** workload, choose Manage > **Apps**.
5. Above the list of apps, choose **Add**.
6. In the **Add App** blade, choose **Software Setup File**.
7. In the **Select setup file** blade, click the browse button and browse to the iOS app setup file (with the extension .ipa), then click **OK**.

## Step 2 - Configure app information

1. In the **Edit App** blade, configure the following information. Once you are done, click **Add**. Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:
	- **App Name** - Enter the name of the app as it will be displayed in the company portal. Make sure all app names that you use are unique. If the same app name exists twice, only one of the apps will be displayed to users in the company portal.
	- **App Description** - Enter a description for the app. This will be displayed to users in the company portal.
	- **Publisher** - Enter the name of the publisher of the app.
	- **Applicable Device Type** - Select whether this app can be installed on iPads, iPhones, or compatible iPods.
	- **Minimum Operating System** -
	- **Category** (optional) - Select one of the built-in app categories. This will make it easier for users to find the app when they browse the company portal.
	- **Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.
	- **Information URL** - Optionally, enter the URL of a website that contains information about this app. The URL will be displayed to users in the company portal.
	- **Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app. The URL will be displayed to users in the company portal.
	- **Developer** - Optionally, enter the name of the app developer.
	- **Owner** - Optionally, enter the name of the app owner.
	- **Notes** - Enter any notes you would like to associate with this app.
	- **Upload Icon** - Upload an icon that will be associated with the app. This is the icon that will be displayed with the app when users browse the company portal.
2. When you are done, on the **Add App** blade, choose **Save**.

The app you have created will be displayed in the apps list where you can assign it to the groups you choose. For help, see [How to assign apps to groups](/intune-azure/manage-apps/deploy-apps).