---
# required metadata

title: Manage apps from Windows Store for Business 
titleSuffix: "Intune on Azure"
description: Learn how you can sync apps into Intune from the Windows Store for Business and then assign and track them."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# How to manage apps you purchased from the Windows Store for Business with Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


The [Windows Store for Business](https://www.microsoft.com/business-store) gives you a place to find and purchase apps for your organization, individually, or in volume. By connecting the store to Microsoft Intune, you can manage volume-purchased apps from the Intune portal. For example:
* You can synchronize the list of apps you have purchased from the store with Intune.
* Apps that are synchronized appear in the Intune administration console, and you can assign these like any other apps.
* You can track how many licenses are available, and how many are being used in the Intune administration console.
* Intune blocks assignment and installation of apps if there are an insufficient number of licenses available.

## Before you start

Review the following information before you start syncing and assigning apps from the Windows Store for Business:

- You must configure Intune as the mobile device management authority for your organization.
- You must have signed up for an account on the Windows Store for Business.
- Once you have associated a Windows Business Store account with Intune, you cannot change to a different account in the future.
- Apps purchased from the store cannot be manually added to or deleted from Intune. They can only be synchronized with the Windows Store for Business.
- Intune synchronizes both online and offline licensed apps you have purchased from the Windows Store for Business.
- Only offline apps that are free of charge can be synced to Intune.
- To use this capability, devices must be joined to Active Directory Domain Services, or workplace-joined.
- Enrolled devices must be using the 1511 release of Windows 10 or later.

## Associate your Windows Store for Business account with Intune
Before you enable synchronization in the Intune console, you must configure your store account to use Intune as a management tool:
1. Ensure that you sign into the Business Store using the same tenant account you use to sign into Intune.
2. In the Business Store, choose **Settings** > **Management tools**.
3. On the Management tools page, choose **Add a management tool**, and choose **Microsoft Intune**.

> [!NOTE]
> If you are using more than one management tool to assign Windows Store for Business apps, previously, you could only associate one of these with the Windows Store for Business. You can now associate multiple management tools with the store, for example, Intune and Configuration Manager.

You can now continue, and set up synchronization in the Intune console.

## Configure synchronization

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Mobile apps**.
1. On the **Mobile Apps** blade, choose **Setup** > **Windows Store for Business**.
2. Click **Enable**.
3. If you haven't already done so, click the link to sign-up for the Windows Store for Business and associate your account as detailed previously.
5. From the **Language** drop-down list, choose the language in which apps from the Windows Store for Business will be displayed in the Intune portal. Regardless of the language in which they are displayed, they will be installed in the end user's language when available.
6. Click **Sync** to get the apps you've purchased from the Windows Store into Intune.

## Synchronize apps

1. In the **Mobile apps** workload, choose **Setup** > **Windows Store for Business**.
2. Click **Sync** to get the apps you've purchased from the Windows Store into Intune.

## Assign apps

You assign apps from the store in the same way you assign any other Intune app. For more information, see [How to assign apps to groups with Microsoft Intune](apps-deploy.md). However, instead of assigning apps from the **All Apps** page, you assign them from the **Licensed Apps** page.

Offline apps can be targeted to user groups, device groups or groups with users and devices.
Offline apps can be installed for a specific user on a device or for all users on a device. 


When you assign a Windows Store for Business app, a license is used by each user who installs the app. If you use all of the available licenses for an assigned app, you will not be able to assign any more copies. You must take one of the following actions:
* Uninstall the app from some devices.
* Reduce the scope of the current assignment to target only the users you have sufficient licenses for.
* Buy more copies of the app from the Windows Store for Business.


