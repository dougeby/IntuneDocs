---
# required metadata

title: Create Windows device compliance policy in Microsoft Intune
titleSuffix:
description: Create a Microsoft Intune device compliance policy for Windows devices so you can specify requirements that a device must meet to be compliant.
keywords:
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---
# How to create a device compliance policy for Windows devices in Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

An Intune device compliance policy for Windows specifies the rules and settings that Windows devices must meet to be considered compliant. You can use these policies with conditional access to allow or block access to company resources, and you can get device reports and take actions for non-compliance. You create device compliance policies for each platform in the Intune Azure portal. To learn more about compliance policies and the prerequisites that you need to address before creating a compliance policy, see [Get started with device compliance](device-compliance-get-started.md).

The following table describes how noncompliant settings are managed when a compliance policy is used with a conditional access policy.

---------------------------

| **Policy setting** | **Windows 8.1 and later** | **Windows Phone 8.1 and later** |
|----| ----| --- |
| **PIN or password configuration** | Remediated | Remediated |   
| **Device encryption** | Not applicable | Remediated |   
| **Jailbroken or rooted device** | Not applicable | Not applicable |  
| **Email profile** | Not applicable | Not applicable |   
| **Minimum OS version** | Quarantined | Quarantined |   
| **Maximum OS version** | Quarantined | Quarantined |   
| **Windows health attestation** | Quarantined: Windows 10 and Windows 10 Mobile|Not applicable: Windows 8.1 |

-------------------------------

**Remediated** = The device operating system enforces compliance. (For example, the user is forced to set a PIN.)

**Quarantined** = The device operating system does not enforce compliance. (For example, Android devices do not force the user to encrypt the device.) When the device is not compliant, the following actions take place:

- The device is blocked if a conditional access policy applies to the user.
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
2. Choose **Selected groups** to open the pane that displays the Azure AD security groups.  Choosing **Save** deploys the policy to users.

You have applied the policy to users. The devices used by the users who are targeted by the policy will be evaluated for compliance.

<!---## Compliance policy settings--->

## System security settings

### Password

- **Require a password to unlock mobile devices:** Set this to **Yes** to require users to enter a password before they can access their device.
- **Allow simple passwords:** Set this to **Yes** to let users create simple passwords such as '**1234**' or '**1111**'.
- **Minimum password length:** Specify the minimum number of digits or characters that the user's password must contain.
- **Required password type:** Specify whether users must create an **Alphanumeric**, or a **Numeric** password.

For devices that run Windows and accessed with a Microsoft account, the compliance policy fails to evaluate correctly if minimum password length is greater than eight characters or if minimum number of character sets is more than two.

- **Minimum number of character sets:** If **Required password type** is set to **Alphanumeric** , this setting specifies the minimum number of character sets that the password must contain. The four character sets are:
  - Lowercase letters
  - Uppercase letters
  - Symbols
  - Numbers

Setting a higher number for this setting will require users to create passwords that are more complex. For devices that run Windows and accessed with a Microsoft account, the compliance policy fails to evaluate correctly if minimum password length is greater than eight characters or if minimum number of character sets is more than two.

- **Minutes of inactivity before password is required:** Specifies the idle time before the user must reenter their password.
- **Password expiration (days):** Select the number of days before the user's password expires and they must create a new one.
- **Remember password history:** Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.
- **Prevent reuse of previous passwords:** If **Remember password history** is selected, specify the number of previously used passwords that cannot be re-used.
- **Require a password when the device returns from an idle state:** This setting should be used together with the **Minutes of inactivity before password is required** setting. The end users are prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.

**This setting only applies to Windows 10 Mobile devices.**

### Encryption

- **Require encryption on mobile device:** Set this to **Yes** to require the device to be encrypted in order to connect to resources.



## Device health settings

- **Require devices to be reported as healthy:** You can set a rule to require that **Windows 10 Mobile** devices must be reported as healthy in new or existing Compliance Policies. If this setting is enabled, Windows 10 devices are evaluated via the Health Attestation Service (HAS) for the following data points:
  - **BitLocker is enabled:** When BitLocker is on, the device is able to protect data that is stored on the drive from unauthorized access, when the system is turned off or goes to hibernation. Windows BitLocker Drive Encryption encrypts all data stored on the Windows operating system volume. BitLocker uses the TPM to help protect the Windows operating system and user data and helps to ensure that a computer is not tampered with, even if it is left unattended, lost, or stolen. If the computer is equipped with a compatible TPM, BitLocker uses the TPM to lock the encryption keys that protect the data. As a result, the keys cannot be accessed until the TPM has verified the state of the computer
  - **Code integrity is enabled:** Code integrity is a feature that validates the integrity of a driver or system file each time it is loaded into memory. Code integrity detects whether an unsigned driver or system file is being loaded into the kernel, or whether a system file has been modified by malicious software that is being run by a user account with administrator privileges.
  - **Secure Boot is enabled:** When Secure Boot is enabled, the system is forced to boot to a factory trusted state. Also, when Secure Boot is enabled, the core components used to boot the machine must have correct cryptographic signatures that are trusted by the organization that manufactured the device. The UEFI firmware verifies this before it lets the machine start. If any files have been tampered with, breaking their signature, the system will not boot.

