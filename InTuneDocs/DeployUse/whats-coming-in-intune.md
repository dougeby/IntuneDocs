---
# required metadata

title: What's coming | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/03/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# What's coming in Microsoft Intune
This information is provided under NDA on an extremely limited basis and is subject to change. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Please reach out to your Intune/PM buddy if you have any questions or concerns.

This page is updated periodically. Check back for new What’s Coming updates.

The following changes are under development for Intune. All of these features will also be supported for hybrid customers deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## Message Center onboarding
The [Office 365 Message Center](https://portal.office.com/default.aspx#MessageCenterPage) will replace Intune alerts for notifications about Intune. You will visit the Office 365 Message Center to see messages from Microsoft regarding new features being deployed as well as other one-off notifications.  The associated mobile app will allow you to also receive messages on your mobile phone and forward messages to your users by emailing individual users or distribution groups.
<!---TFS 1242782--->


## App management
<!--- - **Conditional access for browser.** You will be able to set a conditional access policy for Exchange Online and SharePoint Online so that they can only be accessed by managed and compliant iOS and Android devices. End users who try to sign in to Outlook Web Access (OWA) and SharePoint sites with iOS and Android devices will be prompted to enroll their device with Intune as well as to fix any non-compliance issues before they can complete sign-in.--->
<!---TFS 1175844--->

- **MAM SDK: Support PIN length configuration.** You will be able to specify the length of the PIN for MAM apps similar to a device PIN. This will require end users to comply with the new restrictions you set. They will see a slightly modified PIN screen to account for the longer input.
<!--- TFS 1104753--->

- **MAM controls to prevent Outlook contacts sync (iOS).** A new setting is available for mobile application management without device enrollment. This setting  allows the Intune administrator to prevent an application from syncing contacts to the native address book on iOS devices. When this setting is enabled, the app will no longer be able to save contacts to the native address book. When this setting is disabled, the app will be able to save contacts to the native address book. When an Intune administrator selectively wipes a device, all contacts that have already been saved to the native address book will be removed. This new setting is now supported by the Outlook application on iOS devices.
<!---TFS item 1276166--->

- **Skype for business for Android.** Intune Administrators can now target Skype for business with MAM without enrollment policies.  Once their users are logged in, the MAM policies will be applied.
<!--- TFS item 1248444 --->

- **Skype for business for iOS.** Intune Administrators can now target Skype for business with MAM without enrollment policies.  Once their users are logged in, the MAM policies will be applied.
<!--- TFS item 1248443 --->

### Xamarin support
The Microsoft Intune app SDK now supports Xamarin apps in these scenarios:

- Writing new apps, or modifying the code of existing line of business apps using the Intune SDK. You can get the plugin on the [Microsoft Intune Github](https://github.com/msintuneappsdk) page.
- Adding MAM support to existing line of business apps using the Intune app wrapping tool

For help choosing which method to use, see [Decide how to prepare apps for mobile application management with Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).
<!--- TFS 1061478 & TFS 1152340--->


## Device management
- **Remote assistance sessions for Windows PCs.** TeamViewer integration for Windows desktop agent-managed PCs will let you establish remote assistance sessions with Windows desktop agent-managed computers in support of end-user helpdesk departments. This includes Windows 7, 8, 8.1 and Windows 10.
<!--- TFS 1284856--->

- **Intune support for iOS 9.3.** On Monday March 21st, Apple announced the availability of iOS 9.3. We have been busy working to ensure that Microsoft Intune is compatible with the latest version of Apple's mobile operating system, and [we are pleased to announce that Intune supports managing iOS 9.3 devices](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

    All existing Intune features currently available for managing iOS devices will continue to work seamlessly as users upgrade their devices to iOS 9.3. In addition, iOS 9.3 is also supported today for hybrid customers (Configuration Manager integrated with Intune).
<!--- TFS item 1274326 --->

## Access control
* **Skype for Business Online supports conditional access.** Intune administrators will be able to set a conditional access policy for Skype for Business Online so that it can only be accessed by managed and compliant iOS and Android devices. End users who try to sign in to the Skype for Business mobile app on iOS and Android will be prompted to enroll with Intune as well as fix any non-compliance issues before sign-in can complete.
<!---TFS item 1254499--->

## Company Portal
* **Device identification banner will provide more information to end users.** End users will be ablet to easily identify the device they’ve selected when they are using the Company Portal website. If the wrong device is selected, they will be able to select the correct device by tapping the “Tap here” link in the home page banner.
<!--- TFS 1231157--->

* **Windows app packages available directly from the Company Portal**: Users of Windows 8, Windows 8.1, and Windows RT PCs can now install Windows app packages (with the .appx extension) directly from the Company Portal website. Previously, Intune administrators had to deploy, or users had to install the Company Portal app on their devices to install apps.
<!--- TFS item 1082481 --->

* **Users can remotely lock their device from the Company Portal** A new remote lock option has been added to the Company Portal website to enable end users to remotely lock their device from the portal if their device is lost or stolen. The following table lists the platform support for remote lock for Intune and Intune with Configuration Manager.
<!--- TFS item 1195661 --->

|Platform  |Support details|
|---------|---------|
|iOS | Supported|
|Android | Supported|
|Windows Phone 8.1 | Supported|
|Windows 10 Mobile | Supported only if the phone has a passcode set|
|PC (Windows 8.0 and earlier) | Not supported|
|PC (Windows 8.1) | Not supported|
|Windows Phone 8.0 | Not Supported|
|Windows 10 Desktop | Not supported|

## Service deprecation
* **Custom Group Targeting of Notification Rules Removal.** Coming in early June, 2016, you will no longer be able to use the Create Notification Rule Wizard to target user-created groups with notification rules.

    Currently, to target a user-created group from the Microsoft Intune administration console, you choose **Admin** > **Notification Rules** > **Create New Rule**. In step two of the Create Notification Rule Wizard, you must select the device groups which the rule will target. This step, **Select device groups**, is being deprecated from the Intune Console.

    **Select device groups** will no longer be supported after the June 1606 release of Intune. However, you will continue to see this option until August 2016. After August, we will begin phasing our tenants to the new experience over a period of two months. By October 2016, all existing customers should be transitioned to the new experience. After migrating to the new experience, you will no longer be presented with the option to target notification rules at a specific group.
<!---	TFS 1278864--->







### See also
See [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md) for  details on recent developments.
