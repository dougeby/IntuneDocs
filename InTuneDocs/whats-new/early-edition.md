

---
# required metadata

title: The early edition | Microsoft Intune
description:
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/4/2016
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

# The Early Edition for Microsoft Intune - November

The **Early Edition** provides a list of features that are coming in upcoming releases of Microsoft Intune. This information is provided under NDA on an extremely limited basis and is subject to change. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Please reach out to your Intune/PM buddy if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

The following changes are under development for Intune. All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## New capabilities

### New Microsoft Intune Company Portal App for Windows 10 devices
Microsoft is releasing a new Microsoft Intune Company Portal for Windows 10 devices. This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today. The new app will also allow users to leverage additional platform features like Single Sign On and Certificate based authentication on Windows 10 devices.

The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store. It will also be available for sideloading.

### Windows Store for Business Apps in the New Company Portal App for Windows 10
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of Available or Required. After syncing Windows Store for Business apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.

## Deprecations

### Certificates and Support for the Windows Phone 8 Company Portal

From November 2016, the Windows Phone 8 Company Portal will no longer be required to upload a Symantec Signing Cert in the Intune Admin Console. In addition, the support for Windows Phone 8 Company Portal will also be deprecated.

Support for the Windows Phone 8 and WinRT platforms was deprecated in October 2016. Support for the Windows 8 Company Portal was also deprecated in October 2016.

### See also
See [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md) for details on recent developments.
