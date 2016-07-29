---
# required metadata

title: Enroll with Device Enrollment Manager | Microsoft Intune
description: Device enrollment manager (DEM) account can manage large numbers of shared, corporate-owned mobile devices with a single user account.
keywords:
author: NathBarn
manager: angrobe
ms.date: 07/12/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Enroll corporate-owned devices with the Device Enrollment Manager in Microsoft Intune
Organizations can use Intune to manage large numbers of mobile devices with a single user account. The *device enrollment manager*  (DEM) account is a special Intune account with permission to enroll up to 1000 devices. Use devices enrolled using the device enrollment manager account as shared devices rather than personal ("BYOD") devices. Users will not be able to use "native" email apps, for example. You can assign a store manager or supervisor, for example, a device enrollment manager user account to allow her to do the following:

-   Enroll devices in Intune

-   Log on to company portal to get company apps

-   Install and uninstall software

-   Configure access to company data


**Examples of device enrollment manager scenario:**
A restaurant wants point-of-sale tablets for its wait staff and order monitors for its kitchen staff. The employees never need access to company data or to logon as a user. The Intune administrator creates a device enrollment manager account and enrolls the company-owned devices using that account. Alternatively, the administrator could give the device enrollment manager credentials to a restaurant manager, allowing him or her to enroll and manage the devices.

The administrator or manager can deploy role-specific apps to the restaurant devices. An administrator can also select the device in the Intune console and retire it from mobile device management with the administration console.

Devices enrolled with a device enrollment manager account have the following restrictions:
  - No specific user so all devices are "user-less;" therefore no email or company data access although VPN, for example, could still provide device apps with access to data
  - No conditional access because these are per-user scenarios
  - Cannot be reset devices from the Company Portal
  - Only the local device appears in the Company Portal app or website
  - No Apple Volume Purchase Program (VPP) apps due to per-user Apple ID requirements for app management
  - Cannot also be enrolled with Apple Configurator or Apple device enrollment program (iOS devices)

> [!NOTE]
> To deploy company apps to devices managed with the device enrollment manager, deploy Company Portal app as a **Required Install** to the device enrollment manager's user account.
> To improve performance, viewing the Company Portal app on a DEM device only shows the local device. Remote management of other DEM devices can only be done from the Intune admin console.

## Create device enrollment manager accounts
Device enrollment manager accounts are user accounts with permission to enroll large numbers of corporate-owned devices. Only users in the Intune console can be device enrollment managers.

#### Add a device enrollment manager to Intune

1.  Go to the [Microsoft Intune account portal](http://go.microsoft.com/fwlink/?LinkId=698854) and sign in your administrator account.

2.  Choose **Add user**.

3.  Confirm that the user account that will be a device enrollment manager is listed. If not, add the user by choosing **New** and completing the Add user process. A subscription license is required for each user that accesses the Service and the *device enrollment manager* cannot be an Intune administrator. Determine whether you need to add more licenses before you use this feature.

4.  Logon to the [Microsoft Intune administration console](http://manage.microsoft.com) with your administrator sign in.

5.  In the navigation pane, choose **Admin**, go to **Administrator Management** and select **Device Enrollment Manager**. The Device Enrollment Managers page opens.

6.  Choose **Add…**. The **Add Device Enrollment Manager** dialog box opens.

7.  Enter the **User ID** of the Intune account and then choose **OK**. The device enrollment manager user cannot be an Intune administrator.

8.  The device enrollment manager can now enroll mobile devices using the same procedure an end user uses for a BYOD scenario in the company portal.

## Delete a device enrollment manager from Intune

1.  Logon to the [Microsoft Intune admin portal](http://manage.microsoft.com) with your administrator sign in.

2.  In the navigation pane, choose **Admin** and go to **Administrator Management** and select **Device Enrollment Manager**. The Device Enrollment Managers page opens.

3.  Select the device enrollment manager **User** that you want to delete, and then choose **Delete**. This user won’t be deleted from Intune and the devices this user manages will remain enrolled in Intune. Deleting a device enrollment manager prevents that user from enrolling more devices in Intune.

4.  Choose **Yes** to confirm you want to delete the device enrollment manager.

Deleting a device enrollment manager does not affect enrolled devices. When a device enrollment manager is deleted:

-   No enrolled devices are affected

-   Enrolled devices continue to be fully managed

-   The deleted device enrollment manager account credentials remain valid to logon to the company portal to access apps

-   The deleted device enrollment manager account credentials still cannot wipe or retire devices

-   The deleted device enrollment manager account’s relationship to enrolled devices remains but no additional devices can be enrolled
