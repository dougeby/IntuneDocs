---
# required metadata

title: Intune endpoint protection settings for Windows 10
titleSuffix: "Intune on Azure"
description: Learn the Intune settings you can use to control endpoint protection settings like BitLocker on Windows 10 devices."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: ilwu
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Endpoint protection settings for Windows 10 and later in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The endpoint protection profile let you control security features on Windows 10 devices, like BitLocker, and Windows Defender.

Use the information in this topic to learn how to create endpoint protection profiles.

## Create an endpoint protection profile

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device configuration**.
2. On the **Device Configuration** blade, choose **Manage** > **Profiles**.
3. On the profiles blade, choose **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the device features profile.
5. From the **Platform** drop-down list, select **Windows 10 and later**.
6. From the **Profile type** drop-down list, choose **Endpoint protection**.
7. On the **Windows encryption** blade, configure the settings you want. Use the details in this topic to help you understand what each setting does. When you are finished, choose **OK**.
8. Go back to the **Create Profile** blade, and choose **Create**.

The profile is created and appears on the profiles list blade.

## Windows Defender SmartScreen settings

- **SmartScreen for apps and files** - Enable Windows SmartScreen for file execution, and running apps.
- **Unverified files execution** - Block the end user from running files that have not been verified by Windows SmartScreen.

## Windows encryption settings

### Windows Settings

- **Require devices to be encrypted (Desktop only)** - If enabled, users are prompted to enable device encryption. Additionally, they are asked to confirm that encryption from another provider has not been enabled. If Windows encryption is turned on while another encryption method is active, the device might become unstable.
- **Require Storage Card to be encrypted (mobile only)** - Enable this setting to encrypt any removable storage cards used by the device.


### BitLocker base settings

- **Configure encryption methods** - Enable this setting to configure encryption algorithms for operating system, data, and removable drives.
	- **Encryption for operating system drives** - Choose the encryption method for operating system drives. We recommend you use the XTS-AES algorithm.
	- **Encryption for fixed data-drives** - Choose the encryption method for fixed (built-in) data drives. We recommend you use the XTS-AES algorithm.
	- **Encryption for removable data-drives** - Choose the encryption method for removable data drives. If the removable drive is used with devices that are not running Windows 10, we recommend you use the AES-CBC algorithm.


### BitLocker OS drive settings

- **Require additional authentication at startup** -
	- **BitLocker with non-compatible TPM chip** -
	- **TPM startup** - Configure whether the TPM chip is allowed, not allowed, or required.
	- **TPM startup PIN** - Configure whether using a startup PIN with the TPM chip is allowed, not allowed, or required.
	- **TPM startup key** - Configure whether using a startup key with the TPM chip is allowed, not allowed, or required.
	- **TPM startup key and PIN** - Configure whether using a startup key and PIN with the TPM chip is allowed, not allowed, or required.
- **Minimum PIN Length** - Enable this setting to configure a minimum length for the TPM startup PIN.
	- **Minimum characters** - Enter the number of characters required for the startup PIN from **4**-**20**.
- **Enable OS drive recovery** - Enable this setting to control how BitLocker-protected operating system drives are recovered when the required start-up information is not available.
	- **Certificate-based data recovery agent** - Enable this setting if you want data recovery agents to be able to be used with BitLocker-protected operating system drives.
	- **User creation of recovery password** - Configure whether users are allowed, required, or not allowed to generate a 48-digit recovery password.
	- **User creation of recovery key** - Configure whether users are allowed, required, or not allowed to generate a 256-bit recovery key.
	- **Hide recovery options in the BitLocker setup wizard** - Enable this setting to prevent users from seeing, or changing recovery options when they turn on BitLocker.
	- **Save BitLocker recovery information to AD DS** - Enables the storage of BitLocker recovery information in Active Directory.
	- **Configure storage of BitLocker recovery Information to AD DS** - Configure what parts of BitLocker recovery information are stored in Active Directory. Choose from:
		- **Backup recovery passwords and key packages**
		- **Backup recovery passwords only**
	- **Require recovery information to be stored in AD DS before enabling BitLocker** - Enable this setting to stop users from turning on BitLocker unless the device is domain-joined, and BitLocker recovery information is successfully stored in Active Directory.
- **Enable pre-boot recovery message and URL** - Enable this setting to configure the message and URL that are displayed on the pre-boot key recovery screen.
	- **Pre-boot recovery message** - Configure how the pre-boot recovery message displays to users. Choose from:
		- **Use default recovery message and URL**
		- **Use empty recovery message and URL**
		- **Use custom recovery message**
		- **Use custom recovery URL**


### BitLocker fixed data-drive settings

- **Deny write access to fixed data-drive not protected by BitLocker** - If enabled, BitLocker protection must be enabled on all fixed, or built-in data drives to be able to write to them.
- **Enable fixed drive recovery** - Enable this setting to control how BitLocker-protected fixed drives are recovered when the required start-up information is not available.
	- **Data recovery agent** - Enable this setting if you want data recovery agents to be used with BitLocker-protected fixed drives.
	- **User creation of recovery password** - Configure whether users are allowed, required, or not allowed to generate a 48-digit recovery password.  
	- **User creation of recovery key** - Configure whether users are allowed, required, or not allowed to generate a 256-bit recovery key.
	- **Hide recovery options in the BitLocker setup wizard** - Enable this setting to prevent users from seeing, or changing recovery options when they turn on BitLocker.
	- **Save BitLocker recovery information to AD DS** - Enables the storage of BitLocker recovery information in Active Directory.
	- **Configure storage of BitLocker recovery Information to AD DS** - Configure what parts of BitLocker recovery information are stored in Active Directory. Choose from:
		- **Backup recovery passwords and key packages**
		- **Backup recovery passwords only**
	- **Require recovery information to be stored in AD DS before enabling BitLocker** - Enable this setting to stop users from turning on BitLocker unless the device is domain-joined, and BitLocker recovery information has been successfully stored in Active Directory.


### BitLocker removable data-drive settings

- **Deny write access to removable data-drive not protected by BitLocker** - Specify whether BitLocker encryption is required for removable storage drives.
	- **Block write access to devices configured in another organization** - Specify whether removable data drives that belong to another organization can be written to.



## Next steps

If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).
