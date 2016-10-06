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

You can allow users to enroll their Android for Work devices with Intune. Android for Work lets workers use their smartphones at work. Android for Work helps keep work and personal information separate on their devices. To enable enrollment, you must add an Android for Work binding to Intune.

Once enrolled as an Android for Work device, you can deploy apps to managed devices. Apps and the data they access remain exclusively within the Android for Work environment on the device. To enroll devices that support Android for Work but were previously enrolled as regular Android device, the devices must be unenrolled and then re-enrolled.

## Add Android for Work Binding for Intune

1. **Set up Intune**<br>
If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](prerequisites-for-enrollment.md#set-mobile-device-management-authority) as **Microsoft Intune** and setting up MDM.

2. **Configure Android for Work binding**<br>
    As an administrative user, open the [Microsoft Intune administration console](http://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **Android for Work**, and click **Configure** to open Google Play's Android for Work website.

3. **Log in to Google Play**<br>
   On Google's sign-in page, enter with the Google account that will be associated with all Android for Work management tasks for this binding. This could be Google account shared among the administrators who manage Intune.

4. **Provide Organization details**<br>
   Provide your company's name for the **Organization name**. For **Enterprise mobility management (EMM) provider**, *Microsoft Intune* should be displayed. Agree to the Android for Work agreement, and then click **Confirm**. Your request will be processed .

5. **Specify Android for Work Enrollment Settings**<br>
   Intune lets you specify how Android for Work devices are enrolled. This setting lets you specify how devices are enrolled

   - **Enroll no device as Android for Work** - (Disabled) All Android devices, including Android for Work devices, without Android for Work functionality.
   - **Enroll all supported devices as Android for Work** - (Enabled) All devices that can support Android for Work are enrolled as Android for Work devices.
   - **Only enroll supported devices for these user groups as Android for Work** - (Testing) Lets you deploy to a limited number of devices. Only members of the selected groups are enrolled as Android for Work devices. All others are enrolled as Android devices.

## Unbinding your Android for Work administrative account

You can turn off Android for Work enrollment and management. Clicking **Unbind** removes all enrolled Android for Work from enrollment and removes the relationship between the Android for Work account and Intune.

### How to unbind an Android for Work account

1. **Unbind Android for Work binding**<br>
    As an administrative user, open the [Microsoft Intune administration console](http://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **Android for Work**, and click **Unbind**.

2. **Agree to delete Android for Work binding**<br>
  Click **Yes** to delete the binding and unenroll all Android for Work devices from Intune.
