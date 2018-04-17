---
# required metadata

title: Create macOS device compliance policy in Microsoft Intune - Azure | Microsoft Docs
description: Create or configure a Microsoft Intune device compliance policy for macOS devices to use System Integrity Protection, set the minimum and maximum operating system version,  choose your password requirements, and encrypt data storage.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/16/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: muhosabe
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Add a device compliance policy for macOS devices with Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

An Intune macOS device compliance policy determines the rules and settings that macOS devices must meet to be compliant. When you use device compliance policies with conditional access, you can allow or block access to company resources. You can also get device reports and take actions for non-compliance. Device compliance policies for each platform can be created in the Intune Azure portal. To learn more about compliance policies, and any prerequisites, see [Get started with device compliance](device-compliance-get-started.md).

The following table describes how noncompliant settings are managed when a compliance policy is used with a conditional access policy:

---------------------------

| Policy setting | macOS 10.11 and later |
| --- | --- |
| **PIN or password configuration** | Remediated |   
| **Device encryption** | Remediated (by setting PIN) |
| **Email profile** | Quarantined |
|**Minimum OS version** | Quarantined |
| **Maximum OS version** | Quarantined |

---------------------------

**Remediated** = The device operating system enforces compliance. For example, the user is forced to set a PIN.

**Quarantined** = The device operating system does not enforce compliance. (For example, Android devices do not force the user to encrypt the device.) When the device is not compliant, the following actions take place:

- The device is blocked if a conditional access policy applies to the user.
- The company portal notifies the user about any compliance problems.

## Create a device compliance policy

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. For **Platform**, select **macOS**. Choose **Settings Configure**, and enter the **Device Health**, **Device Properties**, and **System Security** settings. When you're done, select **OK**, and **Create**.

## Device Health

- **Require a system integrity protection**: **Require** your macOS devices to have [System Integrity Protection](https://support.apple.com/HT204899) enabled.

## Device properties

- **Minimum OS version**: When a device doesn't meet the minimum OS version requirement, it's reported as noncompliant. A link with information on how to upgrade appears. The end user can choose to upgrade their device, and then get access to company resources.
- **Maximum OS version**: When a device is using an OS version later than the version specified in the rule, access to company resources is blocked. The user is asked to contact their IT admin. Until there is a rule change to allow the OS version, this device can't access company resources.

## System security settings

### Password

- **Require a password to unlock mobile devices**: **Require** users to enter a password before they can access their device.
- **Simple passwords**: Set to **Block** so users can't create simple passwords, such as **1234** or **1111**. Set to **Not configured** to let users create passwords like **1234** or **1111**.
- **Minimum password length**: Enter the minimum number of digits or characters that the password must have.
- **Password type**: Choose if a password should have only **Numeric** characters, or if there should be a mix of numbers and other characters (**Alphanumeric**).
- **Number of non-alphanumeric characters in password**: Enter the minimum number of special characters (&, #, %, !, and so on) that must be included in the password.

    Setting a higher number requires the user to create a password that is more complex.

- **Maximum minutes of inactivity before password is required**: Enter the idle time before the user must reenter their password.
- **Password expiration (days)**: Select the number of days before the password expires, and they must create a new one.
- **Number of previous passwords to prevent reuse**: Enter the number of previously used passwords that cannot be used.

	> [!IMPORTANT]
	> When the password requirement is changed on a macOS device, it doesn’t take effect until the next time the user changes their password. For example, if you set the password length restriction to eight digits, and the macOS device currently has a six digits password, then the device remains compliant until the next time the user updates their password on the device.

### Encryption

- **Encryption of data storage on a device**: Choose **Require** to encrypt data storage on your devices.

## Assign user groups

1. Choose a policy that you've configured. Existing policies are in **Device compliance** > **Policies**.
2. Choose the policy, and choose **Assignments**. You can include or exclude Azure Active Directory (AD) security groups.
3. Choose **Selected groups** to see your Azure AD security groups. Select the user groups you want this policy to apply, and choose **Save** to deploy the policy to users.

> [!TIP]
> By default, devices check for compliance every eight hours. But users can force this process through the Intune Company Portal app.

You have applied the policy to users. The devices used by the users who are targeted by the policy are evaluated for compliance.

## Next steps
[Automate email and add actions for noncompliant devices](actions-for-noncompliance.md)  
[Monitor Intune Device compliance policies](compliance-policy-monitor.md)