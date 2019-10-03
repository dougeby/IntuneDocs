---
# required metadata

title: iOS device compliance settings in Microsoft Intune - Azure | Microsoft Docs
description: See a list of all the settings you can use when setting compliance for your iOS devices in Microsoft Intune. Require an email, check jailbroken or rooted devices, set the allowed minimum and maximum operating system, set any password restrictions, including password length and device inactivity, restrict apps, and more.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology:
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# iOS settings to mark devices as compliant or not compliant using Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

This article lists and describes the different compliance settings you can configure on iOS devices in Intune. As part of your mobile device management (MDM) solution, use these settings to require an email, mark rooted (jailbroken) devices as not compliant, set an allowed threat level, set passwords to expire, and more.

This feature applies to:

- iOS

As an Intune administrator, use these compliance settings to help protect your organizational resources. To learn more about compliance policies, and what they do, see [get started with device compliance](device-compliance-get-started.md).

## Before you begin

[Create a compliance policy](create-compliance-policy.md#create-the-policy). For **Platform**, select **iOS**.

## Email

- **Require mobile devices to have a managed email profile**: When set to **Require**, devices that don't have an email profile managed by Intune are considered not compliant. A device can't have a managed email profile when it's not correctly targeted, or if the user manually set up the email account on the device. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.

  The device is considered non-compliant in the following situations:

  - The email profile is assigned to a different user group than the user group targeted by the compliance policy.
  - The user already set up an email account on the device that matches the Intune email profile deployed to the device. Intune can't overwrite the user-configured profile, and Intune can't manage it. To be compliant,  the end user must remove the existing email settings. Then, Intune can install the managed email profile.

- **Select the email profile that must be managed by Intune**: If the **Email account must be managed by Intune** setting is selected, choose **Select** to enter the Intune email profile. The email profile must exist on the device.

For details about email profiles, see [configure access to organization email using email profiles with Intune](../configuration/email-settings-configure.md).

## Device health

- **Jailbroken devices**: Choose **Block** to mark rooted (jailbroken) devices as not compliant. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.
- **Require the device to be at or under the Device Threat Level** (iOS 8.0 and newer): Use this setting to take the risk assessment as a condition for compliance. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance. To use this setting, choose the allowed threat level:
  - **Secured**: This option is the most secure, and means that the device can't have any threats. If the device is detected with any level of threats, it's evaluated as non-compliant.
  - **Low**: The device is evaluated as compliant if only low-level threats are present. Anything higher puts the device in a non-compliant status.
  - **Medium**: The device is evaluated as compliant if the threats that are present on the device are low or medium level. If the device is detected to have high-level threats, it's determined to be non-compliant.
  - **High**: This option is the least secure, as it allows all threat levels. It may be useful if you're using this solution only for reporting purposes.

## Device properties

- **Minimum OS required** (iOS 8.0 and newer): When a device doesn't meet the minimum OS version requirement, it's reported as non-compliant. A link with information on how to upgrade is shown. The end user can choose to upgrade their device. After that, they can access organization resources.
- **Maximum OS version allowed** (iOS 8.0 and newer): When a device uses an OS version later than the version in the rule, access to organization resources is blocked. The end user is asked to contact their IT administrator. The device can't access organization resources until a rule changes to allow the OS version.
- **Minimum OS build version** (iOS 8.0 and newer): When Apple publishes security updates, the build number is typically updated, not the OS version. Use this feature to enter a minimum allowed build number on the device.
- **Maximum OS build version** (iOS 8.0 and newer): When Apple publishes security updates, the build number is typically updated, not the OS version. Use this feature to enter a maximum allowed build number on the device.

## System security

### Password

> [!NOTE]
> After a compliance or configuration policy is applied to an iOS device, users are prompted to set a passcode every 15 minutes. Users are continually prompted until a passcode is set.

- **Require a password to unlock mobile devices**: **Require** users to enter a password before they can access their device. iOS devices that use a password are encrypted.
- **Simple passwords**: Set to **Block** so users can't create simple passwords, such as **1234** or **1111**. Set to **Not configured** to let users create passwords like **1234** or **1111**.
- **Minimum password length**: Enter the minimum number of digits or characters that the password must have.
- **Required password type**: Choose if a password should have only **Numeric** characters, or if there should be a mix of numbers and other characters (**Alphanumeric**).
- **Number of non-alphanumeric characters in password**: Enter the minimum number of special characters, such as `&`, `#`, `%`, `!`, and so on, that must be in the password.

    Setting a higher number requires the user to create a password that is more complex.

- **Maximum minutes of inactivity before password is required**: Enter the idle time before the user must reenter their password.
- **Password expiration (days)**: Select the number of days before the password expires, and they must create a new one.
- **Number of previous passwords to prevent reuse**: Enter the number of previously used passwords that can't be used.

### Device security

- **Restricted apps**: You can restrict apps by adding their bundle IDs to the policy. If a device has the app installed, the device is marked as non-compliant.

  - **App name**: Enter a user-friendly name to help you identify the bundle ID.
  - **App Bundle ID**: Enter the unique bundle identifier assigned by the app provider. To find the bundle ID, see [How to find the bundle ID for an iOS app](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app) (opens another Microsoft web site).  

Select **OK** > **Create** to save your changes.

## Next steps

- [Add actions for noncompliant devices](actions-for-noncompliance.md) and [use scope tags to filter policies](../fundamentals/scope-tags.md).
- [Monitor your compliance policies](compliance-policy-monitor.md).
- See the [compliance policy settings for macOS](compliance-policy-create-mac-os.md) devices.