For information on how the HAS service works, see [Health Attestation CSP](https://msdn.microsoft.com/library/dn934876.aspx).

## Device property settings

- **Minimum OS required:** When a device does not meet the minimum OS version requirement, it is reported as noncompliant. A link with information on how to upgrade is displayed. The end user can choose to upgrade their device after which they can access company resources.
- **Maximum OS version allowed:** When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.

<!---## Compliance policy settings for Windows PCs--->

## System security settings

### Password

- **Minimum password length:** - Supported on Windows 8.1.

Specify the minimum number of digits or characters that the user's password must contain.

For devices that are accessed with a Microsoft Account, the compliance policy fails to evaluate correctly if **Minimum password length** is greater than eight characters or if **Minimum number of character sets** is more than two characters.

- **Required password type:** - Supported on Windows RT, Windows RT 8.1, and Windows 8.1

Specify whether users must create an **Alphanumeric**, or a **Numeric** password.

- **Minimum number of character sets:** - Supported on Windows RT, Windows RT 8.1, and Windows 8.1. If **Required password type** is set to **Alphanumeric**, this setting specifies the minimum number of character sets that the password must contain. The four character sets are:
  - Lowercase letters
  - Uppercase letters
  - Symbols
  - Numbers: Setting a higher number for this setting requires users to create passwords that are more complex.

For devices that are accessed with a Microsoft Account, the compliance policy fails to evaluate correctly if **Minimum password length** is greater than eight characters or if **Minimum number of character sets** is more than two characters.

- **Minutes of inactivity before password is required:** - Supported on Windows RT, Windows RT 8.1, and Windows 8.1

Specify the idle time before the user must reenter their password.

- **Password expiration (days):** -Supported on Windows RT, Windows RT 8.1, and Windows 8.1.

Select the number of days before the user's password expires and they must create a new one.

- **Remember password history:** - Supported on Windows RT, Windows RT, and Windows 8.1.

Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.

- **Prevent reuse of previous passwords:** - Supported on Windows RT, Windows RT 8.1, and Windows 8.1

If **Remember password history:** is selected, specify the number of previously used passwords that cannot be reused.


## Device health settings

- **Require devices to be reported as healthy:** - Supported on Windows 10 devices. You can set a rule to require that Windows 10 devices must be reported as healthy in new or existing Compliance Policies. If this setting is enabled, Windows 10 devices are evaluated via the Health Attestation Service (HAS) for the following data points:
  - **BitLocker is enabled:** When BitLocker is on, the device is able to protect data that is stored on the drive from unauthorized access, when the system is turned off or goes to hibernation. Windows BitLocker Drive Encryption encrypts all data stored on the Windows operating system volume. BitLocker uses the TPM to help protect the Windows operating system and user data and helps to ensure that a computer is not tampered with, even if it is left unattended, lost, or stolen. If the computer is equipped with a compatible TPM, BitLocker uses the TPM to lock the encryption keys that protect the data. As a result, the keys cannot be accessed until the TPM has verified the state of the computer
  - **Code integrity is enabled:** Code integrity is a feature that validates the integrity of a driver or system file each time it is loaded into memory. Code integrity detects whether an unsigned driver or system file is being loaded into the kernel, or whether a system file has been modified by malicious software that is being run by a user account with administrator privileges.
  - **Secure Boot is enabled:** When Secure Boot is enabled, the system is forced to boot to a factory trusted state. Also, when Secure Boot is enabled, the core components used to boot the machine must have correct cryptographic signatures that are trusted by the organization that manufactured the device. The UEFI firmware verifies this before it lets the machine start. If any files have been tampered with, breaking their signature, the system will not boot.
  - **Early-launch antimalware is enabled:** Early launch anti-malware (ELAM) provides protection for the computers in your network when they start up and before third-party drivers initialize.

For information on how the HAS service works, see [Health Attestation CSP](https://msdn.microsoft.com/library/dn934876.aspx).

## Device property settings

- **Minimum OS required:** - Supported on Windows 8.1, and Windows 10.

Specify the major.minor.build number here. The version number must correspond to the version returned by the ```winver``` command.

When a device has an earlier version that the specified OS version, it is reported as noncompliant. A link with information on how to upgrade is displayed. The end user can choose to upgrade their device after which they can access company resources.

- **Maximum OS version allowed:** - Supported on Windows 8.1, and Windows 10.

When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.

To find the OS version to use for the **Minimum OS required**, and **Maximum OS version allowed** settings, run the **winver** command from the command prompt. The winver command returns the reported version of the OS.

- Windows 8.1 PCs return a version of **3**. If the OS version rule is set to Windows 8.1 for Windows, then the device is reported as noncompliant even if the device has Windows 8.1.
- PCs running Windows 10, the version should be set as "10.0"+ the OS Build number returned by the winver command.

## Windows Holographic for Business support

Windows Holographic for Business supports the following setting:

- System Security / Encryption

  **Encryption of data storage on device**.

To verify device encryption on the Microsoft HoloLens, see [Verify device encryption](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption).

## Next steps

See the following topic to learn how you can monitor device compliance:

- [How to monitor device compliance](device-compliance-monitor.md)
