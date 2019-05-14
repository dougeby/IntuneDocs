---
# required metadata

title: In development - Microsoft Intune
titleSuffix: 
description: Microsoft Intune features in development
keywords:
author: ErikjeMS 
ms.author: erikje
manager: dougeby
ms.date: 04/29/2019
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: seodec18
ms.collection: M365-identity-device-management
---

# In development for Microsoft Intune - May 2019

To assist in your readiness and planning, this page lists Intune UI updates and features that are in development but not yet released. In addition:

- If we anticipate that you'll need to take action prior to a change, we’ll publish a complementary Office Message Center post.
- When a feature is launched in production, either as a preview or generally available, the feature description will move off this page and onto the [What's New page](whats-new.md).
- This page and the [What's New page](whats-new.md) are updated periodically. Check back for additional updates.
- Refer to the [M365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) for strategic deliverables and timelines.

> [!Note]
> These items reflect Microsoft’s current expectations about Intune capabilities coming in a future release. Dates and individual features may change. Not all items in development have a feature description on this page.

**RSS feed**: Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->
 
## Intune in the Azure portal


<!-- 1905 start-->


### Deleting a device in the Apple portal will be reflected in the Intune portal <!--2489996 -->
If a device is deleted from Apple's Device Enrollment Program or Apple Business Manager portals, the device will automatically be deleted from Intune during the next sync.

### Baseline support for keyword search  <!-- 3082036         -->
While creating or editing a security baseline profile, you’ll soon be able to use *search* to filter the settings that display in the console.   

### Reset and wipe devices in bulk by using the Graph API <!-- 3295288 -->
You'll be able to reset and wipe up to 100 devices in bulk using the Graph API.

### Intune management extension PowerShell scripts  <!-- 3734186    -->
You'll be able to configure PowerShell scripts to run with the user’s admin privileges on the device. For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](intune-management-extension.md).

### Android Enterprise app management <!-- 4459905 idready -->
To make it easier for IT admins to configure and use Android Enterprise management, Intune will automatically add four common Android Enterprise related apps to the Intune admin console. The four Android Enterprise apps are the following:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** - Used for Android Enterprise fully managed scenarios.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** -  Helps you sign-in to your accounts if you use two-factor verification.
- **[Intune Company Portal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** - Used for App Protection Policies (APP) and Android Enterprise work profile scenarios.
- [Managed Home Screen](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) - Used for Android Enterprise dedicated/kiosk scenarios.

Previously, IT admins would need to manually find and approve these apps in the [Managed Google Play store](https://play.google.com/store/apps) as part of setup. This change removes those previously manual steps to make it easier and faster for customers to use Android Enterprise management.

Admins will see these four apps automatically added to their Intune apps list at the time that they first connect their Intune tenant to managed Google Play. For more information, see [Connect your Intune account to your Managed Google Play account](connect-intune-android-enterprise.md). For tenants that have already connected their tenant or who already use Android Enterprise, there is nothing admins need to do. Those four apps will automatically show up within 7 days of the completion of the May 2019 service roll out.

<!-- 1904 start-->

### Advanced settings for Windows Defender Firewall <!-- 1311949 -->
You'll soon be able to use Intune to manage the custom firewall rules on clients for Windows Defender. Rules can specify inbound and outbound behavior to applications, network addresses, and ports. 


### Device users can view all managed apps they've installed or tried to install <!-- 2352913 -->
Company Portal for Windows will list all managed apps&ndash; both required and available&ndash; that are installed on a user's device. Users will be able to view attempted and pending app installations, and their current statuses. If your organization doesn't make apps required or available, users will see a message explaining that no company apps have been installed. Users will also be able to sort or filter their apps by installation status.

### Use "applicability rules" when creating Windows 10 device configuration profiles <!-- 2549910 -->
You create Windows 10 device configuration profiles (**Device configuration** > **Profiles** > **Create profile** > **Windows 10** for platform). You'll be able to create an **applicability rule** so the profile only applies to a specific edition or specific version. For example, you create a profile that enables some BitLocker settings. Once you add the profile, use an applicability rule so the profile only applies to devices running Windows 10 Enterprise.

Applies to: 
- Windows 10 and later


### Windows Defender Advanced Threat Protection baseline <!-- 3754134 -->
We're going to add new baseline to help you configure Windows Defender Advanced Threat Protection settings.



## Notices

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.


