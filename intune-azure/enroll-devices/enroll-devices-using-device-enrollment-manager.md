---
# required metadata

title: Enroll devices using the device enrollment manager in Microsoft Intune | Microsoft Docs
description: Use the device enrollment manager account to enroll devices in Intune. 
keywords:
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:
---

# Enroll devices using device enrollment manager in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Organizations can use Intune to manage large numbers of mobile devices with a single user account. The *device enrollment manager* (DEM) account is a special Intune account that can enroll up to 1,000 devices. Each enrolled device uses a single license. We recommend that you use devices enrolled through this account as shared devices rather than personal ("BYOD") devices. Users will not be able to use "native" email apps, for example. Licensing for DEM is per device, not per user.

As an example, you could assign a device enrollment manager user account to a store manager or supervisor to let them:

-   Enroll devices in Intune.

-   Sign in to the Company Portal to get company apps.

-   Install and uninstall software.

-   Configure access to company data.


**A device enrollment manager scenario:**
A restaurant wants point-of-sale tablets for its wait staff, and order monitors for its kitchen staff. The employees never need to access company data or sign in as users. The Intune admin creates a device enrollment manager account and enrolls the company-owned devices by using that account. Alternatively, the admin could give the device enrollment manager credentials to a restaurant manager, which would let the manager enroll and manage the devices.

The admin or manager can deploy role-specific apps to the restaurant devices. An admin can also select and retire retire the device from mobile device management.

Devices that are enrolled with a device enrollment manager account have the following limitations:
  - There is no specific device "user." Therefore, there is no email or company data access. However VPN, for example, could still provide device apps with access to data.
  - There is no conditional access because these are per-user scenarios.
  - You can't reset these devices from the Company Portal.
  - Only the local device appears in the Company Portal app or website.
  - Users can't use Apple Volume Purchase Program (VPP) apps because of per-user Apple ID requirements for app management.
  - (iOS) Users can't also be enrolled with Apple Configurator or the Apple Device Enrollment Program (DEP), but DEP or Apple Configurator-managed devices can be enrolled without user affinity.

> [!NOTE]
> To deploy company apps to devices that are managed by the device enrollment manager, deploy the Company Portal app as a **Required Install** to the device enrollment manager's user account.
> To improve performance, viewing the Company Portal app on a DEM device only shows the local device. Remote management of other DEM devices can only be done from the Intune admin console.

The device enrollment manager can now enroll mobile devices by using the same procedure that an end user uses for a BYOD scenario in the Company Portal. The manager end user can install the Company Portal app and enroll the device using her DEM credentials on up to 1000 devices.

Device enrollment manager accounts are user accounts with permission to enroll large numbers of corporate-owned devices. Only users in the Intune console can be device enrollment managers. The device enrollment manager user cannot be an Intune admin.

## Add a device enrollment manager

1.  In the **Enrollment** workload, choose **Device Enrollment Managers**.

2.  Select **Add**.

3.  On the **Add User** blade, enter a user principal name for the DEM user, and select **Add**. The DEM user is added to the list of DEM users.

## Remove a device enrollment manager

Deleting a device enrollment manager does not affect enrolled devices. When a device enrollment manager is deleted:

-   No enrolled devices are affected.

-   Enrolled devices continue to be fully managed.

-   The deleted device enrollment manager account credentials remain valid to sign in to the Company Portal to access apps.

-   The deleted device enrollment manager account credentials still cannot wipe or retire devices.

-   The deleted device enrollment manager account’s relationship to enrolled devices remains, but no additional devices can be enrolled.

**To remove a device enrollment manager**:

1.  In the **Enrollment** workload, choose **Device Enrollment Managers**.

2. On the **Device Enrollment Managers** blade, right-click the DEM user, and select **Remove**.

## View the properties of a device enrollment manager

1. In the **Enrollment** workload, choose **Device Enrollment Managers**.

2. On the **Device Enrollment Managers** blade, right-click the DEM user, and select **Properties**.


