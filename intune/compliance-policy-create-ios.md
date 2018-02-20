---
# required metadata

title: How to create a compliance policy for iOS
titleSuffix: "Azure portal"
description: Learn how to create a compliance policy for iOS devices."
keywords:
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: muhosabe
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to create a device compliance policy for iOS devices in Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Compliance policies are created for each platform.  You can create a compliance policy in the Azure portal. To learn more about what compliance policy is see [what is a device compliance](device-compliance.md) topic. To learn about the prerequisites that you need to address before creating a compliance policy see [Get started with device compliance](device-compliance-get-started.md) topic.

The table below describes how noncompliant settings are managed when a compliance policy is used with a conditional access policy.

-------------------------------


| **Policy setting** | **iOS 8.0 and later** |
| --- | --- |
| **PIN or password configuration** | Remediated |   
| **Device encryption** | Remediated (by setting PIN) |
| **Jailbroken or rooted device** | Quarantined (not a setting)
| **Email profile** | Quarantined |
|**Minimum OS version** | Quarantined |
| **Maximum OS version** | Quarantined |  
| **Windows health attestation** | Not applicable |  
----------------------------


**Remediated** = The device operating system enforces compliance. (For example, the user is forced to set a PIN.)

**Quarantined** = The device operating system does not enforce compliance. (For example, Android devices do not force the user to encrypt the device.) When the devices is not compliant, the following actions take place:

- The device is blocked if a conditional access policy applies to the user.
- The company portal notifies the user about any compliance problems.

## Create a compliance policy in the Azure portal

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **More Services** > **Intune**. Intune is located in the **Monitoring + Management** section.
1. From the **Intune** pane, choose **Device compliance**. Under **Manage**, choose **Policies** and choose **Create policy**.
2. Type a name, description and choose the platform that you want this policy to apply to.
3. Choose **Settings Configure** to specify the **System Security**, **Device Health**, and **Device Properties** settings here. When you are done, choose **OK**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## Assign user groups

To assign a compliance policy to users, choose a policy that you have configured. Existing policies can be found in the **Device compliance – Policies** pane.

1. Choose the policy you want to assign to users and choose **Assignments**. This opens the pane where you can select **Azure Active Directory security groups** and assign them to the policy.
2. Choose **Selected groups** to open the pane that displays the Azure AD security groups.  Choosing **Save** deploys the policy to users.

You have applied the policy to users.  The devices used by the users who are targeted by the policy are evaluated for compliance.

<!---## Compliance policy settings--->

## System security settings

### Password

- **Require a password to unlock mobile devices** : Set this to **Yes** to require the user to enter a password before they can access their device. iOS devices that use a password are encrypted.
- **Allow simple passwords** : Set this to **Yes** to let the user create a simple password like **1234** or **1111**.
- **Minimum password length** : Specify the minimum number of digits or characters that the password must have.
- **Required password type** : Specify whether the user must create an **Alphanumeric** password or a **Numeric** password.
- **Minimum number of character sets** : If you set **Required password type** to **Alphanumeric** , use this setting to specify the minimum number of character sets that the password must have. The four character sets are:
  - Lowercase letters
  - Uppercase letters
  - Symbols
  - Numbers

Setting a higher number will require the user to create a password that is more complex.

For iOS devices, this setting refers to the number of special characters (for example, **!** , **#** , **&amp;** ) that must be included in the password.

- **Minutes of inactivity before password is required** : Specify the idle time before the user must reenter their password.
- **Password expiration (days)**: Select the number of days before the password expires and they must create a new one.
- **Remember password history** : Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.
- **Prevent reuse of previous passwords** : If you selected **Remember password history** , specify the number of previously used passwords that cannot be reused.
- **Require a password when the device returns from an idle state** : Use this setting together with the in the **Minutes of inactivity before password is required** setting. The user is prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.

### Email profile

- **Email account must be managed by Intune** : When this option is set to **Yes** , the device must use the email profile deployed to the device. The device is considered noncompliant in the following situations:
  - The email profile is deployed to a user group other than the user group that the compliance policy targets.
  - The user has already set up an email account on the device that matches the Intune email profile deployed to the device. Intune cannot overwrite the user-provisioned profile, and therefore cannot manage it. To ensure compliance, the user must remove the existing email settings. Then, Intune can install the managed email profile.
- **Select the email profile that must be managed by Intune** : If the **Email account must be managed by Intune** setting is selected, choose **Select** to specify the Intune email profile. The email profile must be present on the device.

For details about email profile, see [Configure access to corporate email using email profiles with Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune).

## Device health settings

- **Device must not be jailbroken or rooted** : If you enable this setting, jailbroken devices will not be compliant.

## Device properties

- **Minimum OS required** : When a device does not meet the minimum OS version requirement, it is reported as noncompliant. A link with information on how to upgrade appears. The user can choose to upgrade their device. After that, they can access company resources.
- **Maximum OS version allowed** : When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
