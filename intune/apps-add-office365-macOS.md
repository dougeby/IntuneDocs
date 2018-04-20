---
# required metadata

title: Install Office 365 to macOS devices using Microsoft Intune
titlesuffix: 
description: Learn how you can use Microsoft Intune to install Office 365 apps on macOS devices.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: aiwang
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to assign Office 365 to macOS devices with Microsoft Intune

The **Store app** type makes it easy for you to assign Office 365 apps to macOS devices. This app type allows you to install Word, Excel, PowerPoint, Outlook, and OneNote. These apps also come with the Microsoft AutoUpdate (MAU), to help keep the apps more secure and up-to-date. The apps you want appear as one app in the list of apps in the Intune console.


## Before you start

Before you begin adding Office 365 to macOS devices you must understand the following details:

- Devices to which you deploy these apps must be running macOS 10.10 or later.
- Intune only supports adding Office apps included with Office 2016 for Mac suite.
- If any Office apps are opened when Intune installs the app suite, end users might lose data from unsaved files.

## Create and configure the app suite

Add Office 365 using the **Apps** blade.
1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All Services** > **Monitoring + Management** > **Intune**.
3. Choose **Mobile apps** from the **Intune** blade.
4. In the **Mobile apps** workload, choose **Apps** in the **Manage** section. 
5. Choose **Add** to display the **Add app** blade.
6. In the **App type** list, select **macOS** in the **Office 365 Suite** group.
7. Select **App Suite Information** to provide information about the app suite. This information helps you to identify the app suite in Intune, and also helps users to find it in the Company Portal app.
8.  Specify the following information:
	- **Suite Name** - Enter the name of the app suite as it is displayed in the company portal. Make sure all suite names that you use are unique. If the same app suite name exists twice, only one of the apps is displayed to users in the company portal.
	- **Suite Description** - Enter a description for the app suite.
	- **Publisher** - Microsoft appears as the publisher.
	- **Category** - Select one or more of the built-in app categories, or a category you created. This setting makes it easier for users to find the app suite when they browse the company portal.
	- **Display this as a featured app in the Company Portal** - This setting will display the app suite prominently on the main page of the company portal when users browse for apps.
	- **Information URL** (optional) - Enter the URL of a website that contains information about this app. The URL is displayed to users in the company portal.
	- **Privacy URL** (optional) - Enter the URL of a website that contains privacy information for this app. The URL is displayed to users in the company portal.
	- **Developer** - Microsoft appears as the developer.
	- **Owner** - Microsoft appears as the owner.
	- **Notes** (optional) - Enter any notes you would like to associate with this app.
	- **Logo** - The Office 365 logo is displayed with the app when users browse the company portal.
9.	Click **OK** on the **App information** blade.
10. Click **Add** on the **Add app** blade.
    The suite appears in the list of apps as a single entry.

## Configure app assignments

In this step, configure the assignments for the app suite. 

1. Select the **Office 365** app suite in the list of apps to display the **Office 365** overview blade.
2. Click **Assignments** from the **Office 365** blade.
3. Click **Add group** to add a group to use the app suite. The **Add group** blade is displayed.
3. Set the **Assignement type** to **Required**.
4. Assign the suite to the groups you choose. For more information, see [How to assign apps to groups with Microsoft Intune](apps-deploy.md).

    >[!Note]
    > For any groups that you require the Office 365 app suite, you cannot uninstall it through Microsoft Intune.

5. Select **OK** on the **Assign** blade.
6. Select **OK** on the **Add group** blade.
7. Select **Save** to commit your assignments.

## Next steps

- To learn about adding Office 365 apps to Windows 10 device, see [How to assign Office 365 ProPlus 2016 apps to Windows 10 devices with Microsoft Intune](apps-add-office365.md).
- To learn about including and excluding app assignments to groups of users, see [Include and exclude app assignments](apps-inc-exl-assignments.md).
