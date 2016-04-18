---
title: What's coming | Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid:
author: Lindavr
---
# What's coming in Microsoft Intune
This information is provided under NDA on an extremely limited basis and is subject to change. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Please reach out to your Intune/PM buddy if you have any questions or concerns.

This page is updated periodically. Check back for new What’s Coming updates.

The following changes are under development for Intune. With the exception of the update to the Windows 10 general configuration policy, all of these features will also be supported today for hybrid customers (Configuration Manager integrated with Intune). Hybrid support for the Windows 10 general configuration policy update is coming soon. Please note that some of these features may require the latest version of Configuration Manager.
## App management

- **MAM controls to prevent Outlook contacts sync (iOS).** A new setting is available for mobile application management without device enrollment. This setting  allows the Intune administrator to prevent an application from syncing contacts to the native address book on iOS devices. When this setting is enabled, the app will no longer be able to save contacts to the native address book. When this setting is disabled, the app will be able to save contacts to the native address book. When an Intune administrator selectively wipes a device, all contacts that have already been saved to the native address book will be removed. This new setting is now supported by the Outlook application on iOS devices.
<!---TFS item 1276166--->

- **Skype for business for Android.** Intune Administrators can now target Skype for business with MAM without enrollment policies.  Once their users are logged in, the MAM policies will be applied.
<!--- TFS item 1248444 --->

- **Skype for business for iOS.** Intune Administrators can now target Skype for business with MAM without enrollment policies.  Once their users are logged in, the MAM policies will be applied.
<!--- TFS item 1248443 --->

- **The Rights Management sharing app is supported for Android.** Intune administrators can deploy mobile application management policies so end users can view images, AV, and PDF files more securely, whether or not IT uses Intune to manage the devices.

## Device management
- **Intune support for iOS 9.3.** On Monday March 21st, Apple announced the availability of iOS 9.3. We have been busy working to ensure that Microsoft Intune is compatible with the latest version of Apple's mobile operating system, and [we are pleased to announce that Intune supports managing iOS 9.3 devices](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

    All existing Intune features currently available for managing iOS devices will continue to work seamlessly as users upgrade their devices to iOS 9.3. In addition, iOS 9.3 is also supported today for hybrid customers (Configuration Manager integrated with Intune).
<!--- TFS item 1274326 --->


- The **Windows 10 general configuration policy** now contains settings to manage Windows Defender on enrolled Windows 10 PCs.
<!--- 1244446 --->

## Access control
* **Skype for Business Online supports conditional access.** Intune administrators will be able to set a conditional access policy for Skype for Business Online so that it can only be accessed by managed and compliant iOS and Android devices. End users who try to sign in to the Skype for Business mobile app on iOS and Android will be prompted to enroll with Intune as well as fix any non-compliance issues before sign-in can complete.
<!---TFS item 1254499--->

## Company Portal
* **Windows app packages available directly from the Company Portal**: Users of Windows 8, Windows 8.1, and Windows RT PCs can now install Windows app packages (with the .appx extension) directly from the Company Portal website. Previously, Intune administrators had to deploy, or users had to install the Company Portal app on their devices to install apps.
<!--- TFS item 1082481 --->

* **Users can remotely lock their device from the Company Portal** A new remote lock option has been added to the Company Portal website to enable end users to remotely lock their device from the portal if their device is lost or stolen. The following table lists the platform support for remote lock for Intune and Intune with Configuration Manager.
<!--- TFS item 1195661 --->


Platform  |Support details
---------|---------
iOS | Supported
Android | Supported
Windows Phone 8.1 | Supported
Windows 10 Mobile | Supported only if the phone has a passcode set
PC (Windows 8.0 and earlier) | Not supported
PC (Windows 8.1) | Not supported
Windows Phone 8.0 | Not Supported
Windows 10 Desktop | Not supported




### See also
See [What’s New in Microsoft Intune](https://technet.microsoft.com/library/dn292747.aspx) for  details on recent developments.
