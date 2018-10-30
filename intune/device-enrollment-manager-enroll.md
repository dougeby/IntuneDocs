---
# required metadata

title: Enroll devices using a device enrollment manager account
titlesuffix: "Microsoft Intune"
description: Use the device enrollment manager account to enroll devices in Intune. "
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Enroll devices by using a device enrollment manager account

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Organizations can use Intune to manage large numbers of mobile devices with a single user account. The *device enrollment manager* (DEM) account is a special user account that can enroll up to 1,000 devices. You add existing users to the DEM account to give them the special DEM options. We recommend that you use devices enrolled through this account as shared devices rather than personal ("BYOD") devices.  

Users must exist in the [Azure portal](https://portal.azure.com) to be added as device enrollment managers. For optimal security, the DEM user shouldn't also be an Intune admin.

## Limitations of devices that are enrolled with a DEM account

Devices that are enrolled with a device enrollment manager account have the following limitations:

  - The DEM user can't unenroll DEM-enrolled devices on the device itself by using the Company Portal. The Intune admin can do unenroll.
  - Only the local device appears in the Company Portal app or website.
  - (iOS only) If you use DEM to enroll iOS devices, you can't use the [Apple Configurator with Setup Assistant](apple-configurator-setup-assistant-enroll-ios.md), [Apple Configurator with direct enrollment](apple-configurator-direct-enroll-ios.md), [Apple School Manager (ASM)](apple-school-manager-set-up-ios.md), or [Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md) to enroll devices. This means that you can't put the device in supervised mode and thus won't have access to some configuration options.
  - (Android only) There's a limit to the number of Android work profile devices that can be enrolled with a single DEM account. Up to 10 Android work profile devices may be enrolled per DEM account. This limitation doesn't apply to legacy Android enrollment.
  - Devices can install VPP apps if they have Apple VPP device licenses.
  


## Add a device enrollment manager

1.  In [Intune in the Azure portal](https://aka.ms/intuneportal), choose **Device enrollment** > **Device enrollment managers**.

2.  Select **Add**.

3.  On the **Add User** blade, enter a user principal name for the DEM user, and select **Add**. The DEM user is added to the list of DEM users.

## Permissions for DEM

Global or Intune Service Administrator Azure AD roles are required to
- complete tasks that are related to DEM enrollment in the Admin Portal
- see all DEM users despite RBAC permissions being listed and available under the custom User role.

A user without the Global Administrator or Intune Service Administrator role assigned, but who has read permissions for the Device Enrollment Managers role, can see only the DEM users they created. RBAC role support for these features will be announced in the future.


## Remove a device enrollment manager

When a device enrollment manager is removed:

-   Enrolled devices are unaffected and continue to be fully managed.
-   The removed DEM account credentials are still valid.
-   The removed DEM still can't wipe or retire devices.
-   The removed DEM can only enroll a number of devices up to the per-user limit configured by the Intune admin.

**To remove a device enrollment manager**

1. In [Intune in the Azure portal](https://aka.ms/intuneportal), choose **Device enrollment**, and then choose **Device enrollment managers**.
2. On the **Device enrollment managers** blade, select the DEM user, and select **Delete**.

