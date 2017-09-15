---
# required metadata

title: How to add iOS store apps to Intune 
titlesuffix: "Azure portal"
description: Learn about adding iOS store apps to Intune."
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/11/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# How to add iOS store apps to Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Use the information in this topic to help you add iOS store apps to Intune.

>[!NOTE]
>While users of iOS devices can remove some of the built-in iOS apps like Stocks, and Maps, you cannot use Intune to redeploy those apps. If end users delete these apps, they must go to the app store, and manually re install them.

## Before you start

You can only assign apps using this method if they are free of charge in the app store. If you want to assign paid apps using Intune, consider using the [iOS volume-purchase program](vpp-apps-ios.md).


## Step 1 - Search for the app in the store

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Manage apps**.
4. In the **Mobile apps** workload, choose **Manage** > Apps.
5. Above the list of apps, choose **Add**.
6. In the **Add App** blade, choose **Search the App Store**.
7. In the **Apple App Store** blade, select the App store country locale.
8. Type the name (or part of the name) in the search box. Intune searches the store and return a list of relevant results.
9. From the list, choose the app you want, then click **OK**.

## Step 2 - Configure app information

1. In the **Add App** blade, choose **App Information**.
2. In the **Edit App** blade, configure the app information. Once you are done, click **Add**. Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:
- **Name** -- Type the name of the app for display in the company portal. Make sure all app names that you use are unique. If the same app name exists twice, the company portal displays only one of the apps to users.
- **Description** -- Type a description for the app to displayed to users in the company portal.
- **Publisher** -- Type the name of the publisher of the app.
- **Appstore URL** -- Type the app store URL of the app you want to create.
- **Store country/region** -- Select the App store country locale.
- **Minimum operating system** -- From the list, choose the minimum operating system version on which the app can be installed. The app will not be installed on a device with an earlier operating system.
- **Applicable device type** -- From the list, choose the devices that are used by the App.
- **Category** (optional). Select one or more of the built-in app categories, or a category you created. Categories make it easier for users to find the app when they browse the company portal.
- **Display this as a featured app in the Company Portal** -- Display the app prominently on the main page of the company portal when users browse for apps.
- **Information URL** -- Optionally, type the URL of a website that contains information about this app. The URL displays to users in the company portal.
- **Privacy URL** -- Optionally, type the URL of a website that contains privacy information for this app. The URL displays to users in the company portal.
- **Developer** -- Optionally, type the name of the app developer.
- **Owner** -- Optionally, type a name for the owner of this app, for example, **HR department**.
- **Notes** -- Type any notes you would like to associate with this app.
- **Logo** -- Upload an icon that is associated with the app. The icon is displayed with the app when users browse the company portal.
3. When you are done, on the **Add App** blade, choose **OK**.

The app you have created displays in the apps list, where you can assign it to the groups you choose. For help, see [How to assign apps to groups](apps-deploy.md).
