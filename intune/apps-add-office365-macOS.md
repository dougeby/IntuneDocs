---
# required metadata

title: Install Office 365 to macOS devices using Intune
titlesuffix: "Azure portal"
description: "Learn how you can use Intune to make it easier to install Office 365 apps on macOS devices."
keywords:
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/13/2017
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

This app type makes it easy for you to assign Office 365 apps to macOS devices. This new app type allows you to install Word, Excel, PowerPoint, Outlook, and OneNote. These apps also come with the Microsoft AutoUpdate (MAU), to help keep the apps more secure and up-to-date. The apps you want appear as one app in the list of apps in the Intune console.


## Before you start

>[!IMPORTANT]
>This method of installing Office is only supported if no other versions of Microsoft Office are installed on the device.

- Devices to which you deploy these apps must be running macOS 10.10 or later.
- Intune only supports adding Office apps included with Office 2016 for Mac suite.
- If any Office apps are opened when Intune installs the app suite, end users might lose data from unsaved files.


## Get started
Add Office 365 using the **Apps** blade.
1.	Sign into the Azure portal.
2.	Choose **More Services** > **Monitoring + Management** > **Intune**.
3.	On the **Intune** blade, choose **Mobile apps**.
4.	In the **Mobile apps** workload, choose **Apps** in the **Manage** group. Choose **Add**.
5.	On the **Add App** blade, choose **Office 365** > **macOS**.
6.  Select **Add**.

## Configure the app suite

Provide information about the app suite. This information helps you to identify it in Intune, and also helps users to find it in the Company Portal app.

1.	On the **Add App** blade, choose **App Suite Information**.
2.  Specify the following information:
	- **Suite Name** - Enter the name of the app suite as it is displayed in the company portal. Make sure all suite names that you use are unique. If the same app suite name exists twice, only one of the apps is displayed to users in the company portal.
	- **Suite Description** - Enter a description for the app suite.
	- **Publisher** - Microsoft appears as the publisher.
	- **Category** - Optionally, select one or more of the built-in app categories, or a category you created. This makes it easier for users to find the app suite when they browse the company portal.
	- **Display this as a featured app in the Company Portal** - This will display the app suite prominently on the main page of the company portal when users browse for apps.
	- **Information URL** - Optionally, enter the URL of a website that contains information about this app. The URL is displayed to users in the company portal.
	- **Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app. The URL is displayed to users in the company portal.
	- **Developer** - Microsoft appears as the developer.
	- **Owner** - Microsoft appears as the owner.
	- **Notes** - Enter any notes you would like to associate with this app.
	- **Upload Icon** - Upload an icon that is displayed with the app when users browse the company portal.
3.	Select **OK**. The suite appears in the list of apps as a single entry.

## Configure app assignments

In this step, configure the assignments for the app suite.

1.	Select the app suite in the list of apps, and select **Assignments**.
2.	Choose **Select groups**.
3.	Assign the suite to the groups you choose. For more information, see [How to assign apps to groups with Microsoft Intune](/intune/apps-deploy).
4.	For each group, you select **Require Install**.
		>[!Note]
		> You cannot uninstall Office 365 through Intune.

5. Select **Save** to commit your assignments.

## Next steps

To learn about adding Office 365 apps to Windows 10 device, see [How to assign Office 365 ProPlus 2016 apps to Windows 10 devices with Microsoft Intune](/intune/apps-add-office365).
