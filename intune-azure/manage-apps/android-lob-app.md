---
# required metadata

title: How to add Android line-of-business apps to IntunetitleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn about adding Android line-of-business apps to Intune."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# How to add Android line-of-business (LOB) apps to Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## Step 1 - Specify the software setup file

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Manage apps**.
4. In the **Mobile apps** workload, choose **Manage** > **Apps**.
5. Above the list of apps, choose **Add**.
6. In the **Add App** blade, choose **Software Setup File**.
In the **Select setup file** blade, click the browse button and browse to the Android app setup file (with the extension .apk), then click **OK**.

## Step 2 - Configure app information

1. In the **Add App** blade, choose **App Information**.
2. In the **Edit App** blade, configure the following information. Once you are done, click **Add**. Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:
	- **App Name** - Enter the name of the app as it will be displayed in the company portal. Make sure all app names that you use are unique. If the same app name exists twice, only one of the apps will be displayed to users in the company portal.
	- **App Description** - Enter a description for the app. This will be displayed to users in the company portal.
	- **Publisher** - Enter the name of the publisher of the app.
	- **Minimum Operating System** - From the list, choose the minimum operating system version on which the app can be installed. If you assign the app to a device with an earlier operating system, it will not be installed.
	- **Category (optional)** - Select one or more of the built-in app categories, or a category you created. This will make it easier for users to find the app when they browse the company portal.
	- **Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.
	- **Information URL** - Optionally, enter the URL of a website that contains information about this app. The URL will be displayed to users in the company portal.
	- **Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app. The URL will be displayed to users in the company portal.
	- **Developer** - Optionally, enter the name of the app developer.
	- **Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.
	- **Notes** - Enter any notes you would like to associate with this app.
	- **Upload Icon** - Upload an icon that will be associated with the app. This is the icon that will be displayed with the app when users browse the company portal.
3. When you are done, on the **Add App** blade, choose **Save**.

The app you have created will be displayed in the apps list where you can assign it to the groups you choose. For help, see [How to assign apps to groups](/intune-azure/manage-apps/deploy-apps).
