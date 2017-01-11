---
# required metadata

title: What's new | Microsoft Docs
description: Find out what’s new in this month’s, and past releases of Microsoft Intune
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/11/2017
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
# What's new in Microsoft Intune - January 2017
Learn what’s new in this release of Microsoft Intune. You can also find out about upcoming changes that you should be planning for, as well as information about past releases.

> [!Note]
> All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## New Capabilities

<!--### Actions for non-compliance <!--730266
_Actions for non-compliance_ is a new feature of compliance policies that lets you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.-->

### In-console reports for MAM without enrollment <!--677961-->
New app protection reports have been added for both enrolled devices and devices that have not been enrolled. Find out more about how you can [monitor mobile app management policies with Intune here](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

<!--### Conditional access for MAM with SharePoint Online <!--679339
You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint Online.  You can get started using Intune mobile app management in the Azure portal. Look for the __Conditional Access__ section in the __Settings__ blade which will include the option for SharePoint Online. This feature will ship separately from the rest of the service release. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### Android 7.1.1 support <!--694397-->
Intune now fully supports and manages Android 7.1.1.

### Resolve issue where iOS devices are inactive, or the admin console cannot communicate with them

When users’ devices lose contact with Intune, you can give them new troubleshooting steps to help them regain access to company resources. See [Devices are inactive, or the admin console cannot communicate with them](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## Notices

### Defaulting to managing Windows desktop devices through Windows settings <!--663050-->
The default behavior for enrolling Windows 10 desktops is changing. New enrollments will follow the typical MDM agent enrollment flow rather than through the PC agent.

The Company Portal website will provide Windows 10 desktop users with enrollment instructions that guide them through the process of adding Windows 10 desktop computers as mobile devices. This will not impact currently enrolled PCs, and your organization can still manage Windows 10 desktops using the PC agent [if you prefer](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

<!--### Company Portal for iOS links open inside the app <!--665954
Links inside of the Company Portal app for iOS, including those to documentation and apps, will open directly in the Company Portal app using an in-app view of Safari. This update will ship separately from the service update in January.-->

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

<!--### Progress bar when launching the Company Portal on iOS <!--665978
The Company Portal for iOS is introducing a progress bar on the launch screen to provide the user with information about the loading processes that occur. There will be a phased rollout of the progress bar to replace the spinner. This means that some of your users will see the new progress bar while others will continue to see the spinner.-->

## What's new in the public preview of the Intune admin experience on Azure <!--736542-->

In early calendar year 2017 we will be migrating our full admin experience onto Azure, allowing for powerful and integrated management of core EMS workflows on a modern service platform that’s extensible using Graph APIs.

New trial tenants will start to see the public preview of the new admin experience in the Azure portal this month. While in preview state, capabilities and parity with the existing Intune console will be delivered iteratively.

The admin experience in the Azure portal will use the already announced new grouping and targeting functionality; when your existing tenant is migrated to the new grouping experience you will also be migrated to preview the new admin experience on your tenant. In the meantime, if you want to test or look at any of the new functionality until your tenant is migrated, sign up for a new Intune trial account or take a look at the [new documentation](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

If you have any questions about the timeline for your tenant’s migration, contact our migration team at [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

You can find what's new in the Intune preview in Azure [here](https://docs.microsoft.com/intune-azure/introduction/whats-new).

### See also
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [What's new in the Azure preview](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [What's new archive](whats-new-archive.md)
