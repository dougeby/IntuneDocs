---
# required metadata

title: Early edition | Microsoft Docs
description:
keywords:
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
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
ms.custom: intune-classic

---

# The early edition for Microsoft Intune - May 2017

The **Early Edition** provides a list of features that are coming in upcoming releases of Microsoft Intune. This information is provided under NDA on an extremely limited basis and is subject to change. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Please reach out to your Intune/PM buddy if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

> [!Note]
> The following changes are under development for Intune. All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## New capabilities

### Single sign-on support from the Company Portal for iOS to Outlook for iOS <!--834012-->

Users will no longer have to sign in to the Outlook app if they are signed in to the Company Portal app for iOS on the same device with the same account. When users launch the Outlook app, they will be able to select their account and automatically sign in. We are also working toward adding this functionality for other Microsoft apps.

### Improved notification for Samsung KNOX startup PINs <!--1087143-->

When end users need to set a start-up PIN on Samsung KNOX devices in order to become compliant with encryption, the notification displayed to end users will bring them to the exact place in the Settings app when the notification is tapped.  Previously, the notification brought the end user to the password change screen.

### Promoting the most current version of the Company Portal for Android <!--1098661-->

End users will see an in-app notification when a new recommended version of the Company Portal app for Android has been released in the app's Notifications screen. This notification will tell users that a "Company Portal update is available." Tapping the notification will open a webpage showing the list of available app stores where they can download the updated version. 

### Improvements to app syncing with Windows 10 Creators Update <!-- 676505 -->

The Company Portal for Windows 10 will automatically initiate a sync for app install requests for devices with Windows 10 Creators Update (1704). This will reduce the issue of app installs stalling during the "Pending Sync" state. In addition, users will be able to manually initiate a sync from within the app. 

The Company Portal for Windows 10 will also expose a refresh button to allow the user to refresh the content in the app whenever they need. 

## Notices

### Apple to require updates for Application Transport Security <!--748318-->

