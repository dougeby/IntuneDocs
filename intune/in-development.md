---
# required metadata

title: In development - Microsoft Intune
titleSuffix: 
description: Microsoft Intune features in development
keywords:
author: ErikjeMS 
ms.author: erikje
manager: dougeby
ms.date: 08/30/2019
ms.topic: conceptual
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

# In development for Microsoft Intune - September 2019

To assist in your readiness and planning, this page lists Intune UI updates and features that are in development but not yet released. In addition:

- If we anticipate that you'll need to take action before a change, we’ll publish a complementary Office Message Center post.
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

<!-- Common categories:  
#### App management
#### Device configuration
#### Device enrollment
#### Device management
#### Intune apps
#### Monitor and troubleshoot
#### Role-based access control
#### Security

-->
 
<!-- ***********************************************-->
## App management

### Company Portal app installation status messages <!-- 2514416  -->
The Company Portal app will show additional app installation status messages to end users. The following conditions will apply to new Win32 dependency features:
- App failed to install. Dependencies defined by the admin were not met.
- App installed successfully but requires a restart.
- App is in the process of installing, but requires a restart to continue.

### macOS support for VPP apps <!-- 3173501  -->
macOS apps you have purchased using Apple Business Manager will be displayed in the console when Apple VPP tokens are synced in Intune. You can assign, revoke and reassign device and user-based licenses for groups using the console. Microsoft Intune helps you manage VPP apps purchased for use at your company by:
- Reporting license information from the app store.
- Tracking how many of the licenses you have used.
- Helping you to not install more copies of the app than you own.
For more information about Intune and VPP, see [Manage volume-purchased apps and books with Microsoft Intune](vpp-apps.md).

### macOS support for web apps <!-- 3174427  -->
You'll be able to install Web apps, which allow you to add a shortcut to a URL on the web, to the Dock using the macOS Company Portal. End-users can access the **Install** action from the app details page for a web app in the macOS Company Portal. For more information about the **Web link** app type, see [Add apps to Microsoft Intune](apps-add.md).

#### Assign Microsoft Edge beta for macOS <!-- 4678761  -->
You'll be able to add and assign the latest version of Microsoft Edge beta to Intune for macOS devices. From Intune, select **Client apps** > **Apps** > **Add app** > **Microsoft Edge - macOS**. Then, assign Microsoft Edge beta to the intended groups. Microsoft AutoUpdate (MAU) keeps Microsoft Edge up-to-date. For more information about Microsoft Edge, see [Manage web access by using Microsoft Edge with Microsoft Intune](manage-microsoft-edge.md).

### Configure app notification content for organization accounts <!-- 2576686 -->
Intune app protection policies (APP) on Android and iOS devices will allow you to control app notification content for Org accounts. This feature will require support from applications and may not be available for all APP enabled applications. For more about APP, see [What are app protection policies?](app-protection-policy.md).

### Available Google Play app reporting for Android work profiles <!-- 3041956  -->
For available app installs on Android work profile devices, you can view app installation status and the installed version of managed Google Play apps. For more information, see [How to monitor app protection policies](app-protection-policies-monitor.md), [Manage Android work profile devices with Intune](android-enterprise-overview.md) and [Managed Google Play app type](apps-add-android-for-work.md#managed-google-play-app-types).

<!-- ***********************************************-->
<!--## Device configuration-->

<!-- ***********************************************-->
## Device enrollment

### For iOS devices, customize the enrollment process privacy screen of the Company Portal <!-- 4394993  -->
Using markdown, you'll be able to customize the Company Portal's privacy screen that end users see during iOS enrollment. Specifically, you'll be able to customize the list of things that your organization can't see or do on the device.

<!-- ***********************************************-->
## Device management

### Deploy Software Updates to macOS devices <!-- 3194876 -->
You'll be able to deploy Software Updates to groups of macOS devices. This feature includes critical, firmware, configuration file, and other updates. You'll be able to send updates on the next device check-in or select a weekly schedule to deploy updates in or out of time windows that you set. This helps when you want to update devices outside standard work hours or when your help desk is fully staffed. You'll also get a detailed report of all macOS devices with updates deployed. You can drill into the report on a per-device basis to see the statuses of particular updates.

<!-- ***********************************************-->
## Monitor and troubleshoot

### Updated support experience   <!--  5012398    -->
As part of continuing improvements, we’ll be updating the in-console support experience for Intune.  We’ll be improving the in-console search and feedback for common issues, and streamlining the workflow to contact support.     

<!-- ***********************************************-->
<!--## Security-->


<!-- ***********************************************-->
## Notices

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.




