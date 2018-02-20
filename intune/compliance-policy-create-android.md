---
# required metadata

title: How to create a compliance policy for Android
titleSuffix: "Azure portal"
description: Learn how to create a compliance policy for Android devices."
keywords:
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
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
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to create a device compliance policy for Android devices in Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Device compliance policies are created for each platform form the Intune Azure portal. 

- To learn more about what compliance policy is see [What is a device compliance](device-compliance.md) topic.
- To learn about the prerequisites that you need to address before creating a compliance policy see [Get started with device compliance](device-compliance-get-started.md) topic.

## To create a device compliance policy

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **More Services** > **Intune**. Intune is located in the **Monitoring + Management** section.
1. From the **Intune** pane, choose **Device compliance**. Under **Manage**, choose **Policies** and choose **Create policy**.
3. Choose **Settings Configure** to specify the **System Security**, **Device Health**, and **Device Properties** settings here. When you are done, choose **OK**.

<!-- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant based on the configured settings in this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **OK** when you are finished creating all the actions.-->

## To assign user groups

To assign a compliance policy to users, choose a policy that you have configured. Existing policies can be found in the **Device compliance – Policies** pane.

1. Choose the policy and choose **Assignments**. This opens the pane where you can select **Azure Active Directory security groups** and assign them to the policy.
2. Choose **Selected groups** to open the pane that displays the Azure AD security groups. Here you can find the security groups in your Azure Active Directory.  You can select the user groups you want this policy to apply to and choose **Save** to deploy the policy to users.

You have applied the policy to users.  The devices used by the users who are targeted by the policy will be evaluated for compliance.

<!---##  Compliance policy settings--->

## Device health and security settings

- **Device must not be jailbroken or rooted** : If you enable this setting, jailbroken devices will be evaluated as noncompliant.
- **Require that devices prevent installation of apps from unknown sources (Android 4.0 or later)**: To block devices that have **Security** >; **Unknown sources** enabled on the device, enable this setting and set it to **Yes**.

### Important

Side-loading applications require that the **Unknown sources** setting is enabled. Enforce this compliance policy only if you are not side-loading Android apps on devices.

- **Require that USB debugging is disabled (Android 4.2 or later)**: This setting specifies whether to detect the USB debugging option on the device is enabled.
- **Require devices have enabled Scan device for security threats (Android 4.2-4.4)**: This setting specifies that the **Verify apps** feature is enabled on the device.
- **Minimum Android security patch level (Android 6.0 or later)**: Use this setting to specify the minimum Android patch level. Devices that are not at least at this patch level will be noncompliant. The date must be specified in the format YYYY-MM-DD.
- **Require device threat protection to be enabled** : Use this setting to take the risk assessment from the Lookout MTP solution as a condition for compliance. Choose the maximum allowed threat level, which is one of the following:
  - **None (secured)**: This is the most secure. This means that the device cannot have any threats. If the device is detected as having any level of threats, it will be evaluated as noncompliant.
  - **Low** : The device is evaluated as compliant if only low-level threats are present. Anything higher puts the device in a noncompliant status.
  - **Medium** : The device is evaluated as compliant if the threats that are present on the device are low or medium level. If the device is detected to have high-level threats, it is determined to be noncompliant.
  - **High** : This is the least secure. Essentially, this allows all threat levels. Perhaps it is useful if you are using this solution only for reporting purposes.

For more details, see [Enable device threat protection rule in the compliance policy](https://docs.microsoft.com/intune-classic/deploy-use/enable-device-threat-protection-rule-in-compliance-policy).

## System security settings

### Password

- **Require a password to unlock mobile devices** : Set this to **Yes** to require users to enter a password before they can access their device.
- **Minimum password length** : Specify the minimum number of digits or characters that the user&#39;s password must have.
- **Password quality** : This setting detects if the password requirements that you specify are set up on the device. Enable this setting to require that users meet certain password requirements for Android devices. Choose from:
  - **Low security biometric**
  - **Required**
  - **At least numeric**
  - **At least alphabetic**
  - **At least alphanumeric**
  - **Alphanumeric with symbols**
- **Minutes of inactivity before password is required** : Specify the idle time before the user must reenter their password.
- **Password expiration (days)**: Select the number of days before the password expires and they must create a new one.
- **Remember password history** : Use this setting together with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.
- **Prevent reuse of previous passwords** : If you selected **Remember password history** , specify the number of previously used passwords that cannot be reused.
- **Require a password when the device returns from an idle state** : Use this setting together with the **Minutes of inactivity before password is required** setting. The user is prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.

### Encryption

- **Require encryption on mobile device** : Set this to **Yes** to require devices to be encrypted in order to connect to resources. Devices are encrypted when you choose the setting **Require a password to unlock mobile devices**.

## Device property settings

- **Minimum OS required** : When a device does not meet the minimum OS version requirement, it is reported as noncompliant. A link with information on how to upgrade is shown. The user can choose to upgrade their device, after which they can access company resources.
- **Maximum OS version allowed** : When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rules to allow the OS version, this device cannot be used to access company resources.

## How noncompliant settings work with conditional access policies?

The table below describes how noncompliant settings are managed when a compliance policy is used with a conditional access policy.

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

**Remediated** = The device operating system enforces compliance. (For example, the user is forced to set a PIN.)+

**Quarantined** = The device operating system does not enforce compliance. (For example, Android devices do not force the user to encrypt the device.) When the devices is not compliant, the following actions take place:+

- The device is blocked if a conditional access policy applies to the user.
- The company portal notifies the user about any compliance problems.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
