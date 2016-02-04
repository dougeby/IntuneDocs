---
title: Enroll corporate-owned devices with the Device Enrollment Manager in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
author: NathBarn
---
# Enroll corporate-owned devices with the Device Enrollment Manager in Microsoft Intune
Organizations can use Intune to manage large numbers of mobile devices with a single user account. The *device enrollment manager* account is a special Intune account with permission to enroll more than five devices. You can assign a store manager or supervisor, for example, a device enrollment manager user account to allow her to do the following:

-   Enroll devices in Intune

-   Log on to company portal to get company apps

-   Install and uninstall software

-   Configure access to company data

The store manager cannot reset the device from the company portal.

**Examples of device enrollment manager scenario:**
A restaurant wants point-of-sale tablets for its wait staff and order monitors for its kitchen staff. The employees never need access to company data or to logon as a user. The Intune administrator creates a device enrollment manager account and enrolls the company-owned devices using that account. Alternatively, the administrator could give the device enrollment manager credentials to a restaurant manager, allowing him or her to enroll and manage the devices.

The administrator or manager can deploy role-specific apps to the restaurant devices. An administrator can also select the device in the Intune console and retire it from mobile device management with the administration console.

> [!NOTE]
> Device enrollment manager user accounts with more than 20 devices enrolled might have problems using the Company Portal app. To deploy company apps to devices managed with the device enrollment manager, deploy Company Portal app as a **Required Install** to the device enrollment manager's user account.

## Device enrollment manager accounts in Intune
Device enrollment manager accounts are user accounts with permission to enroll large numbers of corporate-owned devices. Only users in the Intune console can be device enrollment managers.

#### Add a device enrollment manager to Intune

1.  Go to the [Microsoft Intune account portal](http://go.microsoft.com/fwlink/?LinkId=698854) and sign in your administrator account.

2.  Click **Add user**.

3.  Confirm that the user account that will be a device enrollment manager is listed. If not, add the user by clicking **New** and completing the Add user process. A subscription license is required for each user that accesses the Service and the *device enrollment manager* cannot be an Intune administrator. Determine whether you need to add more licenses before you use this feature.

4.  Logon to the [Microsoft Intune administration console](http://manage.microsoft.com) with your administrator sign in.

5.  In the navigation pane, click **Admin**, go to **Administrator Management** and select **Device Enrollment Manager**. The Device Enrollment Managers page opens.

6.  Click **Add…**. The **Add Device Enrollment Manager** dialog box opens.

7.  Enter the **User ID** of the Intune account and then click **OK**. The device enrollment manager user cannot be an Intune administrator.

8.  The device enrollment manager can now enroll mobile devices using the same procedure an end user uses for a BYOD scenario in the company portal. To enroll devices using the company portal, see [Enable mobile device enrollment with the Microsoft Intune Account Portal](../Topic/Enable-mobile-device-enrollment-with-the-Microsoft-Intune-Account-Portal.md).

#### Delete a device enrollment manager from Intune

1.  Logon to the [Microsoft Intune admin portal](http://manage.microsoft.com) with your administrator sign in.

2.  In the navigation pane, click **Admin** and go to **Administrator Management** and select **Device Enrollment Manager**. The Device Enrollment Managers page opens.

3.  Select the device enrollment manager **User** that you want to delete, and then click **Delete**. This user won’t be deleted from Intune and the devices this user manages will remain enrolled in Intune. Deleting a device enrollment manager prevents that user from enrolling more devices in Intune.

4.  Click **Yes** to confirm you want to delete the device enrollment manager.

Deleting a device enrollment manager does not affect enrolled devices. When a device enrollment manager is deleted:

-   No enrolled devices are affected

-   Enrolled devices continue to be fully managed

-   The deleted device enrollment manager account credentials remain valid to logon to the company portal to access apps

-   The deleted device enrollment manager account credentials still cannot wipe or retire devices

-   The deleted device enrollment manager account’s relationship to enrolled devices remains but no additional devices can be enrolled

## See Also
[Get started with a paid subscription to Microsoft Intune](../Topic/Get-started-with-a-paid-subscription-to-Microsoft-Intune.md)
[Get ready to enroll devices in Microsoft Intune](../Topic/Get-ready-to-enroll-devices-in-Microsoft-Intune.md)
[Enable mobile device enrollment with the Microsoft Intune Account Portal](../Topic/Enable-mobile-device-enrollment-with-the-Microsoft-Intune-Account-Portal.md)

