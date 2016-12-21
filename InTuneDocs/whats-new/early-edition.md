---
# required metadata

title: The Early Edition | Microsoft Docs
description:
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/21/2016
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

The admin experience in the Azure portal will use the already announced new grouping and targeting functionality; when your existing tenant is migrated to the new grouping experience you will also be migrated to preview the new admin experience on your tenant. In the meantime, if you want to test or look at any of the new functionality until your tenant is migrated, sign up for a new Intune trial account or take a look at the [new documentation](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune).

If you have any questions about the timeline for your tenant’s migration, contact our migration team at [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### Custom app categories <!--748805 / 1701-->
You can now create, edit, and assign categories for apps you add to Intune. Currently, categories can only be specified in English.

### Assign line of business apps whether or not devices are enrolled <!--748803 / 1701-->
You can now assign line of business and apps from the store to users whether or not their devices are enrolled with Intune. If the users device is not enrolled with Intune, they must go to the Company Portal website to install it, instead of the Company Portal app.

### Telecom expense management integration in public preview of Azure portal<!--747605 / 1612-->
We are now beginning to preview integration with third-party telecom expense management (TEM) services within the Azure portal. You can use Intune to enforce limits on domestic and roaming data usage. We are beginning these integrations with [Saaswedo](http://www.saaswedo.com). To enable this feature in your trial tenant, please [contact Microsoft support](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

## New Capabilities

### Actions for non-compliance <!--730266-->
_Actions for non-compliance_ is a new feature of compliance policies that lets you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.

### In-console reports for MAM without enrollment <!--677961-->
New app protection reports have been added for both enrolled devices and devices that have not been enrolled. Find out more about how you can [monitor mobile app management policies with Intune here](https://docs.microsoft.com/en-us/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

### Conditional access for MAM with SharePoint Online <!--679339-->
You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint Online.  You can get started using Intune mobile app management in the Azure portal. Look for the __Conditional Access__ section in the __Settings__ blade which will include the option for SharePoint Online. This feature will ship separately from the rest of the service release. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### Android 7.1.1 support <!--694397-->
Intune now fully supports and manages Android 7.1.1.

## Notices

### Defaulting to managing Windows desktop devices through Windows settings <!--663050-->
The default behavior for enrolling Windows 10 desktops is changing. New enrollments will follow the typical MDM agent enrollment flow rather than through the PC agent.

The Company Portal website will provide Windows 10 desktop users with enrollment instructions that guide them through the process of adding Windows 10 desktop computers as mobile devices. This will not impact currently enrolled PCs, and your organization can still manage Windows 10 desktops using the PC agent [if you prefer](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

### Company Portal for iOS links open inside the app <!--665954-->
Links inside of the Company Portal app for iOS, including those to documentation and apps, will open directly in the Company Portal app using an in-app view of Safari. This update will ship separately from the service update in January.

### Improving mobile app management support for selective wipe <!--581242-->
End users will be given additional guidance on how to regain access to work or school data if that data is automatically removed due to the "Offline interval before app data is wiped" policy.<!--, or the removal of the Intune Company Portal on Android.-->

### New documentation for app protection policies <!--583398-->
We have updated our documentation for admins and app developers who want to enable app protection policies (known as MAM policies) in their iOS and Android apps using the Intune App Wrapping Tool or Intune App SDK.

The following articles have been updated:

* [Decide how to prepare apps for mobile application management with Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [Prepare iOS apps for mobile application management with the Intune App Wrapping Tool](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Get started with the Microsoft Intune App SDK](https://docs.microsoft.com/intune/develop/intune-app-sdk-get-started)
* [Intune App SDK for iOS developer guide](https://docs.microsoft.com/intune/develop/intune-app-sdk-ios)

The following articles are new additions to the docs library:

* [Intune App SDK Cordova Plugin](https://docs.microsoft.com/intune/develop/intune-app-sdk-cordova)
* [Intune App SDK Xamarin Component](https://docs.microsoft.com/intune/develop/intune-app-sdk-xamarin)

### Progress bar when launching the Company Portal on iOS <!--665978-->
The Company Portal for iOS is introducing a progress bar on the launch screen to provide the user with information about the loading processes that occur. There will be a phased rollout of the progress bar to replace the spinner. This means that some of your users will see the new progress bar while others will continue to see the spinner.

### See also
See [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md) for details on recent developments.
