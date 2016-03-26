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
The [Windows Store for Business](https://www.microsoft.com/business-store) gives you a place to find and purchase apps for your organization, individually, or in volume. By connecting the store to Microsoft Intune, you can manage volume-purchased apps from the Intune console, for example:
* You can synchronize the list of apps you have purchased from the store with Intune.
* Apps that are synchronized appear in the Intune administration console and you can deploy these like any other apps
* You can track how many licenses are available, and how many are being used in the Intune administration console
* Intune blocks deployment and installation of apps if there are not sufficient licenses available

## Before you start
Review the following information before you start syncing and deploying apps from the Windows Store for Business:
* You must configure Intune as the mobile device management authority for your organization. For more information, see [Set mobile device management authority and configure Microsoft Intune](set-mobile-device-management-authority-and-configure-microsoft-intune.md)
* You must have signed up for an account on the Windows Store for Business
* Once you have associated a Windows Business Store account with Intune, you cannot change to a different account in the future.
* Apps purchased from the store cannot be manually added to, or deleted from Intune. They can only be synchronized with the Windows Store for Business.

## Associate your Windows Store for Business account with Intune
Before you enable synchronization in the Intune console, you must configure your store account to use Intune as a management tool:
1. Ensure that you log into the Business Store using the same tenant account you use to log into Intune.
2. In the Business Store, choose **Settings** > **Management tools**.
3. On the Management tools page, choose **Add a management tool**, and choose Microsoft Intune.

You can now continue, and set up synchronization in the Intune console.

## Configure synchronization

1. In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Admin**.
2. In the **Administration** workspace, expand **Mobile Device Management**, and then click **Store for Business**.
3. On the **Windows Store for Business** page, do the following:
* If you haven't already done so, click the link to sign-up for the Windows Store for Business
* Once you are signed-up, click **Configure Sync**
4. In the **Configure Windows Store for Business app sync** dialog box, select **Enable Windows Store for Business sync**.
5. From the **Language** drop-down list, choose the language in which apps from the Windows Store for Business will be displayed in the Intune console. Regardless of the language in which they are displayed, they will be installed in the end user's language when available.
6. Click **OK**.

## Synchronize apps

1. On the **Windows Store for Business** page, click **Sync now** to synchronize the apps you've purchased from the store with Intune.
2. In the **Apps** workspace, click **Managed Software** > **Licensed Software** to view the available apps and to verify that your purchased apps were imported correctly.
The apps in this node are displayed with the total number of licenses you own, together with the number of licenses you have available.

## Deploy apps

You deploy apps from the store in the same way you deploy any other Intune app. For more information, see [Deploy apps to mobile devices in Microsoft Intune](deploy-apps-to-mobile-devices-in-microsoft-intune.md).
When you deploy a Windows Store for Business app, a license is used by each user who installs the app. If you use all of the available licenses for a deployed app, you will not be able to deploy any more copies and must take one of the following actions:
* Uninstall the app from some devices
* Reduce the scope of the current deployment to target only the users you have sufficient licenses for
* Buy more copies of the app from the Windows Store for Business


### See also
[Deploy apps to mobile devices in Microsoft Intune](deploy-apps-to-mobile-devices-in-microsoft-intune.md)


