---
# required metadata

title: How to add Windows line-of-business apps to Intune 
titlesuffix: "Azure portal"
description: Learn about adding Windows line-of-business apps to Intune."
keywords:
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 02/16/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# How to add Windows line-of-business (LOB) apps to Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A line-of-business (LOB) app is one that you add from an app installation file. These types of apps are typically written in-house. The following steps provide guidance to help you add a Windows LOB app to Microsoft Intune.

## Step 1 - Specify the software setup file

1. Sign in to the Azure portal.
2. Choose **More Services** > **Monitoring + Management** + **Intune**.
3. On the **Intune** blade, choose **Manage apps**.
4. In the **Mobile apps** workload, choose **Manage** > **Apps**.
5. Above the list of apps, choose **Add**.
6. In the **Add App** blade, choose **Line-of-business app**.

## Step 2 - Configure the app package file

1. On the **Add app** blade, choose **App package** file.
2. On the **App package** file blade, choose the browse button, and select a Windows installation file with the extension **.msi**, **.appx**, or **.appxbundle**.
3. When you are finished, choose **OK**.


## Step 3 - Configure app information

1. On the **Add app** blade, choose **App package** file.
2. On the **App information** blade, configure the following information (some of the values in this blade might be automatically filled-in):
	- **Name** - Enter the name of the app as it is displayed in the company portal. Make sure all app names that you use are unique. If the same app name exists twice, only one of the apps is displayed to users in the company portal.
	- **Description** - Enter a description for the app. The description is displayed to users in the company portal.
	- **Publisher** - Enter the name of the publisher of the app.
	- **Category** - Select one or more of the built-in app categories, or a category you created. Categorizing apps makes it easier for users to find the app when they browse the company portal.
	- **Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.
	- **Information URL** - Optionally, enter the URL of a website that contains information about the app. The URL is displayed to users in the company portal.
	- **Privacy URL** - Optionally, enter the URL of a website that contains privacy information for the app. The URL is displayed to users in the company portal.
	- **Command-line arguments** - Optionally, enter any command-line arguments that you want to apply to the .msi file when it runs, like **/q**.
	- **Developer** - Optionally, enter the name of the app developer.
	- **Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.
	- **Notes** - Enter any notes you would like to associate with this app.
	- **Logo** - Upload an icon that is associated with the app. The icon is displayed with the app when users browse the company portal.
3. When you are finished, choose **OK**.

## Step 4 - Finish up

1. On the **Add app** blade, verify you configured the app information correctly.
2. Choose **Add**, to upload the app to Intune.

## Step 5 - Update a line-of-business app

[!INCLUDE[shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

## Configuring a self-updating mobile MSI app to ignore the version check process

You can configure a known self-updating mobile MSI app to ignore the version check process. Some MSI installer based apps are automatically updated by the app developer. For these automatically updated MSI apps, you can configure the **Ignore app version** setting in the **App information** blade. When this setting is switched to **Yes**, Microsoft Intune will not enforce the app version installed on the Windows client. This capability is useful to avoid getting into a race condition. For instance, this type of race condition could occur when the app being automatically updated by the app developer is also being update by Intune. Both could try to enforce a version of the app on a Windows client, which could create a conflict.

## Next steps

The app you have created is displayed in the apps list. You can now assign it to the groups you choose. For help, see [How to assign apps to groups](apps-deploy.md).

Learn more about the ways in which you can monitor the properties and assignment of your app. For more information, see [How to monitor app information and assignments](apps-monitor.md).

Learn more about the context of your app in Intune. For more information, see [Overview of device and app lifecycles](introduction-device-app-lifecycles.md)