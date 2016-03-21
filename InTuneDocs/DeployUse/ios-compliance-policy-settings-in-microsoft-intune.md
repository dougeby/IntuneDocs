---
title: Compliance policy settings for iOS devices in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service:
ms.suite: na
ms.tgt_pltfrm: na
ms.topic:
ms.assetid:
author: karthikaraman
---

# Compliance policy settings for iOS devices in Microsoft Intune

This topic lists the the details of the compliance policy settings that
are applicable to and supported on devices running iOS  6 and later.

Select one of the following to learn about other platforms:
> [!div class="op_single_selector"]
- [Compliance policy settings for Android devices](android-compliance-policy-settings-in-microsoft-intune.md)
- [Compliance policy settings for Windows devices](windows-compliance-policy-settings-in-microsoft-intune.md)

## Compliance policy settings for iOS devices

- **Require a password to unlock mobile devices:**    Set this to **Yes** to require users to enter a password before
  they can access their device. Devices are
  encrypted when you configure the setting.

- **Allow simple passwords:**    Set this
   to **Yes** to let users create simple passwords
   such as ‘**1234**’ or ‘**1111**’.

-  **Minimum password length:**
  Specify the minimum number of digits or characters that
  the user’s password must contain.
- **Required password type:** Specify whether users must create
an **Alphanumeric**, or a **Numeric** password.

- **Minimum number of character sets:** If **Required password type** is set to
**Alphanumeric**, this setting specifies the minimum number of
character sets that the password must contain. The four character sets are:
  -   Lowercase letters
  -   Uppercase letters
  -   Symbols
  -   Numbers

  Setting a higher number for this setting will require users to create more complex passwords.<br /><br />For iOS devices, this setting refers to the number of special characters (for example, **!**, **#**, **&amp;**) that must be included in the password.
- **Minutes of inactivity before password is required:**  Specifies the idle time before the user must re-enter their password.

- **Password expiration (days):** Select the number of days before the user’s password expires
and they must create a new one.

- **Remember password history:** Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from
creating previously used passwords.

- **Prevent reuse of previous passwords:** If **Remember password history** is selected, specify the
number of previously used passwords that cannot be re-used.

- **Require a password when the device returns from an idle state:**
This setting should be used together with the in the **Minutes of inactivity before password is required** setting. The end-users will be prompted to enter a password to access a device that has been inactive for the time specified in the
**Minutes of inactivity before password is required** setting.


- **Device must not be jailbroken or rooted:** If you enable this setting,
jailbroken devices will not be compliant.

- **Email account must be managed by Intune:** When this option is set to **Yes** ,
the device will be reported as noncompliant.

  If the user has set up an email account on the device that matches an
  Intune email profile that was deployed to the device by an IT admin.

  Intune cannot overwrite the user-provisioned profile, and therefore
  cannot manage it. To ensure compliance, the user must remove the
  existing email settings, then, Intune can install the managed
  email profile.

 For details about email profiles, see [Configure access to
 corporate email using email profiles with Microsoft Intune](../Topic/Configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md).

- **Select the email profile that must be managed by Intune:**
     If **Email account must be managed by Intune** is selected,
     choose **Select** to specify the Intune email profile that devices
     must be managed by. The email profile must be present on the device.
- **Minimum OS required:** When  a device does not meet the minimum OS
version requirement, it will be reported as non-compliant.
A link with information on how to upgrade will be displayed. The end-user can choose to upgrade their device after which they will be able to access company resources.

- **Maximum OS version allowed:** When a device is using an
OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.
## Next steps
[Create a compliance policy](create-a-device-compliance-policy-in-microsoft-intune.md)
