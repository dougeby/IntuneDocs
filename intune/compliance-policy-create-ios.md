---
# required metadata

title: Create iOS device compliance policy in Microsoft Intune - Azure | Microsoft Docs
description: Create a Microsoft Intune device compliance policy for iOS devices to enter an email account, check jailborken devices, check the  minimum and maximum operating system, and set the password restrictions, including password length and device inactivity.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/20/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Add a device compliance policy for iOS devices in Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

An Intune iOS device compliance policy determines the rules and settings that iOS devices must meet to be compliant. When you use device compliance policies with conditional access, you can allow or block access to company resources. You can also get device reports and take actions for non-compliance. Device compliance policies for each platform can be created in the Intune Azure portal. To learn more about compliance policies and the prerequisites you need before creating a compliance policy, see [Get started with device compliance](device-compliance-get-started.md).

The following table describes how noncompliant settings are managed when a compliance policy is used with a conditional access policy.

| **Policy setting** | **iOS 8.0 and later** |
| --- | --- |
| **PIN or password configuration** | Remediated |
| **Device encryption** | Remediated (by setting PIN) |
| **Jailbroken or rooted device** | Quarantined (not a setting)
| **Email profile** | Quarantined |
|**Minimum OS version** | Quarantined |
| **Maximum OS version** | Quarantined |
| **Windows health attestation** | Not applicable |

**Remediated** = The device operating system enforces compliance. (For example, the user is forced to set a PIN.)

**Quarantined** = The device operating system does not enforce compliance. (For example, Android devices do not force the user to encrypt the device.) When the device is not compliant, the following actions take place:

- The device is blocked if a conditional access policy applies to the user.
- The company portal notifies the user about any compliance problems.

## Create a compliance policy in the Azure portal

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services**, filter on **Intune**, and select **Microsoft Intune**.
3. Select **Device compliance** > **Policies** > **Create Policy**.
4. Enter a name, description, and choose the platform that you want this policy to apply.
5. Choose **Settings** to enter the **Email**, **Device Health**, **Device Properties**, and **System Security** settings. When you're done, choose **OK**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## Assign user groups

To assign a compliance policy to users, choose a policy that you have configured. Existing policies can be found in the **Device compliance – Policies** pane.

1. Choose the policy you want to assign to users and choose **Assignments**. A pane opens where you can select **Azure Active Directory security groups** and assign them to the policy.
2. Choose **Selected groups** to open the pane that displays the Azure AD security groups.  Choosing **Save**  deploys the policy to users.

You have applied the policy to users.  The devices used by the users who are targeted by the policy are evaluated for compliance.

<!---## Compliance policy settings--->

## Email

- **Email account must be managed by Intune**: When this option is set to **Yes**, the device must use the email profile deployed to the device. The device is considered noncompliant in the following situations:
  - The email profile is deployed to a user group other than the user group that the compliance policy targets.
  - The user has already set up an email account on the device that matches the Intune email profile deployed to the device. Intune cannot overwrite the user-provisioned profile, and therefore cannot manage it. To ensure compliance, the user must remove the existing email settings. Then, Intune can install the managed email profile.
- **Select the email profile that must be managed by Intune**: If the **Email account must be managed by Intune** setting is selected, choose **Select** to specify the Intune email profile. The email profile must be present on the device.

For details about email profile, see [Configure access to corporate email using email profiles with Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune).

## Device health

- **Jailbroken devices**: If you enable this setting, jailbroken devices are not compliant.
- **Require the device to be at or under the Device Threat Level**: Choose the maximum threat level to mark devices as noncompliant. For example, if you set the threat level to **Medium**, then devices at medium, low, or secured are compliant. Devices with a high threat level are noncompliant.

## Device properties

- **Minimum OS required**: When a device does not meet the minimum OS version requirement, it is reported as noncompliant. A link with information on how to upgrade is shown. The user can choose to upgrade their device. After that, they can access company resources.
- **Maximum OS version allowed**: When a device uses an OS version later than the version specified in the rule, access to company resources is blocked. The user is then asked to contact their IT admin. Until there is a change in rule to allow the OS version, this device cannot access company resources.

## System security

### Password

> [!NOTE]
> After a compliance or configuration policy is applied to an iOS device, users are prompted to set a passcode every 15 minutes. Users are continually prompted until a passcode is set.

- **Require a password to unlock mobile devices**: Set to **Yes** to require the user to enter a password before they can access their device. iOS devices that use a password are encrypted.
- **Simple passwords**: Set to **Yes** to let the user create a password like **1234** or **1111**.
- **Minimum password length**: Enter the minimum number of digits or characters that the password must have.
- **Required password type**: Enter whether the user must create an **Alphanumeric** password, or a **Numeric** password.
- **Number of non-alphanumeric characters in password**: Enter the minimum number of special characters (&, #, %, !, and so on) that must included in the password.

    Setting a higher number requires the user to create a password that is more complex.

- **Maximum minutes of inactivity before password is required**: Enter the idle time before the user must reenter their password.
- **Password expiration (days)**: Select the number of days before the password expires and they must create a new one.
- **Number of previous passwords to prevent reuse**: Enter the number of previously-used passwords that cannot be used.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
