---
title: What&#39;s coming in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
author: Lindavr
robots: noindex,nofollow
---
# What&#39;s coming in Microsoft Intune
This information is provided under NDA on an extremely limited basis and is subject to change. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Please reach out to your Intune/PM buddy if you have any questions or concerns.
## New in service
The following changes are under development for Intune: 
### App management

- **Take advantage of iOS "Open-in" management for devices that are not enrolled in Intune.** Intune administrators can use their third-party mobile device management (MDM) vendor to take advantage of iOS "Open-In" management. You can send an App Config setting to the app to tell it what work account is required.  

	This approach has two main benefits:

	1. Users are required to log in with their work account before they get access to any corporate data from Cloud Services or other apps. This ensures that mobile app management (MAM) policies are in place when the data is accessed.

	2. Managed native email profiles and other iOS-managed apps can share files and data with the Intune MAM-managed apps. 
	
- **Mobile app configuration policies give you more flexibility to specify user details for iOS apps.** Intune administrators can supply user settings that an iOS app might need when it is opened. For example, you can supply a network port, or a user name. 

- **Deploy Adobe Reader for Microsoft Intune to Intune-managed iOS devices in your enterprise.** When Intune administrators deploy Adobe Reader, they are able to select a MAM policy to be enforced by the app on the device. The MAM policy allows the app to share data with other apps that also have a MAM policy deployed and enforced, such as Microsoft Office apps. 

- **Ensuring deployed web clips are opened in a managed browser.** Intune administrators can deploy targeted web clips that can only be opened using the managed browser on iOS and Android devices. For example, you deploy links to corporate resources through the Company Portal, and when users navigate to the links, they  open directly into the managed browser where they are protected by MAM policy.  

- **The Rights Management sharing app is supported for Android.** IT administrators can deploy mobile application management policies so end users can view images, AV, and PDF files more securely, whether or not IT uses Intune to manage the devices. 

- **Find, manage, and distribute Windows Store for Business apps for Windows 10 devices from the Intune administrator console.** Support for Windows Store for Business is available in Intune to help you find, manage, and distribute apps to the Windows 10 devices you’re managing. Windows Store for Business lets you manage the process of deploying and monitoring these apps from the Intune administrator console—the same console you use to manage your other apps. Specifically, Windows Store for Business manages the content and licensing  of “online licensed apps”.

### Device management
- **PFX certificates distribution for iOS devices.** Intune administrators can create and deploy iOS PFX certificates for Wi-Fi, email, and VPN authentication on iOS devices. This feature is already available for Android and Windows 10 devices.

- **Apply apps and policies to different device categories based on user selection**
Intune administrators can now define custom device categories for users to select from during enrollment. For example, administrators might want their users to specify if they're enrolling a device used for the "Cash Register" or "Delivery Truck" or "Inventory Room." The category selected will cause the device to become a member of an Intune device group, which can be used for deploying different apps and policies to the enrolled device.


## Changes and updates to Microsoft Company Portal
The following changes are under development for the Company Portal apps:

### iOS
- **Enrollment error messages will now be displayed in the Company Portal.** End users will see their enrollment error messages displayed in the Company Portal app instead of in the Company Portal website.

### iOS and Android
- **New enrollment flow checklist design for end users of iOS and Android.** The enrollment flow has been improved to a checklist-style design with descriptive screens to provide information about the enrollment process, as currently documented on the Intune notice board.



