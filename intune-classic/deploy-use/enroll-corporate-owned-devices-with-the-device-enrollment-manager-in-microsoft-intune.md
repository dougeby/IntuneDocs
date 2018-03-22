---
# required metadata

title: Enroll with the device enrollment manager
description: The device enrollment manager (DEM) account can manage large numbers of shared, corporate-owned mobile devices with a single user account.
keywords:
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 01/03/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---


# Enroll corporate-owned devices with the device enrollment manager in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Organizations can use Intune to manage large numbers of mobile devices with a single user account. The *device enrollment manager* (DEM) account is a special user account that can enroll up to 1,000 devices. You add existing users to the DEM account to give them the special DEM capabilities. Each enrolled device uses a single license. We recommend that you use devices enrolled through this account as shared devices (that is, with no user affinity) rather than personal ("BYOD") devices.  

Users must exist in the Azure portal to be added as device enrollment managers. For optimal security, the DEM user should not also be an Intune admin.

>[!NOTE]
>The DEM enrollment method can't be used with the [Apple Configurator Setup Assistant](ios-setup-assistant-enrollment-in-microsoft-intune.md) or [direct enrollment](ios-direct-enrollment-in-microsoft-intune.md), macOS enrollment, and the [DEP enrollment method](ios-device-enrollment-program-in-microsoft-intune.md).

## Example of a device enrollment manager scenario

A restaurant wants to provide 50 point-of-sale tablets for its wait staff, and order monitors for its kitchen staff. The employees never need to access company data or sign in as users. The Intune admin creates a device enrollment manager account and adds a restaurant supervisor to the DEM account, in effect giving that supervisor DEM capabilities. The supervisor can now enroll the 50 tablets devices by using the DEM credentials.

Only users in the Intune console can be device enrollment managers. The device enrollment manager user cannot be an Intune admin.

The DEM user can:

-   Enroll up to 1000 devices in Intune
-   Use the Company Portal app to get company apps
-   Configure access to company data by deploying role-specific apps to the tablets

## Limitations of devices that are enrolled with a DEM account

Devices that are enrolled with a device enrollment manager account have the following limitations:

  - There is no specific device "user." Therefore, there is no email or company data access. However VPN, for example, could still be used to provide device apps with access to data.

  - There is no conditional access because these are per-user scenarios.

  - The DEM user can't unenroll DEM-enrolled devices on the device itself by using the Company Portal. The Intune admin has this capability, but the DEM user does not.

  - Only the local device appears in the Company Portal app or website.

  - Users can't use Apple Volume Purchase Program (VPP) apps because of per-user Apple ID requirements for app management.

  - (iOS only) If you use DEM to enroll iOS devices, you can't use the Apple Configurator or Apple Device Enrollment Program (DEP) to enroll devices.

> [!NOTE]
> To deploy company apps to devices that are managed by the device enrollment manager, deploy the Company Portal app as a **Required Install** to the device enrollment manager's user account.
> To improve performance, viewing the Company Portal app on a DEM device shows only the local device. Remote management of other DEM devices can only be done from the Intune admin console.


## Add a device enrollment manager

1.  Ensure that the user that you want to add to the DEM account already exists. If you need to add the user, sign in to the [Office 365 portal](https://go.microsoft.com/fwlink/p/?LinkId=698854), and follow the steps in [Add users individually or in bulk to the Office 365 portal](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

2.  Sign in to the [Microsoft Intune administration console](https://manage.microsoft.com) with your admin credentials.

3.  In the navigation pane, choose **Admin**, go to **Administrator Management**, and select **Device Enrollment Manager**. The **Device Enrollment Managers** page opens.

4.  Choose **Add…**. The **Add Device Enrollment Manager** dialog box opens.

5.  Enter the **User ID** of the Intune account, and then choose **OK**.

    The DEM user can now enroll mobile devices by using the same procedure that an end user uses for a BYOD scenario in the Company Portal. The manager end user can install the Company Portal app and enroll the device using her DEM credentials on up to 1000 devices. For the end-user enrollment steps for each platform, see:

  - [Enroll your iOS device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)
  - [Enroll your macOS device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos)
  - [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)
  - [Enroll your Windows device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows)

## Delete a device enrollment manager from Intune

1.  Sign in to the [Microsoft Intune admin portal](https://manage.microsoft.com) with your admin credentials.

2.  In the navigation pane, choose **Admin**, go to **Administrator Management**, and select **Device Enrollment Manager**. The **Device Enrollment Managers** page opens.

3.  Select the device enrollment manager **User** that you want to delete, and then choose **Delete**. This user won’t be deleted from Intune, and the devices this user manages will remain enrolled in Intune. Deleting a device enrollment manager prevents that user from enrolling more devices in Intune.

4.  Choose **Yes** to confirm that you want to delete the device enrollment manager.

Deleting a device enrollment manager does not affect enrolled devices. When a device enrollment manager is deleted:

-   No enrolled devices are affected.

-   Enrolled devices continue to be fully managed.

-   The deleted device enrollment manager account credentials remain valid to sign in to the Company Portal to access apps.

-   The deleted device enrollment manager account credentials still cannot wipe or retire devices.

-   The deleted device enrollment manager account’s relationship to enrolled devices remains, but no additional devices can be enrolled.
