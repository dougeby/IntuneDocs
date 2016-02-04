---
title: Manage apps you purchased from the Windows Store for Business with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1643dec0-51dc-4c3a-9dd3-23da496403d9
author: robstackmsft
---
# Manage apps you purchased from the Windows Store for Business with Microsoft Intune
The [Windows Store for Business](https://www.microsoft.com/business-store) gives you a place to find and purchase apps for your organization, individually, or in volume. By connecting the store to [!INCLUDE[wit_firstref](/Token/wit_firstref.xml)], you can manage volume-purchased apps from the [!INCLUDE[wit_nextref](/Token/wit_nextref.xml)] console, for example:
* You can synchronize the list of apps you have purchased from the store with [!INCLUDE[wit_nextref](/Token/wit_nextref.xml)]
* Apps that are synchronized appear in the [!INCLUDE[wit_nextref](/Token/wit_nextref.xml)] console and you can deploy these like any other apps
* You can track how many licences are available, and how many are being used in the [!INCLUDE[wit_nextref](/Token/wit_nextref.xml)] console
* [!INCLUDE[wit_nextref](/Token/wit_nextref.xml)] blocks deployment and installation of apps if there are not sufficient licenses avaiable

## Before you start
Review the following information before you start syncing and deploying apps from the Windows Store for Business:
* You must configure [!INCLUDE[wit_nextref](/Token/wit_nextref.xml)] as the mobile device management authority for your organization. For more information, see [Set mobile device management authority and configure Microsoft Intune](Set-mobile-device-management-authority-and-configure-Microsoft-Intune.md)
* You must have signed up for an account on the Windows Store for Business
* Once you have associated a Windows Business Store account with [!INCLUDE[wit_nextref](/Token/wit_nextref.xml)], you cannot change to a different account in the future.
* Apps purchased from the store cannot be manually added to, or deleted from [!INCLUDE[wit_nextref](/Token/wit_nextref.xml)]. They can only be synchronized with the Windows Store for Business.

## Associate your Windows Store for Business account with Intune
Before you enable synchronization in the [!INCLUDE[wit_nextref](/Token/wit_nextref.xml)] console, you must configure your store account to use [!INCLUDE[wit_nextref](/Token/wit_nextref.xml)] as a management tool:
1. Ensure that you log into the Business Store using the same tenant account you use to log into [!INCLUDE[wit_nextref](/Token/wit_nextref.xml)]
2. In the Business Store, choose **Settings** > **Management tools**.
3. On the Management tools page, choose **Add a management tool**, and choose Microsoft Intune.

You can now continue, and set up synchronization in the [!INCLUDE[wit_nextref](/Token/wit_nextref.xml)] console.

## Configure synchronization

1. In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Admin**.
2. In the **Administration** workspace, expand **Mobile Device Management**, and then click **Store for Business**.
3. On the **Windows Store for Business** page, do the following:
* If you haven't already done so, click the link to sign-up for the Windows Store for Business
* Once you are signed-up, click **Configure Sync**
4. In the **Configure Windows Store for Business app sync** dialog box, select **Enable Windows Store for Business sync**.
5. From the **Language** drop-down list, choose the language in which apps from the Windows Store for Business will be displayed in the [!INCLUDE[wit_nextref](/Token/wit_nextref.xml)] console. Regardless of the language in which they are displayed, they will be installed in the end user's language when available.
6. Click **OK**.

## Synchronize apps

1. On the **Windows Store for Business** page, click **Sync now** to synchronize the apps you've purchased from the store with [!INCLUDE[wit_nextref](/Token/wit_nextref.xml)].
2. In the **Apps** workspace, click **Managed Software** > **Licensed Software** to view the avaiable apps and to verify that your purchased apps were imported correctly.
The apps in this node are displayed with the total number of licenses you own, together with the number of licenses you have available.

## Deploy apps

You deploy apps in the same way you deploy any other [!INCLUDE[wit_nextref](/Token/wit_nextref.xml)] app. For more information, see [Deploy apps to mobile devices in Microsoft Intune](Deploy-apps-to-mobile-devices-in-Microsoft-Intune.md).
When you deploy a Windows Store for Business app, a license is used by each user who installs the app. If you use all of the avialble licenses for a deployed app, you will not be able to deploy any more copies and must take one of the following actions:
* Uninstall the app from some devices
* Reduce the scope of the current deployment to target only the users you have sufficient licenses for
* Buy more copies of the app from the Windows Store for Business


## See also
[Deploy apps to mobile devices in Microsoft Intune](Deploy-apps-to-mobile-devices-in-Microsoft-Intune.md)


