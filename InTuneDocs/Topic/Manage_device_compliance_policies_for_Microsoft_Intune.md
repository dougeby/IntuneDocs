---
title: Manage device compliance policies for Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
author: karthikaraman
---
# Manage device compliance policies for Microsoft Intune
**Compliance policies** define the rules and settings that a device must comply with in order to be considered compliant by conditional access polices. You can also use compliance policies to monitor and remediate compliant issues with devices independently of conditional access.

These rules include:

-   PIN and passwords

-   Encryption

-   Whether the device is jailbroken or rooted, or if the device is reported as unhealthy by the Windows device health attestation service.

-   Whether email on the device is managed by an [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policy

-   Minimum OS version required - Typically this depends on your company compliance policies and security requirements. This helps to prevent access to devices that might have security vulnerabilities because they are using an older OS version.

-   Maximum OS version allowed - You may choose not to support the latest OS version available before testing or other reasons. You can choose to block devices that have a version later than the one you have specified.   The device will not be able to access company resources until the policy is changed.

> [!NOTE]
> -   Windows PCs with Windows Operating System version 8.1 are reported as 6.3 instead of 8.1.    If the OS version rule is set to Windows 8.1 for Windows, then the device will be reported as noncompliant even if the device has Windows 8.1. Make sure you are setting the right **reported** version of Windows for the Minimum and Maximum OS rules. The version number must match the version returned when you run winver from the command prompt.
> 
>     Windows Phones do not have this issue, the version is reported as 8.1 as expected.
> -   Windows PCs with Windows 10 operating system, the version should be set as "10.0"+ the OS Build number returned by the winver command. For example, it could be something like 10.0.10586.
> ![CA_Win10OSVersion](/Image/CA_Win10OSVersion.png)
>     Windows 10 Mobile does not have this issue.

You deploy compliance policies to users and devices. When a compliance policy is deployed to a user, then all of the users devices are checked for compliance.

The following table lists the device types supported by compliance policies and how noncompliant settings are managed when the policy is used with a conditional access policy.

|Policy Setting|Windows 8.1 and later|Windows Phone 8.1 and later|iOS 6.0 and later|Android 4.0 and later|Samsung KNOX Standard 4.0 and later|
|------------------|-------------------------|-------------------------------|---------------------|-------------------------|---------------------------------------|
**PIN or Password Configuration**|Remediated|Remediated|Remediated|Quarantined|Quarantined
**Device encryption**|N/A|Remediated|Remediated (by setting PIN)|Quarantined|Quarantined
**Jailbroken or rooted device**|N/A|N/A|Quarantined (not a setting)|Quarantined (not a setting)|Quarantined (not a setting)|
**Email profile**|N/A|N/A|Quarantined|N/A|N/A
**Minimum OS version**|Quarantined|Quarantined|Quarantined|Quarantined|Quarantined
**Maximum OS version**|Quarantined|Quarantined|Quarantined|Quarantined|Quarantined
**Windows health attestation**|Windows 10 and Windows 10 Mobile are Quarantined.<br /><br />Setting is not applicable to Windows 8.1|N/A|N/A|N/A|N/A
    
**Remediated** = Compliance is enforced by the device operating system (for example, the user is forced to set a PIN).  There is never a case when the setting will be noncompliant.

**Quarantined** = The device operating system does not enforce compliance (for example, Android devices do not force the user to encrypt the device).  In this case:

-   The device will be blocked if the user is targeted by a conditional access policy.

-   The company portal or web portal will notify the user about any compliance issues.

## <a name="BKMK_Compliance"></a>Step 1: Create a compliance policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Compliance Policies** &gt; **Add**.

2.  On the **Create Policy** page, configure the settings you require:

    |Setting name|More information|Supported platforms|
    |----------------|--------------------|-----------------------|
    |**Name**|Enter a unique name for the compliance policy.|All|
    |**Description**|Provide a description that gives an overview of the compliance policy.|All|
    |**Require a password to unlock mobile devices**|Require users to enter a password before they can access their device.|Windows Phone 8 and later<br /><br />iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
    |**Allow simple passwords**|Let users create simple passwords such as ‘**1234**’ or ‘**1111**’.|Windows Phone 8 and later<br /><br />iOS 6 and later|
    |**Minimum password length**<sup>1</sup>|Specifies the minimum number of digits or characters that the user’s password must contain.|Windows Phone 8 and later<br /><br />Windows 8.1<br /><br />iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
    |**Required password type**|Specifies whether users must create an **Alphanumeric**, or a **Numeric** password.|Windows Phone 8 and later<br /><br />Windows RT and Windows RT 8.1<br /><br />Windows 8.1<br /><br />iOS 6 and later|
    |**Minimum number of character sets**<sup>1</sup>|If **Required password type** is set to **Alphanumeric**, this setting specifies the minimum number of character sets that the password must contain.<br /><br />The four character sets are:<br /><br />-   Lowercase letters<br />-   Uppercase letters<br />-   Symbols<br />-   Numbers<br /><br />Setting a higher number for this setting will require users to create more complex passwords.<br /><br />For iOS devices, this setting refers to the number of special characters (for example, **!**, **#**, **&amp;**) that must be included in the password.|Windows Phone 8 and later<br /><br />Windows RT and Windows RT 8.1<br /><br />Windows 8.1<br /><br />iOS 6 and later|
    |**Password quality**|Configures password requirements for Android devices. Choose from:<br /><br />-   **Low security biometric**<br />-   **Required**<br />-   **At least numeric**<br />-   **At least alphabetic**<br />-   **At least alphanumeric**<br />-   **Alphanumeric with symbols**|Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
    |**Minutes of inactivity before password is required**|Specifies the idle time before the user must re-enter their password.|Windows Phone 8 and later<br /><br />Windows RT and Windows RT 8.1<br /><br />Windows 8.1<br /><br />iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
    |**Password expiration (days)**|Select the number of days before the user’s password expires and they must create a new one.|Windows Phone 8 and later<br /><br />Windows RT and Windows RT 8.1<br /><br />Windows 8.1<br /><br />iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
    |**Remember password history**|Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.|Windows Phone 8 and later<br /><br />Windows RT and Windows RT 8.1<br /><br />Windows 8.1<br /><br />iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
    |**Prevent reuse of previous passwords**|If **Remember password history** is selected, specify the number of previously used passwords that cannot be re-used.|Windows Phone 8 and later<br /><br />Windows RT and Windows RT 8.1<br /><br />Windows 8.1<br /><br />iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
    |**Require a password when the device returns from an idle state**|This setting should be used together with the in the **Minutes of inactivity before password is required** setting. The end-users will be prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.|Windows 10 Mobile|
    |**Require encryption on mobile device**|Requires the device to be encrypted in order to connect to resources.<br /><br />Devices that run Windows Phone 8 are automatically encrypted. **Important:** Devices that run iOS are encrypted when you configure the setting **Require a password to unlock mobile devices**.|Windows Phone 8 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
    |**Require devices to be reported as healthy**|You can set a rule to require that Windows 10 devices must be reported as healthy in new or existing Compliance Policies.  If this setting is enabled, Windows 10 devices will be evaluated via the Health Attestation Service (HAS) for  the following data points:<br /><br />-   BitLocker is enabled<br />    When Bitlocker is on, the device is able to protect data that is stored on the drive from unauthorized access, when the system is turned off or goes to hibernation. <br />    Windows BitLocker Drive Encryption encrypts all data stored on the Windows operating system volume. BitLocker uses the TPM to help protect the Windows operating system and user data and helps to ensure that a computer is not tampered with, even if it is left unattended, lost, or stolen.<br />    If the computer is equipped with a compatible TPM, BitLocker uses the TPM to lock the encryption keys that protect the data. As a result, the keys cannot be accessed until the TPM has verified the state of the computer.<br />-   Code integrity is enabled<br />    Code integrity is a feature that validates the integrity of a driver or system file each time it is loaded into memory. Code integrity detects whether an unsigned driver or system file is being loaded into the kernel, or whether a system file has been modified by malicious software that is being run by a user account with administrator privileges.<br />-   Secure boot is enabled<br />    When Secure Boot is enabled, the system is forced to boot to a factory trusted state. Also, when Secure Boot is enabled, the core components used to boot the machine must have correct cryptographic signatures that are trusted by the organization that manufactured the device. The UEFI firmware verifies this before it lets the machine start. If any files have been tampered with, breaking their signature, the system will not boot.<br />-   Early-launch antimalware is enabled (this setting only applies to PCs.)<br />    Early launch anti-malware (ELAM) provides protection for the computers in your network when they start up and before third-party drivers initialize.<br /><br />This rule is turned off by default. For information on how the HAS service works, see [Health Attestation CSP](https://msdn.microsoft.com/en-us/library/dn934876.aspx).|Windows 10<br /><br />Windows 10 Mobile|
    |**Device must not be jailbroken or rooted**|If enabled, jailbroken (iOS), or rooted (Android) devices will not be compliant.|iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
    |**Email account must be managed by Intune**|When this option is selected, the device will be reported as noncompliant if the user has set up an email account on the device that matches an Intune email profile that was deployed to the device by an IT admin. Intune cannot overwrite the user-provisioned profile, and therefore cannot manage it.<br /><br />To ensure compliance, the user must remove the existing email settings, then, Intune can install the managed email profile.<br /><br />For details about email profiles, see [Configure access to corporate email using email profiles with Microsoft Intune](../Topic/Configure_access_to_corporate_email_using_email_profiles_with_Microsoft_Intune.md).|iOS 6 and later|
    |**Select the email profile that must be managed by Intune**|If **Email account must be managed by Intune** is selected, click **Select** to choose the Intune email profile that devices must be managed by. The email profile must be present on the device.|iOS 6 and later
    |**Minimum OS required (one for each platform)**|When  a device does not meet the minimum OS version requirement, it will be reported as non-compliant. A link with information on how to upgrade will be displayed. The end-user can choose to upgrade their device after which they will be able to access company resources.|Windows Phone 8 and later<br /><br />Windows 8.1<br /><br />iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
    |**Maximum OS version allowed (one for each platform)**|When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.|Windows Phone 8 and later<br /><br />Windows 8.1<br /><br />iOS 6 and later<br /><br />Android 4.0 and later<br /><br />Samsung KNOX Standard 4.0 and later|
    <sup>1</sup> For devices that run Windows and are secured with a Microsoft Account, the compliance policy will fail to evaluate correctly if **Minimum password length** is greater than 8 characters or if **Minimum number of character sets** is more than 2.

3.  When you are finished, click **Save Policy**.

The new policy displays in the **Compliance Policies** node of the **Policy** workspace.

## Deploy a compliance policy
Deploy the compliance policy to one or more groups of users or devices in your organization.

For more information about how to deploy policies, see [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use_policies_to_manage_computers_and_mobile_devices_with_Microsoft_Intune.md).

Use the status summary and alerts on the **Overview** page of the **Policy** workspace to identify issues with the policy that require your attention. Additionally, a status summary appears in the **Dashboard** workspace.

## Monitor the compliance policy

#### To view devices that do not conform to a compliance policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Groups**.

2.  Open the **Policy** tab for any device that is compatible with compliance policies.

3.  From the **Filters** drop-down list, select **Does not conform to compliance policy**.

#### To view the Health Attestation Reports

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Reports**.

2.  In the **Health Attestation Report - Create a new report** page, you can view a report with all the Windows 10 health attestation data collected by Intune. You can also create a report with a subset of the data using filters. The filters can be based on the type of device, operating system, or only a subset of data points.

## How Intune policy conflicts are resolved
When conflicts occur due to multiple Intune settings being applied to a device, the following rules apply:

-   If the conflicting settings are from an Intune configuration policy and a compliance policy, the settings in the compliance policy take precedence over the settings in the configuration policy, even if the settings in the configuration policy are more secure.

-   If you have deployed multiple compliance policies, the most secure of these policies will be used.

## Next Steps
You can now use the compliance policy with conditional access policies to control access to services in your organization.

## See Also
[Manage access to email and SharePoint with Microsoft Intune](../Topic/Manage_access_to_email_and_SharePoint_with_Microsoft_Intune.md)

