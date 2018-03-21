---
# required metadata

title: Compliance policy setting for iOS devices 
description: This topic describes the rules and settings that you can set in a compliance policy for iOS devices.
keywords:
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 12/15/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---


# Compliance policy settings for iOS devices in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

The policy settings described in this topic apply to devices running iOS 8.0 and later.

If you are looking for information about other platforms, select one of the following:
> [!div class="op_single_selector"]
- [Compliance policy settings for Android devices](android-compliance-policy-settings-in-microsoft-intune.md)
- [Compliance policy settings for Android for work](afw-compliance-policy-settings-in-microsoft-intune.md)
- [Compliance policy settings for Windows devices](windows-compliance-policy-settings-in-microsoft-intune.md)

## System security settings
### Password
- **Require a password to unlock mobile devices**: Set this to **Yes** to require the user to enter a password before they can access their device. iOS devices that use a password are encrypted.

- **Allow simple passwords**: Set this to **Yes** to let the user create a simple password like **1234** or **1111**.

-  **Minimum password length**: Specify the minimum number of digits or characters that the user’s password must have.

- **Required password type**: Specify whether the user must create
an **Alphanumeric** password or a **Numeric** password.

- **Minimum number of character sets**: If you set **Required password type** to
**Alphanumeric**, use this setting to specify the minimum number of
character sets that the password must have. The four character sets are:
  -   Lowercase letters
  -   Uppercase letters
  -   Symbols
  -   Numbers

  Setting a higher number will require the user to create a password that is more complex.

  For iOS devices, this setting refers to the number of special characters (for example, **!**, **#**, **&amp;**) that must be included in the password.

- **Minutes of inactivity before password is required**:  Specify the idle time before the user must reenter their password.

- **Password expiration (days)**: Select the number of days before the user’s password expires and they must create a new one.

- **Remember password history**: Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.

- **Prevent reuse of previous passwords**: If you selected **Remember password history**, specify the number of previously used passwords that cannot be reused.

- **Require a password when the device returns from an idle state**:
Use this setting together with the in the **Minutes of inactivity before password is required** setting. The user is prompted to enter a password to access a device that has been inactive for the time specified in the
**Minutes of inactivity before password is required** setting.

### Email profile
- **Email account must be managed by Intune**: When this option is set to **Yes**, the device must use the email profile deployed to the device. The device is considered noncompliant in the following situations:
  - The email profile is deployed to a user group other than the user group that the compliance policy targets.
  - The user has already set up an email account on the device that matches the Intune email profile deployed to the device. Intune cannot overwrite the user-provisioned profile, and therefore cannot manage it. To ensure compliance, the user must remove the existing email settings. Then, Intune can install the managed email profile.

- **Select the email profile that must be managed by Intune**: If the **Email account must be managed by Intune** setting is selected, choose **Select** to specify the Intune email profile. The email profile must be present on the device.

     For details about email profiles, see [Configure access to corporate email using email profiles with Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## Device health settings

- **Device must not be jailbroken or rooted**: If you enable this setting, jailbroken devices will not be compliant.

##  Device properties
- **Minimum OS required**: When a device does not meet the minimum OS version requirement, it is reported as noncompliant.
A link with information on how to upgrade appears. The user can choose to upgrade their device. After that, they can access company resources.

- **Maximum OS version allowed**: When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.
