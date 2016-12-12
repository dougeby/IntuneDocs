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

> [!Note]
> The following changes are under development for Intune. All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## Public preview of the new Intune admin experience on Azure <!--736542-->

In early calendar year 2017 we will be migrating our full admin experience onto Azure, allowing for powerful and integrated management of core EMS workflows on a modern service platform that’s extensible using Graph APIs.

New trial tenants will start to see the public preview of the new admin experience in the Azure portal this month. While in preview state, capabilities and parity with the existing Intune console will be delivered iteratively.

The admin experience in the Azure portal will use the already announced new grouping and targeting functionality; when your existing tenant is migrated to the new grouping experience you will also be migrated to preview the new admin experience on your tenant. In the meantime, if you want to test or look at any of the new functionality until your tenant is migrated, sign up for a new Intune trial account or take a look at the new documentation.

If you have any questions about the timeline for your tenant’s migration, contact our migration team at [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

## New Capabilities

### Actions for non-compliance <!--730266-->
_Actions for non-compliance_ is a new feature of compliance policies that lets you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.

### In-console reports available for MAM without enrollment <!--677961-->
Detailed app protection reporting will offer two new, improved, in-console reports:

  * Managed users
  * Unmanaged users

For each user, you can get details on:

  * Policies on those apps
  * Device name/type
  * Last used

### Android 7.1.1 support for Intune <!--694397-->
Intune fully supports Android 7.1.1 for Android devices in MDM scenarios.

## Notices

### Company Portal for iOS links open inside the app <!--665954-->
Links inside of the Company Portal app for iOS, including those to documentation and apps, will open directly in the Company Portal app using an in-app view of Safari. This update will ship separately from the service update in January.

### Improving mobile app management support for selective wipe <!--581242-->
End users will be given additional guidance on how to regain access to work or school data if that data is automatically removed due to the "Offline interval before app data is wiped" policy, or the removal of the Intune Company Portal on Android.

## Deprecations

### Defaulting to managing Windows desktop devices through Windows settings <!--663050-->
The Company Portal website will provide Windows 10 desktop users with enrollment instructions that guide them through the process of adding a work or school account via Windows settings. This method of enrollment allows Intune to manage Windows 10 desktop computers as mobile devices.

If your organization wants to manage Windows 10 desktops as PCs, click [here](https://docs.microsoft.com/en-us/intune/deploy-use/manage-windows-pcs-with-microsoft-intune) to learn more about how the Intune client can be installed and used on those devices.

### See also
See [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md) for details on recent developments.
