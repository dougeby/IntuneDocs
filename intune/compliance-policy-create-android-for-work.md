---
# required metadata

title: Create Android Enterprise compliance policy in Microsoft Intune - Azure | Microsoft Docs
description: Create or configure a Microsoft Intune device compliance policy for Android Enterprise or work profile devices. Choose to allow jailbroken devices, set the acceptable threat level, check for Google Play, enter the minimum and maximum operating system version, choose your password requirements, and allow Side-loading applications.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/19/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Add a device compliance policy for Android Enterprise devices in Intune

Device compliance policies are a key feature when using Intune to protect your organization's resources. In Intune, you can create rules and settings that devices must meet to be considered compliant, such as a password length. If the device isn't compliant, you can then block access to data and resources using [conditional access](conditional-access.md). 

You can also get device reports, and take actions for non-compliance, such as sending a notification email to the user. To learn more about compliance policies, and any prerequisites, see [get started with device compliance](device-compliance-get-started.md).

This article lists the settings you can use within a compliance policy for devices running Android Enterprise.

## Non-compliance and conditional access

The following table describes how noncompliant settings are managed when a compliance policy is used with a conditional access policy.

--------------------------

|**policy setting**| **Android Enterprise profile** |
| --- | --- |
| **PIN or password configuration** |  Quarantined |
| **Device encryption** |  Quarantined |
| **Jailbroken or rooted device** | Quarantined (not a setting) |
| **email profile** | Not applicable |
| **Minimum OS version** | Quarantined |
| **Maximum OS version** | Quarantined |
| **Windows health attestation** |Not applicable |

**Remediated** = The device operating system enforces compliance. For example, the user is forced to set a PIN.

**Quarantined** = The device operating system doesn't enforce compliance. For example, Android devices don't force the user to encrypt the device. When the device isn't compliant, the following actions take place:

  - If a conditional access policy applies to the user, the device is blocked.
  - The company portal notifies the user about any compliance problems.

## Create a device compliance policy

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. For **Platform**, select **Android enterprise**. 
5. Choose **Settings Configure**. Enter the **Device Health**, **Device Properties**, and **System Security** settings, as described in this article.

## Device health

- **Rooted devices**: Choose **Block** to mark rooted (jailbroken) devices as not compliant. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.
- **Require the device to be at or under the Device Threat Level**: Use this setting to take the risk assessment from the Lookout MTP solution as a condition for compliance. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance. To use this setting, choose the allowed threat level:
  - **Secured**: This option is the most secure, and means that the device can't have any threats. If the device is detected with any level of threats, it's evaluated as noncompliant.
  - **Low**: The device is evaluated as compliant if only low-level threats are present. Anything higher puts the device in a noncompliant status.
  - **Medium**: The device is evaluated as compliant if the threats that are present on the device are low or medium level. If the device is detected to have high-level threats, it's determined to be noncompliant.
  - **High**: This option is the least secure, as it allows all threat levels. It may be useful if you're using this solution only for reporting purposes.
