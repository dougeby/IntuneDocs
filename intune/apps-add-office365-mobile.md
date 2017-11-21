---
# required metadata

title: Install Office 365 apps to Mobile devices using Intune
titlesuffix: Azure portal
description: Learn how you can use Intune to make it easier to install Office 365 apps on Windows 10 devices.
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/21/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 91B6842A-982A-4919-A5A5-0E16B93C777E

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: aiwang
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to assign Office 365 apps to mobile devices with Microsoft Intune

The **Built-in** app type type makes it easy for you to assign Office 365 apps to the iOS and Android devices that you manage. These apps include 0365 apps such as Word, Excel, PowerPoint, and OneDrive. The apps appear as one app in the list of apps in the Intune console. You can assign specific apps to the app type and edit the app information configuration.

## Before you start

- iOS devices must be `specifications` or later.
- Android devices must be `specifications` or later.

## Get started

1.  Sign into the Azure portal.
2.  Choose **More Services** > **Monitoring + Management** > **Intune**.
3.  On the **Intune** blade, choose **Mobile apps**.
4.  In the **Mobile apps** workload, choose **Apps** in the **Manage** group.
5. Choose **Add**.
6.  On the **Add App** blade, choose *Built-in Apps** and click **Add**.

## Configure the app suite

In this step, choose the Office apps you want to assign to devices.

1.  On the **Add App** blade, choose **Select app**.
2.  Choose the  Office apps that you want to assign to devices form the app list.
3.  When you are done, click **OK**.

## Configure app information

In this step, provide information about the app suite. This information helps you to identify it in Intune, and also helps users to find it in the Company Portal app.

1.  On the **Add App** blade, choose **App Suite Information**.
2.  On the **App Suite Information** blade, specify the following information: 
  - **Suite Name** - Enter the name of the app suite as it is displayed in the company portal. Make sure all suite names that you use are unique. If the same app suite name exists twice, only one of the apps is displayed to users in the company portal.
  - **Suite Description** - Enter a description for the app suite. For example, you could list the apps you've selected to include.
  - **Publisher** - Enter the name of the publisher of the app.
  - **Category** - Optionally, select one or more of the built-in app categories, or a category you created. This makes it easier for users to find the app suite when they browse the company portal.
  - **Display this as a featured app in the Company Portal** - Display the app suite prominently on the main page of the company portal when users browse for apps.
  - **Information URL** - Optionally, enter the URL of a website that contains information about this app. The URL is displayed to users in the company portal.
  - **Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app. The URL is displayed to users in the company portal.
  - **Developer** - Optionally, enter the name of the app developer.
  - **Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.
  - **Notes** - Enter any notes you would like to associate with this app.
  - **Upload Icon** - Upload an icon that is displayed with the app when users browse the company portal.
3.  When you are done, click **OK**.

## Configure app settings

In this step, configure installation options for the app suite. The settings apply to all apps you added to the suite.

1.  On the **Add App** blade, choose **App Suite Settings**.
2.  On the **App Suite Settings** blade, specify the following information: 
  - **Office version** - Choose whether you want to assign the 32-bit, or 64-bit version of Office. You can install the 32-bit version on both 32-bit, and 64-bit devices, but you can only install the 64-bit version on 64-bit devices.
  - **Update Channel** - Choose how office is updated on devices.
  - **Automatically accept the app end user license agreement** - Select this option if you don't require end users to accept the license agreement. Intune then automatically accepts the agreement.
  - **Use shared computer activation** - Shared computer activation is used when multiple users share a computer. For more information, see Overview of shared computer activation for Office 365.
  - **Languages** - Office automatically installs in any supported languages that are installed with Windows on the end-users device. Select this option if you want to install additional languages with the app suite.

## Finish up

When you are done, on the **Add App** blade, choose **Save**. The app you have created is displayed in the apps list.

## Next steps

You can now assign the apps the groups you choose. For help, see [How to assign apps to groups](/intune-azure/manage-apps/deploy-apps).