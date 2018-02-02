---
# required metadata

title: Compliance settings Android for Work 
description: This topic describes the device compliance policy settings for Android devices that are compatible with Android for Work.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---


# Compliance policy settings for Android for Work devices in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

The policy settings described in this topic apply to Android for Work devices.

If you are looking for information about other platforms, select one of the following:
> [!div class="op_single_selector"]
- [Compliance policy setting for Android](android-compliance-policy-settings-in-microsoft-intune.md)
- [Compliance policy settings for iOS devices](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Compliance policy settings for Windows devices](windows-compliance-policy-settings-in-microsoft-intune.md)

## System security settings
### Password
- **Require a password to unlock mobile devices:** Set this to **Yes** to require users to enter a password before they can access their device.

-  **Minimum password length:** Specify the minimum number of digits or characters that the user’s password must contain.

- **Password quality:** This setting detects if the password requirements you specify is configured on the device. Enable this setting to require that users configure certain password requirements for Android devices. Choose from:
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
- **Require encryption on mobile device:** You don't have to configure this setting since Android for Work devices enforce encryption.

## Device health and security settings

- **Device must not be jailbroken or rooted:** If you enable this setting, jailbroken devices will be evaluated as noncompliant.
- **Require that devices prevent installation of apps from unknown sources:** You do not have to configure this setting as Android for Work devices always restrict installation from unknown sources. .  

- **Require that USB debugging is  disabled**: You do not have to configure this settings as USB debugging is already disabled on Android for Work devices.

- **Minimum Android security patch level**: Use this setting to specify the minimum Android patch level.  Devices that are not at least at this patch level will be noncompliant. The date must be specified the format: YYYY-MM-DD.
- **Require device threat protection to be enabled**: Use this setting to take the risk assessment from the device threat protection solution as a condition for compliance. Select the maximum allowed threat level, which is one of the following:

  - **None (secured)** This is the most secure. This means that the device cannot have any threats. If the device is detected as having any level of threats, it will be evaluated as noncompliant.
  - **Low:** Device is evaluated as compliant if only low level threats are present. Anything higher puts the device in a noncompliant status.
  - **Medium:** Device is evaluated as compliant if the threats that are present on the device are low or medium level. If the device is detected to have high level threats, it is determined as noncompliant.
  - **High:** This is the least secure. Essentially, this allows all threat levels, and perhaps only useful if you using this solution only for reporting purposes.

  For more details, see [Create device compliance policy](create-lookout-device-compliance-policy.md).

## Device property settings
- **Minimum OS required:** When a device does not meet the minimum operating system (OS) version requirement, it is reported as noncompliant.
  A link with information on how to upgrade is displayed. The end-user can choose to upgrade their device after which they can access company resources.

- **Maximum OS version allowed:** When a device is using an operating system (OS) version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in the rule to allow the operating system version, this device cannot be used to access company resources.
