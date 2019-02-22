---
# required metadata

title: Early edition - Microsoft Intune
titlesuffix: 
description: Microsoft Intune early edition
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 02/04/2019
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
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: seodec18
ms.collection: M365-identity-device-management
---

# The early edition for Microsoft Intune - February 2019

> [!Note]
> NDA notification: The following changes are under development for Intune. This information is shared under NDA on a very limited basis. Do not post any of this information on social media or public websites such as Twitter, UserVoice, Reddit, and so on. 

The **early edition** provides a list of features, shared under NDA, that are coming in upcoming releases of Microsoft Intune. This information is provided on a limited basis and is subject to change. Do not tweet, post on UserVoice, or otherwise share this information outside of your company. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Reach out to your Microsoft product group contact if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## Intune in the Azure portal
<!-- 1902 start-->


<!-- 1901 start -->

### Deployment of online licensed Microsoft Store for Business apps <!-- 1672660  -->
You will be able to assign required online licensed Microsoft Store for Business apps in the device context. Deploying a Microsoft Store for Business app this way will enable the app to be installed for all users on the device. This is only applicable on Windows 10 RS4+ desktop devices. The option to install in the device context is available in the Client Apps assignment page for MSFB Online Licensed apps.

<!-- 1812 start -->

### Android Enterprise APP-WE app deployment <!-- 1171203 -->
For Android devices in a non-enrolled App Protection Policy Without Enrollment (APP-WE) deployment scenario, you'll be able to use managed Google Play to deploy store apps and LOB apps to users. Specifically, IT can provide end users with an app catalog and installation experience that no longer requires end users to loosen the security posture of their devices by allowing installations from unknown sources. In addition, this deployment scenario will provide an improved end user experience.

### Intune policies update authentication method and Company Portal app installation  <!-- 1927359 -->
On devices already enrolled via Setup Assistant through one of Apple’s corporate device enrollment methods, Intune will no longer support the Company Portal when it is manually installed by end users from the app store. This change is only relevant when you authenticate with Apple Setup Assistant during enrollment. This change also only affects iOS devices enrolled through:  
* Apple configurator
* Apple Business Manager
* Apple School Manager
* Apple Device Enrollment Program (DEP)

If users install the Company Portal app from the App store, and then try to enroll these devices through it, they will receive an error. These devices will be expected to only use Company Portal when it's been pushed, automatically, by Intune during enrollment. Enrollment profiles in Intune in the Azure portal will be updated so that you can specify how devices authenticate and if they receive the Company Portal app. If you want your DEP device users to have the Company Portal, you will need to specify your preferences in an enrollment profile. 
In addition, the **Identify your device** screen in the Company Portal app will soon become obsolete.  
To install Company Portal on already-enrolled DEP devices, you will need to go to Intune > Client apps, and push it as a managed app with app configuration policies. Details about how to do these steps will be outlined in future docs.

### Administrative templates are in public preview, and moved to their own configuration profile <!-- 3322847 -->
Administrative templates in Intune (**Device configuration** > **Administrative templates**) are currently in private preview. With this update:
Administrative templates includes about 300 settings that can be managed in Intune. Previously, these settings only existed in the group policy editor.
Administrative templates are available in public preview
Administrative templates are moving from **Device configuration** > **Administrative templates** to **Device configuration** > **Profiles** >**Create profile** > In **Platform**, choose **Windows 10 and later**, In **Profile type**, choose **Administrative templates**.
Reporting is enabled
Applies to: Windows 10 and later

### Intune macOS Company Portal Dark Mode <!-- 3300524 -->
The Intune macOS Company Portal now supports Dark Mode for macOS. When you enable Dark Mode on a macOS 10.14+ device, the Company Portal will adjust its appearance to colors that reflect that mode.

<!-- 1809 start -->  

### App Protection Policy (APP) settings for web data <!-- 2662995 -->
APP policy settings for web content on both Android and iOS devices will be updated to better handle both http and https web links, as well as data transfer via iOS Universal Links and Android App Links.  

<!-- 1808 start -->

### Apple VPP token used by another MDM <!-- 1488946 -->
Intune will detect and show details if an Apple volume-purchased program (VPP) token is in use by both Intune and another MDM.

### Retired devices in the device compliance dashboard <!-- 1981119 -->
In a future update, retired devices will be removed from the device compliance dashboard. This will change your compliance numbers.

## Notices

There are no active notices at this time.

### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.
