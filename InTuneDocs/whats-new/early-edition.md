---
# required metadata

title: The Early Edition | Microsoft Intune
description:
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/22/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

ROBOTS: NOINDEX,NOFOLLOW
#audience:
#ms.devlang:
ms.reviewer: cacampbell
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# The Early Edition for Microsoft Intune - December

The **Early Edition** provides a list of features that are coming in upcoming releases of Microsoft Intune. This information is provided under NDA on an extremely limited basis and is subject to change. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Please reach out to your Intune/PM buddy if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

The following changes are under development for Intune. All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

<!--736542-->
## Public preview of the new Intune admin experience on Azure

In early calendar year 2017 we will be migrating our full admin experience onto Azure, allowing for powerful and integrated management of core EMS workflows on a modern service platform that’s extensible using Graph APIs.

New trial tenants will start to see the public preview of the new admin experience in the Azure portal this month. While in preview state, capabilities and parity with the existing Intune console will be delivered iteratively.

The admin experience in the Azure portal will use the already announced new grouping and targeting functionality; when your existing tenant is migrated to the new grouping experience you will also be migrated to preview the new admin experience on your tenant. In the meantime, if you want to test or look at any of the new functionality until your tenant is migrated, sign up for a new Intune trial account or take a look at the new documentation.

If you have any questions about the timeline for your tenant’s migration, contact our migration team at [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### Telecom expense management integration in public preview of Azure portal<!--747605-->
We are now beginning to preview integration with third-party telecom expense management (TEM) services within the Azure portal. You can use Intune to enforce limits on domestic and roaming data usage. We are beginning these integrations with [Saaswedo](http://www.saaswedo.com).

## New Capabilities

### Multi-factor authentication across all platforms <!--747590-->
You can now enforce multi-factor authentication (MFA) on a selected group of users when they enroll an iOS, Android, Windows 8.1+, or Windows Phone 8.1+ device from the Azure Management Portal by configuring MFA on the Microsoft Intune Enrollment application in Azure Active Directory.

### Conditional access for MAM with SharePoint Online <!--VSO 679339-->
You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint Online.  You can get started using Intune mobile app management in the Azure portal. Look for the __Conditional Access__ section in the __Settings__ blade which will include the option for SharePoint Online. This feature will ship separately from the rest of the service release.

## Notices

### Multi-Factor Authentication on Enrollment moving to the Azure portal <!--VSO 750545-->
Previously, admins would go to either the Intune console or the Configuration Manager (earlier than release 1610) console to set MFA for Intune enrollments. With this updated feature, you will now login to the [Microsoft Azure portal](https://manage.windowsazure.com) using your Intune credentials and configure MFA settings through Azure AD. Learn more about this [here](https://aka.ms/mfa_ad).

### Company Portal app for Android now available in China <!--VSO 658093-->
We are publishing the Company Portal app for Android for download in China. Due to the absence of Google Play Store in China, Android devices must obtain apps from Chinese app marketplaces. The Company Portal app for Android will be available for download on 360, Tencent, Xiaomi, Wandoujia and Huawei. 

The Company Portal app for Android uses Google Play Services to communicate with the Microsoft Intune service. Since Google Play Services are not yet available in China, performing any of the following tasks can take up to 8 hours to complete. 

|Intune Admin Console| Intune Company Portal app for Android |Intune Company Portal Website|   
|---|---|---|
|Full wipe| Remove a remote device| Remove device (local and remote)|
|Selective wipe| Reset device| Reset device|
|New or updated app deployments| Install available line-of-business apps| Device passcode reset|
|Remote lock|||
|Passcode reset|||

## Deprecations

### Removal of Exchange Online mobile inbox policies <!--770687-->
Beginning in December, admins will no longer be able to view or configure Exchange Online (EAS) mobile mailbox policies within the Intune console. This change will roll out to all Intune tenants over December and January. All existing policies will stay as configured; for configuring new policies, use the Exchange Management Shell. Find out more information [here](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx).

### Intune AV Player, Image Viewer, and PDF Viewer apps are no longer supported on Android <!--747553-->
From mid-December 2016 on, users will no longer be able to use the Intune AV Player, Image Viewer, and PDF Viewer apps. These apps have been replaced with the Azure Information Protection app. Find out more about the Azure Information Protection app [here](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq).

### See also
See [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md) for details on recent developments.
