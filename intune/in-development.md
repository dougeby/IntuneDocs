---
# required metadata

title: In development - Microsoft Intune
titleSuffix: 
description: Microsoft Intune features in development
keywords:
author: ErikjeMS 
ms.author: erikje
manager: dougeby
ms.date: 04/15/2019
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

# In development for Microsoft Intune - April 2019

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

<!-- 1904 start-->

### Advanced settings for Windows Defender Firewall <!-- 1311949 -->
You'll soon be able to use Intune to manage the custom firewall rules on clients for Windows Defender. Rules can specify inbound and outbound behavior to applications, network addresses, and ports. 

### Require App Protection Conditional Access  <!--1634317 -->
You'll be able to use *Require App Protection policy*, which confirms policy is applied to a user’s app before sign in completes to prevent users from accessing data you protect with conditional access. While policy assurance might slow down the first use experience, it helps to protect against network issues, administrative misconfigurations, or intentional efforts to foil application protection policies. 

### Configure settings for kernel extensions on macOS devices <!-- 2043024 -->
On macOS devices, you can create a device configuration profile (**Device configuration** > **Profiles** > **Create profile** > choose **macOS** for platform). A new group of settings will let you configure and use kernel extensions on your devices.

Applies to: 
macOS 10.13.2 and later

### Device users can view all managed apps they've installed or tried to install <!-- 2352913 -->
Company Portal for Windows will list all managed apps&ndash; both required and available&ndash; that are installed on a user's device. Users will be able to view attempted and pending app installations, and their current statuses. If your organization doesn't make apps required or available, users will see a message explaining that no company apps have been installed. Users will also be able to sort or filter their apps by installation status.

### Use "applicability rules" when creating Windows 10 device configuration profiles <!-- 2549910 -->
You create Windows 10 device configuration profiles (**Device configuration** > **Profiles** > **Create profile** > **Windows 10** for platform). You'll be able to create an **applicability rule** so the profile only applies to a specific edition or specific version. For example, you create a profile that enables some BitLocker settings. Once you add the profile, use an applicability rule so the profile only applies to devices running Windows 10 Enterprise.

Applies to: 
- Windows 10 and later

### Monitor Security Baseline status (public preview) <!-- 3082047 --> 
When you monitor the *Device status* for your security baselines, the view will organize the status by the baseline categories, like *Above lock*, *BitLocker*, and *Browser*. All available baseline categories will be represented. For each category, you'll see how many devices do not match a specific baseline category, are misconfigured, or are not applicable.

###  Intune security tasks for Defender ATP (In public preview) <!-- 3208597 -->
Coming as a public preview, Intune will soon add security tasks for the newly announced Microsoft Defender Threat & Vulnerability Management.  With this integration, security operations admins in Windows Defender ATP (WDATP) can more effectively communicate the recommended remediations for emerging threats to Intune administrators. The addition of security tasks adds a risk-based approach to discover, prioritize, and remediate endpoint vulnerabilities and misconfigurations.

To learn more about security tasks in Intune, see the blog post about [using Intune security tasks to extend Microsoft Defender ATP’s Threat and Vulnerability Management](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### Windows Defender Advanced Threat Protection baseline <!-- 3754134 -->
We're going to add new baseline to help you configure Windows Defender Advanced Threat Protection settings.


### iOS Third Party Keyboards <!-- 4111843 -->
Support for the Intune app protection policy (APP) for the **Third Party Keyboards** setting will end due to an iOS platform change. You will not be able to configure this setting in the Intune Admin Console and it will not be enforced on the client in the Intune App SDK.

<!-- 1903 start-->

### Windows Update notifications <!-- 3316782 -->
We're adding support to the Windows Update ring configurations so you'll be able to configure the Windows Update notifications your users see. This setting won't be available from within the portal, but can be configured by using the Intune Graph API.

### Easier access to Diagnostic Settings <!-- 3804627 -->
We’re adding a new option to the **Audit logs** blade in every Audit Log workload in the Intune console that you can use to directly open the *Diagnostic Settings* page.

## Notices

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.


