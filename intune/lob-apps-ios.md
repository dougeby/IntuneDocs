---
# required metadata

title: How to add iOS line-of-business apps to Intune
titlesuffix: "Azure portal"
description: Learn about adding iOS line-of-business apps to Intune."
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/3/2017
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
ms.custom: intune-azure
---

# How to add iOS line-of-business (LOB) apps to Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use the information in this topic to help you add iOS line-of-business apps to Intune.

>[!NOTE]
>While users of iOS devices can remove some of the built-in iOS apps like Stocks, and Maps, you cannot use Intune to redeploy those apps. If end users delete these apps, they must go to the app store, and manually re install them.

## Step 1 - Specify the software setup file

1. [!INCLUDE[shared-proc-openintuneazure](./includes/shared-proc-openintuneazure.md)]
3. On the **Intune** blade, choose **Manage apps**.
4. In the **Mobile apps** workload, choose **Manage** > **Apps**.
5. Above the list of apps, choose **Add**.
6. In the **Add App** blade, choose **Line-of-business app**.

## Step 2 - Configure the app package file

1. On the **Add app** blade, choose **App package** file.
2. On the **App package** file blade, choose the browse button, and select an iOS installation file with the extension **.ipa**.
3. When you are finished, choose **OK**.


## Step 3 - Configure app information

1. On the **Add app** blade, choose **App package** file.
2. On the **App information** blade, add the details for your app. Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:
	- **Name** - Enter the name of the app to be displayed in the company portal. Make sure all app names that you use are unique. If the same app name exists twice, only one of the apps will be displayed to users in the company portal.
	- **Description** - Enter a description for the app to be displayed to users in the company portal.
	- **Publisher** - Enter the name of the publisher of the app.
	- **Minimum Operating System** - From the list, choose the minimum operating system version on which the app can be installed. If you assign the app to a device with an earlier operating system, it will not be installed.
	- **Category** - Select one or more of the built-in app categories, or a category you created. This makes it easier for users to find the app when they browse the company portal.
	- **Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.
	- **Information URL** - Optionally, enter the URL of a website that contains information about this app. The URL is displayed to users in the company portal.
	- **Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app. The URL is displayed to users in the company portal.
	- **Developer** - Optionally, enter the name of the app developer.
	- **Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.
	- **Notes** - Enter any notes you would like to associate with this app.
	- **Logo** - Upload an icon that is associated with the app. This is the icon that is displayed with the app when users browse the company portal.
3. When you are finished, choose **OK**.

## Step 4 - Finish up

1. On the **Add app** blade, verify that the details for your app is correct.
2. Choose **Add**, to upload the app to Intune.

The app you have created appears in the apps list where you can assign it to the groups you choose. For help, see [How to assign apps to groups](apps-deploy.md).

## Step 5 - Update a line-of-business app

[!INCLUDE[shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

## Next steps

The app you have created is displayed in the apps list. You can now assign it to the groups you choose. For help, see [How to assign apps to groups](apps-deploy.md).

Learn more about the ways in which you can monitor the properties and assignment of your app. For more information, see [How to monitor app information and assignments](apps-monitor.md).

Learn more about the context of your app in Intune. For more information, see [Overview of device and app lifecycles](introduction-device-app-lifecycles.md)
