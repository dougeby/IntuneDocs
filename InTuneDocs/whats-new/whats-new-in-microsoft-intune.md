---
# required metadata

title: What's new | Microsoft Docs
description: Find out what’s new in this month’s and past releases of Microsoft Intune
keywords:
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/15/2017
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
ms.custom: intune-classic

---
# What's new in Microsoft Intune - March 2017
Learn what’s new in this release of Microsoft Intune. You can also find out about upcoming changes that you should be planning for, as well as information about past releases.

> [!Note]
> All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## New Capabilities

### New user experience for the Company Portal app for Android <!--621622-->

The Company Portal app for Android will be updating its user interface for a more modern look and feel, and better user experience. The notable updates are:

- Colors: Company Portal tab headers are colored in IT-defined branding.
- Apps: In the **Apps** tab, the **Featured Apps** and **All Apps** buttons are updated.
- Search: In the **Apps** tab, the **Search** button is a floating action button.
- Navigating Apps: **All Apps** view shows a tabbed view of **Featured**, **All**, and **Categories** for easier navigation.
- Support: **My Devices** and **Contact IT** tabs are updated to improve readability.

For more details about these changes, see [UI updates for Intune end user apps](whats-new-in-intune-app-ui.md).

### Non-managed devices can access assigned apps <!--664691-->

As part of the design changes on the Company Portal website, iOS and Android users will be able to install apps assigned to them as "available without enrollment" on their non-managed devices. Using their Intune credentials, users will be able to log into the Company Portal website and see the list of apps assigned to them. The app packages of the "available without enrollment" apps are made available for download via the Company Portal website. Apps which require enrollment for installation are not affected by this change, as users will be prompted to enroll their device if they wish to install those apps.

### Signing Script for Windows 10 Company Portal <!--941642-->

If you need to download and sideload the Windows 10 Company Portal app, you can now use a script to simplify and streamline the app-signing process for your organization.   To download the script and the instructions for using it, see  [Microsoft Intune Signing Script for Windows 10 Company Portal](https://aka.ms/win10cpscript) on TechNet Gallery. For more details about this announcement, see [Updating your Windows 10 Company Portal app](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) on the Intune Support Team Blog.


## Notices

### Improved support for Android users based in China <!--720444-->

Due to the absence of the Google Play Store in China, Android devices must obtain apps from Chinese marketplaces. The Company Portal will support this workflow by redirecting Android users in China to download the Company Portal and Outlook apps from local app stores. This will improve the user experience when Conditional Access policies are enabled, both for Mobile Device Management and for Mobile Application Management. The Company Portal and Outlook apps for Android are available on the following Chinese app stores:

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

### Best practice: make sure your Company Portal apps are up-to-date <!--879465-->

In December 2016, we released an update that enabled enforcement for multi-factor authentication (MFA) on a group of users when they enroll an iOS, Android, Windows 8.1+, or Windows Phone 8.1+ device. This feature cannot work without certain baseline versions of the Company Portal app for Android (v5.0.3419.0+) and iOS (v2.1.17+).

Microsoft is continuously improving Intune by adding new functions to both the console and the Company Portal apps on all supported platforms. As a result, Microsoft only releases fixes for issues that we find in the current version of the Company Portal app. We therefore recommend to use the latest versions of the Company Portal apps for the best user experience.

>[!Tip]
> Have your users set their devices to automatically update apps from the appropriate app store. If you have made the Android Company Portal app available on a network share, you can download the latest version from [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=49140).

## What's new in the public preview of the Intune admin experience on Azure <!--736542-->

In early calendar year 2017 we will be migrating our full admin experience onto Azure, allowing for powerful and integrated management of core EMS workflows on a modern service platform that’s extensible using Graph APIs.

New trial tenants will start to see the public preview of the new admin experience in the Azure portal this month. While in preview state, capabilities and parity with the existing Intune console will be delivered iteratively.

The admin experience in the Azure portal will use the already announced new grouping and targeting functionality; when your existing tenant is migrated to the new grouping experience you will also be migrated to preview the new admin experience on your tenant. In the meantime, if you want to test or look at any of the new functionality until your tenant is migrated, sign up for a new Intune trial account or take a look at the [new documentation](https://docs.microsoft.com/intune-azure/introduction/whats-new).

> [!Note]
> For the Azure portal preview, we’re rolling out the updates for this month. However, the changes may not be available right away due to how the Intune service is rolled out.  Several components of the service must be updated sequentially over a period of days, and this process can cause delays in the availability of new Azure portal features. Look for changes to the Azure portal preview as they roll out later this month. For the complete list of changes to the Azure preview portal, see [What’s new in the Microsoft Intune preview](/intune-azure/introduction/whats-new).

## What's coming

### Apple to require updates for Application Transport Security <!--748318-->

Beginning in Spring 2017, Apple has announced that they will enforce specific requirements for Application Transport Security (ATS). ATS is used to enforce stricter security on all app communications over HTTPS. This change impacts Intune customers using the iOS Company Portal apps. Review our [Intune support blog](https://aka.ms/compportalats) for more details.

### See also
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [What's new in the Azure preview](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [What's new in the Company Portal UI](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [What's new archive](whats-new-archive.md)
