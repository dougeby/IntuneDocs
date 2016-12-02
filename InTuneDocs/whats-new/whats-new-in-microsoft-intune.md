---
# required metadata

title: What's new | Microsoft Intune
description: Find out what’s new in this month’s, and past releases of Microsoft Intune
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/06/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: priyar
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
# What's new in Microsoft Intune - December 2016
Learn what’s new in this release of Microsoft Intune. You can also find out about upcoming changes that you should be planning for, as well as information about past releases.

> [!Note]
> All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://technet.microsoft.com/library/mt718155.aspx).

## Public preview of the new Intune admin experience on Azure<!--736542-->

In early calendar year 2017 we will be migrating our full admin experience onto Azure, allowing for powerful and integrated management of core EMS workflows on a modern service platform that’s extensible using Graph APIs.

New trial tenants will start to see the public preview of the new admin experience in the Azure portal this month. While in preview state, capabilities and parity with the existing Intune console will be delivered iteratively.

The admin experience in the Azure portal will use the already announced new grouping and targeting functionality; when your existing tenant is migrated to the new grouping experience you will also be migrated to preview the new admin experience on your tenant. In the meantime, if you want to test or look at any of the new functionality until your tenant is migrated, sign up for a new Intune trial account or take a look at the [new documentation](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

If you have any questions about the timeline for your tenant’s migration, contact our migration team at [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### Telecom expense management integration in public preview of Azure portal<!--747605-->
We are now beginning to preview integration with third-party telecom expense management (TEM) services within the Azure portal. You can use Intune to enforce limits on domestic and roaming data usage. We are beginning these integrations with [Saaswedo](http://www.saaswedo.com).

## New Capabilities

### Multi-factor authentication across all platforms <!--747590-->
You can now enforce multi-factor authentication (MFA) on a selected group of users when they enroll an iOS, Android, Windows 8.1+, or Windows Phone 8.1+ device from the Azure Management Portal by configuring MFA on the Microsoft Intune Enrollment application in Azure Active Directory.

### Conditional access for MAM with SharePoint Online <!--VSO 679339-->
You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint Online.  You can get started using Intune mobile app management in the Azure portal. Look for the __Conditional Access__ section in the __Settings__ blade which will include the option for SharePoint Online. This feature will ship separately from the rest of the service release. Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).

### Ability to restrict mobile device enrollment<!--747596-->
Intune is adding new enrollment restrictions that control which mobile device platforms are allowed to enroll. Intune separates mobile device platforms as iOS, macOS, Android, Windows and Windows Mobile.
* Restricting mobile device enrollment does not restrict PC client enrollment.
* For iOS only, there is one additional option to block the enrollment of personally owned devices.

Intune marks all new devices as personal unless the IT admin takes action to mark them as corporate owned, as explained in [this article](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).


## Notices

### Multi-Factor Authentication on Enrollment moving to the Azure portal <!--VSO 750545-->
Previously, admins would go to either the Intune console or the Configuration Manager (earlier than release October 2016) console to set MFA for Intune enrollments. With this updated feature, you will now login to the [Microsoft Azure portal](https://manage.windowsazure.com) using your Intune credentials and configure MFA settings through Azure AD. Learn more about this [here](https://aka.ms/mfa_ad).

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

### Firefox to no longer support Silverlight<!--VSO TBA-->
Mozilla is removing support for Silverlight in version 52 of the [Firefox browser](https://www.mozilla.org/firefox), effective March 2017. As a result, you will no longer be able to log in to the existing Intune console using Firefox versions greater than 51. We recommend using Internet Explorer 10 or 11 to access the admin console, or a [version of Firefox prior to version 52](https://ftp.mozilla.org/pub/firefox/releases). Intune's transition to the Azure portal will allow it to support a number of [modern browsers](https://docs.microsoft.com/en-us/azure/azure-preview-portal-supported-browsers-devices) without dependency on Silverlight.

### Removal of Exchange Online mobile inbox policies <!--770687-->
Beginning in December, admins will no longer be able to view or configure Exchange Online (EAS) mobile mailbox policies within the Intune console. This change will roll out to all Intune tenants over December and January. All existing policies will stay as configured; for configuring new policies, use the Exchange Management Shell. Find out more information [here](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx).

### Intune AV Player, Image Viewer, and PDF Viewer apps are no longer supported on Android <!--747553-->
From mid-December 2016 on, users will no longer be able to use the Intune AV Player, Image Viewer, and PDF Viewer apps. These apps have been replaced with the Azure Information Protection app. Find out more about the Azure Information Protection app [here](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq).

### See also
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Previous Intune releases](whats-new-archive.md)
