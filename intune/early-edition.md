---
# required metadata

title: Early edition
description:
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 01/18/2018
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

# The early edition for Microsoft Intune - January 2018

The **early edition** provides a list of features that are coming in upcoming releases of Microsoft Intune. This information is provided on a limited basis and is subject to change. Do not share this information outside of your company. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Reach out to your Microsoft product group contact if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

> [!Note]
>The following changes are under development for Intune. For more information about new hybrid features, check out the [hybrid What’s New page](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->


## Intune in the Azure portal

### Easier resolution of compliance issues for the Company Portal app for Windows 10 <!--676546 -->

End users with Windows devices will be able to tap the non-compliance reason in the Company Portal app. When possible, this will take them directly to the correct location in the settings app to fix the issue.

### New option for user authentication for Apple bulk enrollment <!-- 747625 -->
Intune will give you the option to authenticate devices by using the Company Portal app for the following enrollment methods:

- Apple Device Enrollment Program
- Apple School Manager
- Apple Configurator Enrollment

When using the Company Portal option, Azure Active Directory multi-factor authentication can be enforced without blocking these enrollment methods.

When using the Company Portal option, Intune skips user authentication in the iOS Setup Assistant for user affinity enrollment. This means that the device is initially enrolled as a userless device, and so won't receive configurations or policies of user groups. It will only receive configurations and policies for device groups. However, Intune will automatically install the Company Portal app on the Device. The first user to launch and sign in to the Company Portal app will be associated with the device in Intune. At this point, the user will receive configurations and policies of their user groups. The user association cannot be changed without re-enrollment.

### Intune support for multiple Apple DEP / Apple School Manager accounts <!-- 747685 -->
Intune will support enrolling devices from up to 100 different Apple Device Enrollment Program (DEP) or Apple School Manager accounts. Each token uploaded can be managed separately for enrollment profiles and devices. A different enrollment profile can be automatically assigned per DEP/School Manager token uploaded. If multiple School Manager tokens are uploaded, only one can be shared with Microsoft School Data Sync at a time.

After migration, the beta Graph APIs and published scripts for managing Apple DEP or ASM over Graph will no longer work. New beta Graph APIs are in development and will be released after the migration.

### Select device categories by using the Access Work or School settings <!-- 1058963 eeready -->
If you've enabled [device group mapping](https://docs.microsoft.com/en-us/intune/device-group-mapping), users on Windows 10 will be prompted to select a device category after enrolling through the **Connect** button in **Settings** > **Accounts** > **Access work or school** or during the out-of-box experience.

### Targeting compliance policies to devices in device groups <!--1307012 -->

You will be able to target compliance policies to users in user groups. You'll be able to target compliance policies to devices in device groups.

### Windows Information Protection (WIP) encrypted data in Windows search results <!-- 1469193 -->

A new setting in the Windows Information Protection (WIP) policy will allow you to control whether WIP-encrypted data is included in Windows search results.

### Remote printing over a secure network <!-- 1709994  -->
PrinterOn’s wireless mobile printing solutions will enable users to remotely print from anywhere at any time over a secure network. PrinterOn will integrate with the Intune APP SDK for both iOS and Android. You will be able to target app protection policies to this app through the Intune **App protection policies** blade in the admin console. End users will be able to download the app 'PrinterOn for Microsoft' through the Play Store or iTunes to use within their Intune ecosystem.



### Microsoft Graph API for Intune - General Availability  <!-- 1833289 -->
Intune APIs in Microsoft Graph will provide programmatic access to data and methods for automating administrative actions for the Intune service.  With the **General Availability** of these APIs, customers, partners, and developers will be able to leverage the APIs to integrate with in-house or commercial solutions relating to or requiring the support of Intune, or other Microsoft services available through Microsoft Graph.

<!-- the following are present prior to 1801 -->

### App Protection Policies  <!-- 679615 -->
Intune App Protection Policies will offer the ability to create global, default policies to quickly enable protection across all users in the entire tenant.

### New iOS device action   <!-- 1244701 -->
You can shut down iOS 10.3 supervised devices. This action shuts down the device immediately without warning to the end user. The **Shut down (supervised only)** action can be found at the device properties when you select a device in the **Device** workload.


### Intune now provides the Account Move operation  <!-- 1573558, 1579830 -->
The **Account Move** migrates a tenant from one Azure Scale Unit (ASU) to another. The **Account Move** can be used for both customer-initiated scenarios, when you call the Intune support team requesting it, and it can also be a Microsoft-driven scenario where Microsoft needs to make adjustments to the service in the back-end. During the **Account Move**, the tenant enters in read-only mode (ROM). Service operations like enrolling, renaming devices, updating compliance status will fail during the ROM period.




<!-- the following are present prior to 1712 -->



The change addresses the confusion when one app is assigned to multiple groups with different app intents.

If you would like to have your app available in the Information Worker Portal and the Company Portal before the November service release, you have two options:

1. Remove the **Not Applicable** assignment for your group.
2. Create a new group that does not include members with **Required and Available** intent assigned and assign that group as **Not Applicable**.

For more information, see [How to assign apps to groups with Microsoft Intune](apps-deploy.md).

> [!Note]
> After the release you will no longer be able to view or modify Mobile Device Management (MDM) app assignments in the Intune classic console. However, you can use Azure console or the Intune Graph API to make your app assignments.

### Manage Android for Work devices independently from Android devices <!-- 1490731 -->
Intune will support managing enrollment of Android for Work devices independently from the Android platform. These settings are managed under **Device Enrollment** > **Enrollment restrictions** > **Device Type Restrictions**. (They were previously located under **Device Enrollment** > **Android for Work Enrollment** > **Android for Work Enrollment Settings**.)

By default, your Android for Work devices settings will be the same as your settings for your Android devices. However, after you change your Android for Work settings that will no longer be the case.
 
If you block personal Android for Work enrollment, only corporate Android devices can enroll as Android for Work.

When working with the new settings, consider the following issues:

#### If you have never previously onboarded Android for Work enrollment
The new Android for Work platform is blocked in the default Device Type Restrictions. After you onboard the feature, you can allow devices to enroll with Android for Work. To do so, change the default or create a new Device Type Restriction to supersede the default Device Type Restriction.

#### If you have onboarded Android for Work enrollment
If you’ve previously onboarded, your situation depends on the setting you chose:

| Setting | Android for Work status in default Device Type Restriction | Notes |
| --- | --- | --- |
| **Manage all devices as Android** | Blocked | All Android devices must enroll without Android for Work. |
| **Manage supported devices as Android for Work** | Allowed | All Android devices that support Android for Work must enroll with Android for Work. |
| **Manage supported devices for users only in these groups as Android for Work** | Blocked | A separate Device Type Restriction policy was created to override the default. This policy defines the groups you previously selected to allow Android for Work enrollment. Users within the selected groups will continue to be allowed to enroll their Android for Work devices. All other users are restricted from enrolling with Android for Work. |

In all cases, your intended regulation is preserved. No action is required on your part to maintain the global or per-group allowance of Android for Work in your environment.

These changes will begin rollout with the November update, but may take time to execute on your account. You will receive a confirmation notification in the Office 365 portal when these changes are effective for your account.


### Configure an iOS app PIN <!-- 1586774 -->
Soon you will be able to require a PIN for targeted iOS apps. You can configure the PIN requirement and expiration date in days through the Azure portal. When required, a user will be required to set and use a new PIN before getting access to an iOS app. Only iOS apps that have app protection enabled with the Intune App SDK will support this feature.

### User experience update for the Company Portal app for iOS <!--1412866-->

We will be releasing a major user experience update to the Company Portal app for iOS. The update will feature a complete visual redesign, which includes a modernized look and feel with increased usability and accessibility. All current iOS Company Portal functionality will be maintained.

We are offering a pre-release version of the updated Company Portal app for iOS through the Apple TestFlight program for you to use and to provide feedback. Sign up at https://aka.ms/intune_ios_cp_testflight for TestFlight access. 

![teaser images for new ios company portal app](./media/ios-cp-app-redesign-1801-teaser.png)


<!-- the following are present prior to 1711 -->

### Azure Active Directory web sites can require the Intune Managed Browser App and support Single Sign-On for the Managed Browser (Public Preview) <!-- 710595 -->   
Using Azure Active Directory (Azure AD), you will be able to restrict access to web sites on mobile devices to the Intune Managed Browser app. In the managed browser, web site data will remain secure and separate from end-user personal data. In addition, the Managed Browser will support Single Sign-On capabilities for sites protected by Azure AD. Signing in to the Managed Browser, or using the Managed Browser on a device with another app managed by Intune, allows the Managed Browser to access corporate sites protected by Azure AD without the user having to enter their credentials. This functionality applies to sites like Outlook Web Access (OWA) and SharePoint Online, as well as other corporate sites like intranet resources accessed through the Azure App Proxy.


<!-- the following are present prior to 1709 -->


### Intune App Protection and Citrix MDX Development Tools <!-- 709185 -->
You can manage devices and apps with a combination of Citrix XenMobile MDX and Microsoft Intune. This allows you to manage apps with Intune app protection policy while using Citrix’s mVPN technology.

You are able to find a code repository that contains the Intune App Wrapping Tool and Intune App SDK for iOS and Android, integrating with Citrix MDX mVPN technology.




<!-- the following are present prior to 1711 -->


### Redirecting macOS users to the new Company Portal app <!--1380728-->   
When an end user logs into the Company Portal website to enroll their macOS device, they will be directed to download the new Company Portal app for macOS to complete the process. This occurs for macOS devices using OS X El Capitan 10.11 or above. 



<!-- the following are present prior to 1709 -->

### Intune Managed Browser support for iOS and Android <!-- 1374196 -->
As of October 2017, the Intune Managed Browser app on Android app will support only devices running Android 4.4 and later. The Intune Managed Browser app on iOS will support only devices running iOS 9.0 and later. Earlier versions of Android and iOS will be able to continue using the Managed Browser, but will be unable to install new versions of the app and might not be able to access all of the app capabilities. We encourage you to update these devices to a supported operating system version.


### Improved error message for when a user reaches the maximum number of devices allowed to enroll <!-- 1270370 -->
Instead of a generic error message, end users with Android devices see a friendly, actionable error message: "You have enrolled the maximum number of devices allowed by your IT admin. Please remove an enrolled device or get help from your IT admin."




## Notices

There are no active notices at this time.




### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.