Beginning in Spring 2017, Apple has announced that they will enforce specific requirements for Application Transport Security (ATS). ATS is used to enforce stricter security on all app communications over HTTPS. This change impacts Intune customers using the iOS Company Portal apps. Review our [Intune support blog](https://aka.ms/compportalats) for more details.

### Direct access to Apple enrollment scenarios <!--951869-->

For Intune accounts created after January 2017, Intune has enabled direct access to Apple enrollment scenarios using the Enroll Devices workload in the Azure Preview portal. Previously, the Apple enrollment preview was only accessible from links in the classic Intune portal. Intune accounts created before January 2017 will require a one-time migration before these features are available in Azure. The schedule for migration has not been announced yet, but details will be made available as soon as possible. We strongly recommend creating a trial account to test out the new experience if your existing account cannot access the preview.

### What's coming for Appx in Intune on Azure <!-- 1000270 -->

As part of the migration to Intune on Azure, we are making three appx changes:

1. Adding a new appx app type in the classic Intune console that can only be deployed to MDM-enrolled devices.
2. Repurposing the existing appx app type to only be targeted to PCs managed through the Intune PC agent.
3. Converting all existing appxs into MDM appxs with the migration.

This will not impact any of your existing deployments to devices that are managed through the Intune PC agent. However, after migration, you will not be able to deploy those migrated appxs to any new devices that are managed through the Intune PC agent that were not previously targeted.

After migration, you will need to re-upload the appx again as a PC appx if you want to do new PC deployments. To learn more, see [Appx changes in Intune on Azure](https://aka.ms/appxchange) on the Intune Support team blog.  


## Public preview of the new Intune admin experience on Azure <!--736542-->

In early calendar year 2017 we will be migrating our full admin experience onto Azure, allowing for powerful and integrated management of core EMS workflows on a modern service platform that’s extensible using Graph APIs.

New trial tenants will start to see the public preview of the new admin experience in the Azure portal this month. While in preview state, capabilities and parity with the existing Intune console will be delivered iteratively.

The admin experience in the Azure portal will use the already announced new grouping and targeting functionality; when your existing tenant is migrated to the new grouping experience you will also be migrated to preview the new admin experience on your tenant. In the meantime, if you want to test or look at any of the new functionality until your tenant is migrated, sign up for a new Intune trial account or take a look at the [new documentation](https://docs.microsoft.com/intune/what-is-intune).

### Support for managed configuration options for Android apps <!-- 621621 -->

You will be able to configure Android apps in the Play store that support managed configuration options.  This feature lets you view the list of configuration values supported by an app, and provides a guided, first-class UI to allow them to configure those values.

### Remote assistance for Android devices <!-- 675418 -->

Intune will use the [TeamViewer](https://www.teamviewer.com) software, purchased separately, to enable you to give remote assistance to your users who are running Android devices.

### Preconfigure device permissions for Android for Work apps <!-- 621614 -->

For apps deployed to Android for Work device work profiles, you will be able to configure the permissions state for individual apps. By default, Android apps that require device permissions such as access to location or the device camera will prompt users to accept or deny permissions.  For example, if an app uses the device's microphone, then the end user is prompted to grant the app permission to use the microphone. This feature will allow you to define permissions on behalf of the end user.  The admin can configure permissions to

- Automatically deny without notifying the user
- Automatically approve without notifying the user
- Prompt the user to accept or deny.

### Define app-specific PIN for Android for Work devices <!--728976-->

You will be able to define a passcode policy that only applies to apps in the work profile for Android 7.0 and above devices managed as an Android for Work device.  Options include:

- Define just a device-wide passcode policy - This is the passcode that the end user must use to unlock their entire device
- Define just a work profile passcode policy - end users will be prompted to enter a passcode whenever any app in the work profile is opened.
- Define both a device and and work profile policy - IT has the choice to define both a device passcode policy and a work profile passcode policy at differing strengths (eg, a 4 digit PIN to unlock the device, but a 6 digit PIN to open any work app)

>[!NOTE]
> This will only be available on Android 7.0 and above.  By default, the end user will have the option to use the two separately defined PINs or they can elect to combine the two defined PINs into the strongest of the two.

### Manage password and other Android for Work settings <!--1102534-->

We are adding a new Android for Work device restriction policy that lets you manage password and work profile settings on Android for Work devices.

###  New Web content filter policy for iOS devices <!-- 723832 -->

You will be able to control which websites users of iOS devices can visit using one of the following two methods:

  - Add permitted, and blocked URLs using Apples built-in web content filter.
  - Allow only specified websites to be accessed by the Safari browser. Bookmarks will be created in Safari for each site you specify.

### Apple School Manager (ASM) support <!--748864-->

Intune will support use of Apple School Manager (ASM) in place of Apple Device Enrollment Program to provide out-of-box enrollment of iOS devices. ASM onboarding is required to use the Classroom app for Shared iPads, and is required to enable syncing data from ASM to Azure Active Directory via Microsoft School Data Sync (SDS).  

### Shared iPad support <!--770395, 1044681 -->

Intune will support configuring Shared iPad mode in the enrollment profile for Apple's Device Enrollment Program or Apple School Manager. This setting lets multiple managed Apple IDs to sign into the same device.

We'll also be expanding the support for managing the iOS Classroom app to include students who log into shared iPads using their managed Apple ID.

### New Windows device restriction settings <!--978585-->

We're adding settings to the Windows device restriction profile that control features like wireless displays, device discovery, task switching, and SIM card error messages.

### Office 365 ProPlus app available for Windows 10 devices <!--1121362-->

We're adding the new Office 365 ProPlus app type that makes it easy for you to assign Office 365 ProPlus apps to Windows 10 devices. Additionally, you will also be able to install Microsoft Project, and Microsoft Visio, if you own licenses for them. The apps you want will be bundled together and appear as one app in the list of apps in the Intune console.

### New allow/block list for the Managed Browser <!--682960-->

You will be able to configure the allow/block list of domains and URLs for the Managed Browser with the Intune Application Configuration settings in the Azure portal. This can be configured for the Managed Browser regardless of whether it is being used on a managed or unmanaged device.

### New app configuration capabilities <!-- 677969 -->

This feature will be equivalent to mobile device management (MDM) app configuration. It allows admins to apply more app configuration values that just the app configuration values available through app protection policies in the MAM without enrollment channel.

### New app protection policies conditions for MAM <!--679864-->

You will be able to set a requirement for MAM without enrollment users through the Admin Console that enforces the following:

- Minimum application version
- Minimum operating system version
- Minimum Intune APP SDK version of the targeted application (iOS only)

This feature will be available on both Android and iOS. Intune supports minimum version enforcement for OS platform versions, application versions, and Intune APP SDK. On iOS, applications that have the SDK integrated can also set a minimum version enforcement at the SDK level.

The user will be unable to access the targeted application if the minimum requirements through the app protection policy are not met at the 3 different levels mentioned above. At this point, the user may either remove their account (for multi-identity applications), close the application and/or update their OS or application version to meet the requirement.

Furthermore, you will also be able to configure additional settings through the Admin Console to provide a non-blocking notification that recommends an OS or application upgrade. This notification can be closed and the application may be used as normal.

### Change your MDM authority without unenrolling managed devices <!--1103950-->

You will be able to change your MDM authority without having to contact Microsoft Support, and without having to unenroll and reenroll your existing managed devices. In the Configuration Manager console, you can change your MDM authority from Set to Configuration Manager (hybrid) to Microsoft Intune (standalone) or vice versa.


### See also
See [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md) for details on recent developments.
