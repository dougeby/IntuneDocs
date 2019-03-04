---
# required metadata

title: Create Android device compliance policy in Microsoft Intune - Azure | Microsoft Docs
description: Create or configure a Microsoft Intune device compliance policy for Android devices. Choose to allow jailbroken devices, set the acceptable threat level, check for Google Play, enter the minimum and maximum operating system version, choose your password requirements, and allow Side-loading applications.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/19/2018
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Add a device compliance policy for Android devices in Intune

An Intune device compliance policy for Android specifies the rules and settings that Android devices must meet to be considered compliant. You can use these policies with [conditional access](conditional-access.md) to allow or block access to organiational resources. You can also get device reports and take actions for non-compliance. 

To learn more about compliance policies, and any prerequisites, see [Get started with device compliance](device-compliance-get-started.md).

This topic lists the settings you can use within a compliance policy for Android devices.

## Non-compliance and conditional access

The following table describes how noncompliant settings are managed when a compliance policy is used with a conditional access policy.

--------------------

|**Policy setting**| **Android 4.0 and later, Samsung Knox Standard 4.0 and later** |
| --- | ----|
| **PIN or password configuration** |  Quarantined |
| **Device encryption** | Quarantined |
| **Jailbroken or rooted device** | Quarantined (not a setting) |
| **email profile** | Not applicable |
| **Minimum OS version** | Quarantined |
| **Maximum OS version** |   Quarantined |
| **Windows health attestation** | Not applicable |

--------------------------

**Remediated** = The device operating system enforces compliance. For example, the user is forced to set a PIN.

**Quarantined** = The device operating system doesn't enforce compliance. For example, Android devices don't force the user to encrypt the device. When the device is not compliant, the following actions take place:

  - The device is blocked if a conditional access policy applies to the user.
  - The company portal notifies the user about any compliance problems.

## Create a device compliance policy

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. For **Platform**, select **Android**. 
5. Choose **Settings Configure**. Enter the **Device Health**, **Device Properties**, and **System Security** settings, as described in this article.

## Device health

- **Rooted devices**: Choose **Block** to mark rooted (jailbroken) devices as not compliant. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.
- **Require the device to be at or under the Device Threat Level**: Use this setting to take the risk assessment from the Lookout MTP solution as a condition for compliance. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance. To use this setting, choose the allowed threat level:
  - **Secured**: This option is the most secure, as the device can't have any threats. If the device is detected with any level of threats, it's evaluated as noncompliant.
  - **Low**: The device is evaluated as compliant if only low-level threats are present. Anything higher puts the device in a noncompliant status.
  - **Medium**: The device is evaluated as compliant if existing threats on the device are low or medium level. If the device is detected to have high-level threats, it's determined to be noncompliant.
  - **High**: This option is the least secure, and allows all threat levels. It may be useful if you're using this solution only for reporting purposes.
- **Google Play Services is configured**: **Require** that the Google Play services app is installed and enabled. Google Play services allows security updates, and is a base-level dependency for many security features on certified-Google devices. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.
- **Up-to-date security provider**: **Require** that an up-to-date security provider can protect a device from known vulnerabilities. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.
- **Threat scan on apps**: **Require** that the Android **Verify Apps** feature is enabled. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.

  > [!NOTE]
  > On the legacy Android platform, this feature is a compliance setting. Intune can only check whether this setting is enabled at the device level.

- **SafetyNet device attestation**: Enter the level of [SafetyNet attestation](https://developer.android.com/training/safetynet/attestation.html) that must be met. Your options:
  - **Not configured** (default): Setting isn't evaluated for compliance or non-compliance.
  - **Check basic integrity**
  - **Check basic integrity & certified devices**

## Device property settings

- **Minimum OS version**: When a device doesn't meet the minimum OS version requirement, it's reported as noncompliant. A link with information about how to upgrade is shown. The end user can choose to upgrade their device, and then get access to company resources.
- **Maximum OS version**: When a device is using an OS version later than the version specified in the rule, access to company resources is blocked. The user is asked to contact their IT admin. Until a rule is changed to allow the OS version, this device can't access company resources.

## System security settings

### Password

- **Require a password to unlock mobile devices**: **Require** users to enter a password before they can access their device. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.
- **Minimum password length**: Enter the minimum number of digits or characters that the user's password must have.
- **Required password type**: Choose if a password should include only numeric characters, or a mix of numerals and other characters. Your options:
  - **Device Default**
  - **Low security biometric**
  - **At least numeric** (default)
  - **Numeric complex**: Repeated or consecutive numerals, such as `1111` or `1234`, aren't allowed.
  - **At least alphabetic** 
  - **At least alphanumeric**
  - **At least alphanumeric with symbols**

- **Maximum minutes of inactivity before password is required**: Enter the idle time before the user must reenter their password. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.
- **Password expiration (days)**: Select the number of days before the password expires and the user must create a new password.
- **Number of previous passwords to prevent reuse**: Enter the number of recent passwords that can't be reused. Use this setting to restrict the user from creating previously used passwords.

### Encryption

- **Encryption of data storage on a device** (Android 4.0 and above, or KNOX 4.0 and above): Choose **Require** to encrypt data storage on your devices. Devices are encrypted when you choose the **Require a password to unlock mobile devices** setting. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.

### Device Security

- **Block apps from unknown sources**: Choose to **block** devices with "Security > Unknown Sources" enabled sources (supported on Android 4.0 – Android 7.x; not supported by Android 8.0 and later). When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.

  To side-load apps, unknown sources must be allowed. If you're not side-loading Android apps, then set this feature to **Block** to enable this compliance policy. 

  > [!IMPORTANT]
  > Side-loading applications require that the **Block apps from unknown sources** setting is enabled. Enforce this compliance policy only if you're not side-loading Android apps on devices.

- **Company portal app runtime integrity**: Choose **Require** to confirm the Company Portal app meets all the following requirements:

  - Has the default runtime environment installed
  - Is properly signed
  - Isn't in debug-mode
  - Is installed from a known source

  When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.

- **Block USB debugging on device** (Android 4.2 or later): Choose **Block** to prevent devices from using the USB debugging feature. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.
- **Minimum security patch level** (Android 6.0 or later): Select the oldest security patch level a device can have. Devices that aren't at least at this patch level are noncompliant. The date must be entered in the `YYYY-MM-DD` format.
- **Restricted apps**: Enter the **App name** and **App bundle ID** for apps that should be restricted. Choose **Add**. A device with at least one restricted app installed is marked as non-compliant.

When done, select **OK** > **OK** to save your changes.

## Locations

In your policy, choose from existing locations. Don't have a location yet? [Use Locations (network fence) in Intune](use-network-locations.md) provides some guidance.

1. Choose **Locations**.
2. From the list, check your location, and choose **Select**.
3. **Save** the policy.

## Actions for noncompliance

Select **Actions for noncompliance**. The default action marks the device as noncompliant immediately.

You can change the schedule when the device is marked non-compliant, such as after one day. You can also configure a second action that sends an email to the user when the device isn't compliant.

[Add actions for noncompliant devices](actions-for-noncompliance.md) provides more information, including creating a notification email to your users.

For example, you're using the Locations feature, and add a location in a compliance policy. The default action for noncompliance applies when you select at least one location. If the device isn't connected to the selected locations, it's immediately considered not compliant. You can give your users a grace period, such as one day.

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
[Compliance policy settings for Android Enterprise](compliance-policy-create-android-for-work.md)
