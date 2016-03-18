---
title: Create a compliance policy in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service:
ms.suite: na
ms.tgt_pltfrm: na
ms.topic:
ms.assetid:
author: karthikaraman
---
# Create a compliance policy in Microsoft Intune
## <a name="BKMK_Compliance"></a>Create a compliance policy

Step1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Compliance Policies** &gt; **Add**.

  ![Screenshot of the compliance policy page in the Intune admin console, showing the add option in the menu at the top of page](./media/intune-sa-3a-add-compliance-policy.png)

Step2.  On the **Create Policy** page, configure the settings you require:
  -   The System security settings like password, and encryption
  -   Device health settings like whether or not a device is jailbroken or is reported healthy by the Windows device health attestation service.
  -   Device property settings like the miniumum OS version required or maximum OS version allowed.
![IntuneSA3bCreatePolicy](./media/intune-sa-3b-create-policy.png)

Step3. When you are finished, choose **Save Policy**.

You will be given the option to deploy the policy now, or you can choose to deploy it later. The new policy displays in the **Compliance Policies** node of the **Policy** workspace.

## Compliance policy settings for mobile devices

The following table lists the compliance policy settings that are applicable to mobile devices.

--------------------------------------

|Setting name|More information|Supported platforms|
|----------------|--------------------|---------------------|
|**Name**|Enter a unique name for the compliance policy.|All|
|**Description**|Provide a description that gives an overview of the compliance policy.|All|
|**Require a password to unlock mobile devices**|Require users to enter a password before they can access their device.|Windows Phone 8 and later<br /><br />iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
|**Allow simple passwords**|Let users create simple passwords such as ‘**1234**’ or ‘**1111**’.|Windows Phone 8 and later<br /><br />iOS 6 and later|
|**Minimum password length**<sup>1</sup>|Specifies the minimum number of digits or characters that the user’s password must contain.|Windows Phone 8 and later<br /><br />iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
|**Required password type**|Specifies whether users must create an **Alphanumeric**, or a **Numeric** password.|Windows Phone 8 and later<br /><br />iOS 6 and later|
|**Minimum number of character sets**<sup>1</sup>|If **Required password type** is set to **Alphanumeric**, this setting specifies the minimum number of character sets that the password must contain.<br /><br />The four character sets are:<br /><br />-   Lowercase letters<br />-   Uppercase letters<br />-   Symbols<br />-   Numbers<br /><br />Setting a higher number for this setting will require users to create more complex passwords.<br /><br />For iOS devices, this setting refers to the number of special characters (for example, **!**, **#**, **&amp;**) that must be included in the password.|Windows Phone 8 and later<br /><br />iOS 6 and later|
|**Password quality**|Configures password requirements for Android devices. Choose from:<br /><br />-   **Low security biometric**<br />-   **Required**<br />-   **At least numeric**<br />-   **At least alphabetic**<br />-   **At least alphanumeric**<br />-   **Alphanumeric with symbols**|Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
|**Minutes of inactivity before password is required**|Specifies the idle time before the user must re-enter their password.|Windows Phone 8 and later<br /><br />iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
|**Password expiration (days)**|Select the number of days before the user’s password expires and they must create a new one.|Windows Phone 8 and later<br /><br />iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
|**Remember password history**|Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.|Windows Phone 8 and later<br /><br />Windows 8.1<br /><br />iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
|**Prevent reuse of previous passwords**|If **Remember password history** is selected, specify the number of previously used passwords that cannot be re-used.|Windows Phone 8 and later<br /><br />iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later
|**Require a password when the device returns from an idle state**|This setting should be used together with the in the **Minutes of inactivity before password is required** setting. The end-users will be prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.|Windows 10 Mobile|
|**Require encryption on mobile device**|Requires the device to be encrypted in order to connect to resources.<br /><br />Devices that run Windows Phone 8 are automatically encrypted. **Important:** Devices that run iOS are encrypted when you configure the setting **Require a password to unlock mobile devices**.|Windows Phone 8 and later<br /><br /> Windows 8.1<br /><br/>Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
|**Require devices to be reported as healthy**|You can set a rule to require that Windows 10 devices must be reported as healthy in new or existing Compliance Policies.  If this setting is enabled, Windows 10 devices will be evaluated via the Health Attestation Service (HAS) for  the following data points:<br /><br />-   BitLocker is enabled<br />    -   Code integrity is enabled<br />    -   Secure boot is enabled<br />    -    For more details on these data points, see [Health attestion data points](#BKMK_HAS) described later in this topic. <br/><br>For information on how the HAS service works, see [Health Attestation CSP](https://msdn.microsoft.com/library/dn934876.aspx).|<br />Windows 10 Mobile|
|**Device must not be jailbroken or rooted**|If enabled, jailbroken (iOS), or rooted (Android) devices will not be compliant.|iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
|**Email account must be managed by Intune**|When this option is selected, the device will be reported as noncompliant if the user has set up an email account on the device that matches an Intune email profile that was deployed to the device by an IT admin. Intune cannot overwrite the user-provisioned profile, and therefore cannot manage it.<br /><br />To ensure compliance, the user must remove the existing email settings, then, Intune can install the managed email profile.<br /><br />For details about email profiles, see [Configure access to corporate email using email profiles with Microsoft Intune](../Topic/Configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md).|iOS 6 and later|
|**Select the email profile that must be managed by Intune**|If **Email account must be managed by Intune** is selected, choose **Select** to specify the Intune email profile that devices must be managed by. The email profile must be present on the device.|iOS 6 and later
|**Minimum OS required (one for each platform)**|When  a device does not meet the minimum OS version requirement, it will be reported as non-compliant. A link with information on how to upgrade will be displayed. The end-user can choose to upgrade their device after which they will be able to access company resources.|Windows Phone 8 and later<br /><br />iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
|**Maximum OS version allowed (one for each platform)**|When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.|Windows Phone 8 and later<br /><br />iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
--------
<sup>1</sup> For devices that run Windows and are secured with a Microsoft Account, the compliance policy will fail to evaluate correctly if **Minimum password length** is greater than 8 characters or if **Minimum number of character sets** is more than 2.

## Compliance policy for PCs

The following table lists the compliance policy settings that are applicable to Windows PCs.

------------------------

|Setting name|More information|Supported platforms|
|----------------|--------------------|---------------------|
|**Name**|Enter a unique name for the compliance policy.|All|
|**Description**|Provide a description that gives an overview of the compliance policy.|All|
|**Minimum password length**<sup>1</sup>|Specifies the minimum number of digits or characters that the user’s password must contain.|Windows 8.1|
|**Required password type**|Specifies whether users must create an **Alphanumeric**, or a **Numeric** password.|Windows RT and Windows RT 8.1<br /><br />Windows 8.1<br />|
|**Minimum number of character sets**<sup>1</sup>|If **Required password type** is set to **Alphanumeric**, this setting specifies the minimum number of character sets that the password must contain.<br /><br />The four character sets are:<br /><br />-   Lowercase letters<br />-   Uppercase letters<br />-   Symbols<br />-   Numbers<br /><br />Setting a higher number for this setting will require users to create more complex passwords.<br /><br />|Windows RT and Windows RT 8.1<br /><br />Windows 8.1<br />|
|**Minutes of inactivity before password is required**|Specifies the idle time before the user must re-enter their password.|Windows RT and Windows RT 8.1<br /><br />Windows 8.1<br />|
|**Password expiration (days)**|Select the number of days before the user’s password expires and they must create a new one.|Windows RT and Windows RT 8.1<br /><br />Windows 8.1<br />|
|**Remember password history**|Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.|Windows RT and Windows RT 8.1<br /><br />Windows 8.1|
|**Prevent reuse of previous passwords**|If **Remember password history** is selected, specify the number of previously used passwords that cannot be re-used.|Windows RT and Windows RT 8.1<br /><br />Windows 8.1|
|**Require devices to be reported as healthy**|You can set a rule to require that Windows 10 devices must be reported as healthy in new or existing Compliance Policies.  If this setting is enabled, Windows 10 devices will be evaluated via the Health Attestation Service (HAS) for  the following data points:<br /><br />-   BitLocker is enabled<br />    -   Code integrity is enabled<br />    -   Secure boot is enabled<br />    -   Early-launch antimalware is enabled (this setting only applies to PCs.)This rule is turned off by default. <br> For more details on these data points, see [Health attestion data points](#BKMK_HAS) described later in this topic. <br/> <br>For information on how the HAS service works, see [Health Attestation CSP](https://msdn.microsoft.com/library/dn934876.aspx).|Windows 10|
|**Minimum OS required (one for each platform)**|Specify the major.minor.build number here. The version number must correspond to the version returned by the winver command. <sup>**2**</sup>  <br/><br/>When  a device has a lesser version that the specified OS version, it will be reported as non-compliant. A link with information on how to upgrade will be displayed. The end-user can choose to upgrade their device after which they will be able to access company resources.|Windows 8.1<br/><br /><br />Windows 10<br><br/> |
|**Maximum OS version allowed (one for each platform)**|When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.|Windows 8.1 <br /><br />Windows 10|
----------
<sup>1</sup> For devices that run Windows and are secured with a Microsoft Account, the compliance policy will fail to evaluate correctly if **Minimum password length** is greater than 8 characters or if **Minimum number of character sets** is more than 2 characters.

<sup>**2**</sup> Run the winver command from the command prompt to see the reported version of the OS. Use the version reported when you run this command to specify the minimum and maximum OS version settings.
- Windows 8.1 PCs return a version of **6.3**.    If the OS version rule is set to Windows 8.1 for Windows, then the device will be reported as noncompliant even if the device has Windows 8.1.
- Windows PCs with Windows 10 operating system, the version should be set as "10.0"+ the OS Build number returned by the winver command. For example, it could be something like 10.0.10586.
> ![CA_Win10OSVersion](./media/ca_win10-os-version.png)



### <a name="BKMK_HAS"></a>Health attestation data points
-  **BitLocker is enabled:** When Bitlocker is on, the device is able to protect data that is stored on the drive from unauthorized access, when the system is turned off or goes to hibernation. Windows BitLocker Drive Encryption encrypts all data stored on the Windows operating system volume. BitLocker uses the TPM to help protect the Windows operating system and user data and helps to ensure that a computer is not tampered with, even if it is left unattended, lost, or stolen. If the computer is equipped with a compatible TPM, BitLocker uses the TPM to lock the encryption keys that protect the data. As a result, the keys cannot be accessed until the TPM has verified the state of the computer
-  **Code integrity is enabled:** Code integrity is a feature that validates the integrity of a driver or system file each time it is loaded into memory. Code integrity detects whether an unsigned driver or system file is being loaded into the kernel, or whether a system file has been modified by malicious software that is being run by a user account with administrator privileges.
- **Secure boot is enabled:** When Secure Boot is enabled, the system is forced to boot to a factory trusted state. Also, when Secure Boot is enabled, the core components used to boot the machine must have correct cryptographic signatures that are trusted by the organization that manufactured the device. The UEFI firmware verifies this before it lets the machine start. If any files have been tampered with, breaking their signature, the system will not boot.
- **Early-launch antimalware is enabled (this setting only applies to PCs.):** Early launch anti-malware (ELAM) provides protection for the computers in your network when they start up and before third-party drivers initialize.
## Next Steps
[Deploy and monitor a compliance policy](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### See also
[Introducution to device compliance policies](introduction-to-device-compliance-policies-in-microsoft-intune.md)
