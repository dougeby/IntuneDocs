---
title: Manage apps you purchased through a volume-purchase program with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 9797054d-7e97-4467-96f7-d061a296ed45
author: robstackmsft
---
# Manage apps you purchased through a volume-purchase program with Microsoft Intune
Some app stores give you the ability to purchase multiple licenses for an app you want to run in your company. This helps you reduce the administrative overhead of tracking multiple purchased copies of apps.

[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] helps you manage apps you purchased through such a program by importing the license information from the app store, tracking how many of the licenses you have used, and preventing you from installing more copies of the app than you own.

## Manage volume-purchased apps for iOS devices
You purchase multiple licenses for iOS apps through the [Apple Volume Purchase Program for Business (VPP)](http://www.apple.com/business/vpp/). This involves setting up an Apple VPP account from the Apple web site and the Apple VPP token into [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].  You can then synchronize your volume purchase information with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] and track your volume-purchased app use.

### Before you start
Before you begin, you'll need to get a VPP token from Apple, and upload this to your [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] account.

> [!IMPORTANT]
> -   Each organization can have only one VPP account and token.
> -   Once you associate an Apple VPP account to Intune, you cannot subsequently associate a different account. For this reason, it's very important that more than one person has the details of the account you use.
> -   If you have previously used a VPP token with a different product, you must generate a new one to use with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].
> -   Each token is valid for one year.
> -   By default, [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] syncs with the Apple VPP service twice a day. You can, however, initiate a manual sync at any time.

##### To get and upload an Apple VPP token

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Admin** &gt; **iOS and Mac OS X** &gt;  **Volume Purchase Program**.

2.  Click the **Apple VPP Account** link, and if you haven't already, sign up for the Volume Purchase Program for Business. Once you are signed up, download the Apple VPP token for your account.

3.  On the **Manage Apple Volume Purchase Program (VPP)** page of the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console, click **Upload the VPP token**.

4.  In the **Upload the VPP token** dialog box, enter or paste the VPP token name, and your Apple ID, then click **Upload**.

5.  In the warning dialog box, click the checkbox to indicate that you understand that you can't change to a different VPP account later, then click **Yes**.

On the **Volume Purchase Program** page, you can now view information about the Apple VPP token including when it was last updated, when it will expire, and when it was last synchronized with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

You can synchronize the data held by Apple with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] at any time by clicking **Sync now**.

### Step 2 - Upload and deploy a volume-purchased app

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Apps** &gt; **Managed Software** &gt; **Volume-Purchased apps**.

2.  Use the instructions in the [Deploy apps to mobile devices in Microsoft Intune - deleted](../Topic/Deploy_apps_to_mobile_devices_in_Microsoft_Intune_-_deleted.md) topic to complete uploading, creation, and deployment of the app.

When you deploy the app as a **Required** install, a license is used by each user that installs the app.

To reclaim a license, you must change the deployment action to **Uninstall**. The license will be reclaimed once the app uninstalls.

When a user with an eligible device first tries to install a VPP app, they will be asked to join the Apple Volume Purchase program. They must do this before the app installation proceeds.

> [!TIP]
> Look at the **VPP Terms Status** column to see the acceptance status for each user to whom the app was deployed.

If there are no further licenses available, the deployment will fail.

### Step 3 - Monitor Apple VPP apps
You can monitor which VPP apps have been deployed, and how many licenses are used from the **Apps** workspace, in the **Managed Software** &gt; **Volume-Purchased Apps** node.

> [!TIP]
> You can also use app **Filters** to examine the status of each app install.

## See Also
[Deploy and configure apps with Microsoft Intune](../Topic/Deploy_and_configure_apps_with_Microsoft_Intune.md)

