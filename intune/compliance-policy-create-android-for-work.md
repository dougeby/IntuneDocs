---
# required metadata

title: Create compliance policy for Android for Work
titleSuffix: "Azure portal"
description: Learn how to create a compliance policy for Android for Work devices."
keywords:
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 02/22/2018
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
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to create a device compliance policy for Android for Work devices in Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Compliance policies are created for each platform.  You can create a compliance policy in the Azure portal. To learn more about compliance policies, see [What is  device compliance](device-compliance.md). To learn about the prerequisites that you need to address before creating a compliance policy, see [Get started with device compliance](device-compliance-get-started.md).

The following table describes how noncompliant settings are managed when a compliance policy is used with a conditional access policy.

--------------------------

|**policy setting**| **Android for Work** |
| --- | --- |
| **PIN or password configuration** |  Quarantined |
| **Device encryption** |  Quarantined |
| **Jailbroken or rooted device** | Quarantined (not a setting) |
| **email profile** | Not applicable |
| **Minimum OS version** | Quarantined |
| **Maximum OS version** | Quarantined |
| **Windows health attestation** |Not applicable |

**Remediated** = The device operating system enforces compliance. (For example, the user is forced to set a PIN.)+

**Quarantined** = The device operating system does not enforce compliance. (For example, Android devices do not force the user to encrypt the device.) When the device is not compliant, the following actions take place:

- If a conditional access policy applies to the user, the device is blocked.
- The company portal notifies the user about any compliance problems.

## Create a compliance policy in the Azure portal

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
1. From the **Intune** pane, choose **Device compliance**. Under **Manage**, choose **Policies** and choose **Create policy**.
2. Type a name, description and choose the platform that you want this policy to apply to.
3. Choose **Settings Configure** to specify the **System Security**, **Device Health**, and **Device Properties** settings here. When you are done, choose **OK**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## Assign user groups

To assign a compliance policy to users, choose a policy that you have configured. Existing policies can be found in the **Device compliance – Policies** pane.

1. Choose the policy you want to assign to users and choose **Assignments**. This opens the pane where you can select **Azure Active Directory security groups** and assign them to the policy.
2. Choose **Selected groups** to open the pane that displays the Azure AD security groups.  Choosing **Save**  deploys the policy to users.

You have applied the policy to users.  The devices used by the users who are targeted by the policy will be evaluated for compliance.

<!--- ##  Compliance policy settings--->

## System security settings

### Password

- **Require a password to unlock mobile devices**: Set this to **Yes** to require users to enter a password before they can access their device.
- **Minimum password length**: Specify the minimum number of digits or characters that the password must contain.
- **Password quality**: This setting detects if the password requirements you specify is configured on the device. Enable this setting to require that users configure certain password requirements for Android devices. Choose from:
  - **Low security biometric**
  - **Required**
  - **At least numeric**
  - **At least alphabetic**
  - **At least alphanumeric**
  - **Alphanumeric with symbols**

- **Minutes of inactivity before password is required**: Specifies the idle time before the user must re-enter their password.
- **Password expiration (days)**: Select the number of days before the user&#39;s password expires and they must create a new one.
- **Remember password history**: Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.
- **Prevent reuse of previous passwords**: If **Remember password history** is selected, specify the number of previously used passwords that cannot be reused.
- **Require a password when the device returns from an idle state**: This setting should be used with the **Minutes of inactivity before password is required** setting. End users are prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.


### Encryption

- **Require encryption on mobile device**: You don't have to configure this setting because Android for Work devices enforce encryption.


## Device health and security settings

- **Device must not be jailbroken or rooted**: If you enable this setting, jailbroken devices are evaluated as noncompliant.
- **Require that devices prevent installation of apps from unknown sources**: You do not have to configure this setting as Android for Work devices always restrict installation from unknown sources.
- **Require that USB debugging is disabled**: You do not have to configure this setting because USB debugging is already disabled on Android for Work devices.
- **Minimum Android security patch level**: Use this setting to specify the minimum Android patch level. Devices that are not at least at this patch level will be noncompliant. The date must be specified the format: YYYY-MM-DD.
- **Require device threat protection to be enabled**: Use this setting to take the risk assessment from the Lookout MTP solution as a condition for compliance. Select the maximum allowed threat level, which is one of the following:
  - **None (secured)** This is the most secure. This means that the device cannot have any threats. If the device is detected as having any level of threats, it is evaluated as noncompliant.
  - **Low**: Device is evaluated as compliant if only low-level threats are present. Anything higher puts the device in a noncompliant status.
  - **Medium**: Device is evaluated as compliant if the threats that are present on the device are low or medium level. If the device is detected to have high-level threats, it is determined as noncompliant.
  - **High**: This is the least secure. Essentially, this allows all threat levels, and perhaps only useful if you are using this solution only for reporting purposes.

## Device property settings

- **Minimum OS required**: When a device does not meet the minimum OS version requirement, it is reported as noncompliant. A link with information on how to upgrade is displayed. The end user can choose to upgrade their device after which they can access company resources.
- **Maximum OS version allowed**: When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
