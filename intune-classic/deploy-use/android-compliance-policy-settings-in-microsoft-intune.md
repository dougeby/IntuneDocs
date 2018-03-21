---
# required metadata

title: Compliance policy settings for Android 
description: This topic describes the device compliance policy settings for Android devices.
keywords:
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 01/23/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---


# Compliance policy settings for Android devices in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

The policy settings described in this topic apply to devices that are running Android 4.0 and later or Samsung KNOX 4.0 and later.

If you're looking for information about other platforms, select one of the following:
> [!div class="op_single_selector"]
- [Compliance policy settings for iOS devices](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Compliance policy settings for Windows devices](windows-compliance-policy-settings-in-microsoft-intune.md)
- [Compliance policy settings for Android for Work devices](afw-compliance-policy-settings-in-microsoft-intune.md)

## System security settings
### Password
- **Require a password to unlock mobile devices**: Set this to **Yes** to require users to enter a password before they can access their device.

-  **Minimum password length**: Specify the minimum number of digits or characters that the user’s password must have.

- **Password quality**: This setting detects if the password requirements that you specify are set up on the device. Enable this setting to require that users meet certain password requirements for Android devices. Choose from:

  -   **Low security biometric**
  -   **Required**
  -   **At least numeric**
  -   **At least alphabetic**
  -   **At least alphanumeric**
  -   **Alphanumeric with symbols**

- **Minutes of inactivity before password is required:**  Specify the idle time before the user must re-enter their password.

- **Password expiration (days)**: Select the number of days before the user’s password expires and they must create a new one.

- **Remember password history**: Use this setting together with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.

- **Prevent reuse of previous passwords:** Specify the number of previously used passwords that cannot be re-used (if **Remember password history** is selected).

- **Require a password when the device returns from an idle state:**
  Use together with the **Minutes of inactivity before password is required** setting. Users are prompted to enter a password to access a device that has been inactive for the time specified in the
  **Minutes of inactivity before password is required** setting.

### Encryption
- **Require encryption on mobile device:** Set this to **Yes** to require devices to be encrypted to be able connect to resources. Devices are
  encrypted when you configure the setting **Require a password to unlock mobile devices**.

## Device health and security settings

- **Device must not be jailbroken or rooted:** If you enable this setting, jailbroken devices are evaluated as noncompliant.
- **Require that devices prevent installation of apps from unknown sources (Android 4.0 or later)**: To block devices that have **Security > Unknown sources** enabled on the device, enable this setting and set it to **Yes**.  

>[!IMPORTANT]
>Side-loading applications requires that the  **Unknown sources** setting is enabled. Enforce this compliance policy only if you are not side-loading Android apps on devices.

- **Require that USB debugging is  disabled (Android 4.2 or later)**: Specify whether to detect if the USB debugging option on the device is enabled.
- **Require devices have enabled Scan device for security threats (Android 4.2-4.4)**: Specify that the **Verify apps** feature is enabled on the device.
- **Minimum Android security patch level (Android 6.0 or later)**: Specify the minimum Android patch level.  Devices that are not at least at this patch level will be noncompliant. The date must be specified in this format: YYYY-MM-DD.
- **Require device threat protection to be enabled**: Use this setting to take the risk assessment from the Lookout MTP solution as a condition for compliance. Select the maximum allowed threat level, which is one of the following:

  - **None (secured)** This is the most secure. This means that the device cannot have any threats. If the device is detected as having any threats, it is evaluated as noncompliant.
  - **Low:** The device is evaluated as compliant if only low-level threats are present. Anything higher puts the device in noncompliant status.
  - **Medium:** The device is evaluated as compliant if the threats that are present on the device are low- or medium-level. If high-level threats are detected on the device, it is determined to be noncompliant.
  - **High:** This is the least secure. Essentially this allows all threat levels, which is perhaps only useful if you using this solution only for reporting purposes.

  For more details, see [Create Lookout device compliance policy](create-lookout-device-compliance-policy.md).

## Device property settings

- **Minimum OS required:** When  a device doesn't meet the minimum OS version requirement, it is reported as noncompliant.
  A link with information about how to upgrade is displayed. The user can choose to upgrade their device, after which they can access company resources.

- **Maximum OS version allowed:** When a device is using an OS version that's later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until the rule changes to allow the OS version, this device cannot be used to access company resources.
