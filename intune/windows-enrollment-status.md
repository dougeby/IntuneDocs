---
# required metadata

title: Set up an enrollment status page
titleSuffix: Microsoft Intune
description: Greet your users who are enrolling Windows 10 devices.
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/17/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
 
# optional metadata
 
#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
 
---
 
# Set up an enrollment status page
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
During device setup, the enrollment status page displays installation status information on the end user's device. Some applications, profiles, and certificates might not be fully installed by the time a user is enrolled. The status page can help users understand the status of their device during and after enrollment. You can turn on the status page for all your users, as well as prevent users from using the device until all the assigned applications and profiles are installed.
 
To turn on the enrollment status page for all your end users, follow the steps below.
 
1.  In [Intune](https://aka.ms/intuneportal), choose **Device enrollment** > **Windows enrollment** > **Enrollment Status Page (Preview)**.
2.  In the **Enrollment Status Page** blade, choose **Default** > **Settings**.
3.  For **Show app and profile installation progress**, choose **Yes**.
4.  Choose the other settings that you want to turn on and then choose **Save**.
 
## Enrollment status page tracking information

The status page tracks information for device preparation, device setup, and account setup.

### Device preparation

For device preparation, the enrollment status page tracks Trusted Platform Module (TPM) key attestations (when applicable), progress in joining Azure Active Directory, and enrolling into Intune.

### Device setup

For device setup, the enrollment status page tracks the following items if they are assigned to All Devices:
- Security policies
    - One configuration service provider (CSP) for all enrollments.
    - Actual CSPs configured by Intune are not tracked here.
- Applications
    - Per machine Line-of-business (LoB) MSI apps.
    - LoB store apps with installation context = Device.
    - Offline store and LoB store apps with installation context = Device.
- Connectivity profiles (VPN and Wi-Fi) are not tracked yet, so these will always say "0 of 0".
- Certificates are not tracked yet, so these will always say "0 of 0".

### Account setup
For account setup, the enrollment status page tracks the following items:
- Security policies
    - One CSP for all enrollments.
    - Actual CSPs configured by Intune are not tracked here.
- Applications
    - Per user LoB MSI apps that are assigned to All Devices, All Users, or a user group in which the user enrolling the device is a member.
    - Per machine LoB MSI apps that are assigned to All Users or a user group in which the user enrolling device is a member.
    - LoB store apps that are assigned to All Devices, All Users, or a user group in which the user enrolling the device is a member with installation context = User.
    - Online store apps that are assigned to All Devices, All Users, or a user group in which the user enrolling device is a member with installation context = User.
    - Offline store apps that are assigned to All Devices, All Users, or a user group in which the user enrolling device is a member with installation context = User.
- Connectivity profiles
    - VPN or Wi-Fi profiles that are assigned to All Users or a user group in which the user enrolling the device is a member.
- Certificates
    - Certificate profiles that are assigned to All Users or a user group in which the user enrolling the device is a member.

## Next steps
After you set up Windows enrollment pages, learn how to manage Windows devices. For more information, see [What is Microsoft Intune device management?](https://docs.microsoft.com/intune/device-management)