- **Google Play Services is configured**: **Require** that the Google Play services app is installed and enabled. Google Play services allows security updates, and is a base-level dependency for many security features on certified-Google devices. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.
- **Up-to-date security provider**: **Require** that an up-to-date security provider can protect a device from known vulnerabilities. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.
- **SafetyNet device attestation**: Enter the level of [SafetyNet attestation](https://developer.android.com/training/safetynet/attestation.html) that must be met. Your options:
  - **Not configured** (default): Setting isn't evaluated for compliance or non-compliance.
  - **Check basic integrity**
  - **Check basic integrity & certified devices**

#### Threat scan on apps

On Android Enterprise devices, the **Threat scan on apps** setting is a configuration policy. See [Android Enterprise device restriction settings](device-restrictions-android-for-work.md).

## Device properties settings

- **Minimum OS version**: When a device doesn't meet the minimum OS version requirement, it's reported as noncompliant. A link with information on how to upgrade is displayed. The end user can choose to upgrade their device, and then access company resources.
- **Maximum OS version**: When a device is using an OS version later than the version in the rule, access to company resources is blocked. And, the user is asked to contact their IT admin. Until a rule is changed to allow the OS version, this device can't access company resources.

## System security settings

### Password

- **Require a password to unlock mobile devices**: **Require** users to enter a password before they can access their device. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance. This setting is applied at the device level. If you only need to require a password at the work profile level then use a configuration policy, see [Android Enterprise Device Setting](device-restrictions-android-for-work.md)
- **Minimum password length**: Enter the minimum number of digits or characters the user's password must have.
- **Required password type**: Choose if a password should include only numeric characters, or a mix of numerals and other characters. Your options:
  - **Device Default**
  - **Low security biometric**
  - **At least numeric** (default)
  - **Numeric complex**
  - **At least alphabetic**
  - **At least alphanumeric**
  - **At least alphanumeric with symbols**

- **Maximum minutes of inactivity before password is required**: Enter the idle time before the user must reenter their password. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.
- **Password expiration (days)**: Select the number of days before the password expires, and they must create a new one.
- **Number of previous passwords to prevent reuse**: Enter the number of recent passwords that can't be reused. Use this setting to restrict the user from creating previously used passwords.

### Encryption

- **Encryption of data storage on device**: Choose **Require** to encrypt data storage on your devices. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance. 

  You don't have to configure this setting because Android work profile devices enforce encryption.

### Device Security

- **Block apps from unknown sources**: Choose to **block** devices with "Security > Unknown Sources" enabled sources (supported on Android 4.0 – Android 7.x; not supported by Android 8.0 and later). When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.

  To side-load apps, unknown sources must be allowed. If you're not side-loading Android apps, then set this feature to **Block** to enable this compliance policy. 

  > [!IMPORTANT]
  > Side-loading applications require that the **Block apps from unknown sources** setting is enabled. Enforce this compliance policy only if you're not side-loading Android apps on devices.

  You don't have to configure this setting as Android work profile devices always restrict installation from unknown sources.

- **Company portal app runtime integrity**: Choose **Require** to confirm the Company Portal app meets all the following requirements:

  - Has the default runtime environment installed
  - Is properly signed
  - Isn't in debug-mode
  - Is installed from a known source

  When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.

- **Block USB debugging on device**: Choose **Block** to prevent devices from using the USB debugging feature. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.

  You don't have to configure this setting because USB debugging is already disabled on Android work profile devices.

- **Minimum security patch level**: Select the oldest security patch level a device can have. Devices that aren't at least at this patch level are noncompliant. The date must be entered in the *YYYY-MM-DD* format.

When done, select **OK** > **OK** to save your changes.

## Actions for noncompliance

Select **Actions for noncompliance**. The default action marks the device as noncompliant immediately.

You can change the schedule when the device is marked non-compliant, such as after one day. You can also configure a second action that sends an email to the user when the device isn't compliant.

[Add actions for noncompliant devices](actions-for-noncompliance.md) provides more information, including creating a notification email to your users.

## Scope tags

Scope tags are a great way to assign policies to specific groups, such as Sales, Engineering, HR, and so on. You can add a scope tags to compliance policies. See [Use scope tags to filter policies](scope-tags.md). 

## Assign user groups

Once a policy is created, it's not doing anything until you assign the policy. To assign the policy: 

1. Choose a policy that you've configured. Existing policies are in **Device compliance** > **Policies**.
2. Choose the policy, and choose **Assignments**. You can include or exclude Azure Active Directory (AD) security groups.
3. Choose **Selected groups** to see your Azure AD security groups. Select the user groups you want this policy to apply, and choose **Save** to deploy the policy to users.

You've applied the policy to users. The devices used by the users targeted by the policy are evaluated for compliance.

## Next steps
[Automate email and add actions for noncompliant devices](actions-for-noncompliance.md)  
[Monitor Intune Device compliance policies](compliance-policy-monitor.md)  
[Compliance policy settings for Android](compliance-policy-create-android.md)
