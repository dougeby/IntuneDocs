---
# required metadata

title: Set up Android for Work management  | Microsoft Intune
description: Enable mobile device management (MDM) for Android for Work devices with Microsoft Intune.
keywords:
author: NathBarn
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b2fdcea9-9ad7-4d73-88e2-854b7a774bb2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: [ALIAS]
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Enable enrollment of Android for Work devices

To enable management of Android for Work devices, you must add an Android for Work binding to Intune. To enroll devices that support Android for Work but were previously enrolled as regular Android device, the devices must be unenrolled and then re-enrolled.

## Add Android for Work Binding for Intune

1. **Set up Intune**<br>
If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](prerequisites-for-enrollment.md#set-mobile-device-management-authority) as **Microsoft Intune** and setting up MDM.

2. **Configure Android for Work binding**<br>
    As an administrative user, open the [Microsoft Intune administration console](http://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **Android for Work**, and click **Configure** to open Google Play's Android for Work website. This will open in a new tab in your browser.

3. **Log in to Google**<br>
   On Google's sign-in page, enter with the Google account that will be associated with all Android for Work management tasks for this tenant. This could be Google account shared among the administrators who manage Intune. This is the Google account that your organization uses to manage and publish apps in the Play for Work console.

4. **Provide Organization details**<br>
   Provide your company's name for the **Organization name**. For **Enterprise mobility management (EMM) provider**, *Microsoft Intune* should be displayed. Agree to the Android for Work agreement, and then click **Confirm**. Your request will be processed .

## Specify Android for Work Enrollment Settings
   Android for Work is only supported on certain Android devices, usually Android version 6 and higher.  Any device that supports Android for Work will also support conventional Android management.  Intune lets you specify how devices support Android for Work should be managed:

   - **Manage all devices as Android** - (Disabled) All Android devices, including devices that support Android for Work, will be enrolled as conventional Android devices.
   - **Manage supported devices as Android for Work** - (Enabled) All devices that support Android for Work are enrolled as Android for Work devices. Any Android device that does not support Android for Work is enrolled as a conventional Android device.
   - **Manage supported devices for users only in these user groups as Android for Work** - (Testing) Lets you target Android for Work management to a limited set of users. Only members of the selected groups who enroll a device that supports Android for Work are enrolled as Android for Work devices. All others are enrolled as Android devices.

## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can manage do the following:
- [Configure Android for Work apps](afw-app-configuration-policy.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)

## Unbinding your Android for Work administrative account

You can turn off Android for Work enrollment and management. Clicking **Unbind** removes all enrolled Android for Work devices from enrollment and removes the relationship between the Android for Work account and Intune.

### How to unbind an Android for Work account

1. **Unbind Android for Work binding**<br>
    As an administrative user, open the [Microsoft Intune administration console](http://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **Android for Work**, and click **Unbind**.

2. **Agree to delete Android for Work binding**<br>
  Click **Yes** to delete the binding and unenroll all Android for Work devices from Intune.
