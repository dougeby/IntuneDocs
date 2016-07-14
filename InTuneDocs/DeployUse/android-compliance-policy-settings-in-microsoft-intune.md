---
# required metadata

title: Compliance policy settings for Android devices | Microsoft Intune
description: This topic describes the device compliance policy settings for Android devices.
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 07/13/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Compliance policy settings for Android devices in Microsoft Intune

The policy settings described in this topic apply to devices running Android 4.0 and later, or Samsung KNOX 4.0 and later.

If you are looking for information about other platforms, select one of the following:
> [!div class="op_single_selector"]
- [Compliance policy settings for iOS devices](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Compliance policy settings for Windows devices](windows-compliance-policy-settings-in-microsoft-intune.md)

## System security settings
### Password
- **Require a password to unlock mobile devices:** Set this to **Yes** to require users to enter a password before they can access their device.

-  **Minimum password length:** Specify the minimum number of digits or characters that the user’s password must contain.

- **Password quality:** Enable this setting to configure password requirements for Android devices. Choose from:
  -   **Low security biometric**
  - **Required**
  -   **At least numeric**
  -   **At least alphabetic**
  -   **At least alphanumeric**
  -   **Alphanumeric with symbols**

- **Minutes of inactivity before password is required:**  Specifies the idle time before the user must re-enter their password.

- **Password expiration (days):** Select the number of days before the user’s password expires and they must create a new one.

- **Remember password history:** Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.

- **Prevent reuse of previous passwords:** If **Remember password history** is selected, specify the number of previously used passwords that cannot be re-used.

- **Require a password when the device returns from an idle state:**
  This setting should be used together with the in the **Minutes of inactivity before password is required** setting. The end-users are prompted to enter a password to access a device that has been inactive for the time specified in the
  **Minutes of inactivity before password is required** setting.

### Encryption
- **Require encryption on mobile device:** Set this to **Yes** to require devices to be encrypted in order to connect to resources. Devices are
  encrypted when you configure the setting **Require a password to unlock mobile devices**.

## Device health settings

- **Device must not be jailbroken or rooted:** If you enable this setting, jailbroken devices will be evaluated as noncompliant.

## Device property settings
- **Minimum OS required:** When  a device does not meet the minimum OS version requirement, it is reported as noncompliant.
  A link with information on how to upgrade is displayed. The end-user can choose to upgrade their device after which they can access company resources.

- **Maximum OS version allowed:** When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.
