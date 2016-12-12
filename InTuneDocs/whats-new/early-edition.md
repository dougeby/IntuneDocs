---
# required metadata

title: The Early Edition | Microsoft Docs
description:
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/16/2016
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

# The Early Edition for Microsoft Intune - January

The **Early Edition** provides a list of features that are coming in upcoming releases of Microsoft Intune. This information is provided under NDA on an extremely limited basis and is subject to change. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Please reach out to your Intune/PM buddy if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

The following changes are under development for Intune. All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## New Capabilities

__Actions for non-compliance__<!--730266-->
_Actions for non-compliance_ is a new feature of compliance policies that lets you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.

__In-console reports available for MAM without enrollment__<!--677961-->
Detailed app protection reporting will offer two new, improved, in-console reports:

    * Managed users
    * Unmanaged users

For each user, you can get details on:

    * Policies on those apps
    * Device name/type
    * Last used

__Android 7.1.1 support for Intune__<!--694397-->
Intune fully supports Android 7.1.1 for Android devices in MDM scenarios.

## Notices

__Company Portal for iOS links open inside the app__ <!--665954-->
Links inside of the Company Portal app for iOS, including those to documentation and apps, will open directly in the Company Portal app using an in-app view of Safari. This update will ship separately from the service update in January.

__Improving mobile app management support for selective wipe__<!--581242-->
End users will be given additional guidance on how to regain access to work or school data if that data is automatically removed due to the "Offline interval before app data is wiped" policy, or the removal of the Intune Company Portal on Android.

## Deprecations

__Defaulting to managing Windows desktop devices through Windows settings__<!--663050-->
The Company Portal website will provide Windows 10 desktop users with enrollment instructions that guide them through the process of adding a work or school account via Windows settings. This method of enrollment allows Intune to manage Windows 10 desktop computers as mobile devices.

If your organization wants to manage Windows 10 desktops as PCs, click [here](https://docs.microsoft.com/en-us/intune/deploy-use/manage-windows-pcs-with-microsoft-intune) to learn more about how the Intune client can be installed and used on those devices.

### See also
See [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md) for details on recent developments.
