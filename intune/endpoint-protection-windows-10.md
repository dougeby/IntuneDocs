---
# required metadata

title: Intune endpoint protection settings for Windows 10
titlesuffix: "Azure portal"
description: Learn the Intune settings you can use to control endpoint protection settings like BitLocker on Windows 10 devices."
keywords:
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 01/04/2017
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

The endpoint protection profile let you control security features on Windows 10 devices, like BitLocker and Windows Defender.

Use the information in this topic to learn how to create endpoint protection profiles.

> [!Note]
> These settings are not supported on the Home and Professional editions of Windows 10.

## Create an endpoint protection profile

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device configuration**.
2. On the **Device Configuration** blade, choose **Manage** > **Profiles**.
3. On the profiles blade, choose **Create profile**.
4. On the **Create profile** blade, enter a **Name** and **Description** for the device features profile.
5. From the **Platform** drop-down list, select **Windows 10 and later**.
6. From the **Profile type** drop-down list, choose **Endpoint protection**.
7. Configure the settings you want. Use the details in this topic to help you understand what each setting does. When you are finished, choose **OK**.
8. Go back to the **Create profile** blade, and choose **Create**.

The profile is created and appears on the profiles list blade.

## Windows Defender Application Guard

Application Guard is only available for Windows 10 (64-bit) devices. Using this profile will install a Win32 component to activate Application Guard.

- **Application Guard** - Open unapproved sites in a Hyper-V virtualized browsing container.
- **Clipboard behavior** - Choose what copy/paste actions are allowed between the local PC and the Application Guard virtual browser.
- **External content on enterprise sites** - Block content from unapproved websites from loading.
- **Print from virtual browser** - Allow PDF, XPS, local, and/or network printers to print content from the virtual browser.
- **Collect logs** - Collect logs for events that occur within an Application Guard browsing session.
- **Retain user-generated browser data** - Allow user data (such as passwords, favorites, and cookies) that is created during an Application Guard virtual browsing session to be saved.


## Windows Defender Firewall

### Global settings

These settings are applicable to all network types.

- **File Transfer Protocol** - Block stateful FTP.
- **Security association idle time before deletion** - Security associations are deleted after no network traffic is detected for *n* seconds.
- **Pre-shared key encoding** - Encode preshared keys using UTF-8.
- **IPsec exemptions** - Configure specific traffic to be exempt from IPsec, including **Neighbor discover IPv6 ICMP type-codes**, **ICMP**, **Router discover IPv6 ICMP type-codes**, and **Both IPv4 and IPv6 DHCP network traffic**.
- **Certificate revocation list verification** - Set a value for how certificate revocation list verification is enforced, including **Disable CRL verification**, **Fail CRL verification on revoked certificate only**, and **Fail CRL verification on any error encountered**.
- **Opportunistically match authentication set per keying module** - Set keying modules to ignore the entire authentication set if they do not support all authentication suites in that set.
- **Packet queuing** - Specify how scaling for software on the receive side is enabled for the encrypted receive and clear text forward for the IPsec tunnel gateway scenario. This ensures that packet order is preserved.

### Network settings

These settings are applicable to specific network types, including **Domain (workplace) network**, **Private (discoverable) network**, and **Public (non-discoverable) network**.

#### General settings

- **Windows Defender Firewall** - Enable this setting to block network traffic.
- **Stealth mode** - Block Firewall from operating in stealth mode. Blocking this allows you to also block **IPsec secured packet exemption**.
- **Shielded** - Enabling this and the firewall setting will block all incoming traffic.
- **Unicast responses to multicast broadcasts** - Block unicast responses to multicast broadcasts. Typically, you would not want to receive unicast responses to multicast or broadcast messages, since such responses can indicate a denial of service attack or an attacker attempting to probe a known live computer.
- **Inbound notifications** - Block notifications from displaying to users when an application is blocked from listening on a port.
- **Default action for inbound connections** - Block the default action that firewall performs on inbound connections.

#### Rule merging

- **Authorized application Windows Defender Firewall rules from the local store** - Apply authorized firewall rules in the local store to be recognized and enforced.
- **Global port Windows Defender Firewall rules from the local store** - Apply global port firewall rules in the local store to be recognized and enforced.
- **Windows Defender Firewall rules from the local store** - Apply global firewall rules in the local store to be recognized and enforced.
- **IPsec rules from the local store** - Apply connection security rules from the local store, regardless of schema or connection security rule versions.

## Windows Defender SmartScreen settings

- **SmartScreen for apps and files** - Enable Windows SmartScreen for file execution, and running apps.
- **Unverified files execution** - Block the end user from running files that have not been verified by Windows SmartScreen.

## Windows encryption

### Windows settings

These settings apply to all versions of Windows 10.

- **Encrypt devices** - If enabled, users are prompted to enable device encryption. Additionally, they are asked to confirm that encryption from another provider has not been enabled. If Windows encryption is turned on while another encryption method is active, the device might become unstable.
- **Encrypt storage card** - Enable this setting to encrypt any removable storage cards used by the device.


### BitLocker base settings

Base settings are universal BitLocker settings for all types of data drives. BitLocker Group Policy settings manage what drive encryption tasks or configuration options the end user can modify across all types of data drives.

- **Warning for other disk encryption** - Disable the warning prompt for other disk encryption on end users' machines.
- **Configure encryption methods** - Enable this setting to configure encryption algorithms for operating system, data, and removable drives.
	- **Encryption for operating system drives** - Choose the encryption method for operating system drives. We recommend you use the XTS-AES algorithm.
	- **Encryption for fixed data-drives** - Choose the encryption method for fixed (built-in) data drives. We recommend you use the XTS-AES algorithm.
	- **Encryption for removable data-drives** - Choose the encryption method for removable data drives. If the removable drive is used with devices that are not running Windows 10, we recommend you use the AES-CBC algorithm.

### BitLocker OS drive settings

These settings apply specifically to operating system data drives.

- **Additional authentication at startup** - Configure authentication requirements for computer startup, including the use of Trusted Platform Module (TPM).
	- **BitLocker with non-compatible TPM chip**
	- **Compatible TPM startup** - Configure whether the TPM chip is allowed, not allowed, or required.
	- **Compatible TPM startup PIN** - Configure whether using a startup PIN with the TPM chip is allowed, not allowed, or required.
	- **Compatible TPM startup key** - Configure whether using a startup key with the TPM chip is allowed, not allowed, or required.
	- **Compatible TPM startup key and PIN** - Configure whether using a startup key and PIN with the TPM chip is allowed, not allowed, or required.
- **Minimum PIN Length** - Enable this setting to configure a minimum length for the TPM startup PIN.
	- **Minimum characters** - Enter the number of characters required for the startup PIN from **4**-**20**.
- **OS drive recovery** - Enable this setting to control how BitLocker-protected operating system drives are recovered when the required start-up information is not available.
	- **Certificate-based data recovery agent** - Enable this setting if you want data recovery agents to be able to be used with BitLocker-protected operating system drives.
	- **User creation of recovery password** - Configure whether users are allowed, required, or not allowed to generate a 48-digit recovery password.
	- **User creation of recovery key** - Configure whether users are allowed, required, or not allowed to generate a 256-bit recovery key.
	- **Recovery options in the BitLocker setup wizard** - Enable this setting to prevent users from seeing, or changing recovery options when they turn on BitLocker.
	- **Save BitLocker recovery information to AD DS** - Enables the storage of BitLocker recovery information in Active Directory.
	- **BitLocker recovery Information stored to AD DS** - Configure what parts of BitLocker recovery information are stored in Active Directory. Choose from:
		- **Backup recovery passwords and key packages**
		- **Backup recovery passwords only**
	- **Store recovery information in AD DS before enabling BitLocker** - Enable this setting to stop users from turning on BitLocker unless the device is domain-joined, and BitLocker recovery information is successfully stored in Active Directory.
- **Pre-boot recovery message and URL** - Enable this setting to configure the message and URL that are displayed on the pre-boot key recovery screen.
	- **Pre-boot recovery message** - Configure how the pre-boot recovery message displays to users. Choose from:
		- **Use default recovery message and URL**
		- **Use empty recovery message and URL**
		- **Use custom recovery message**
		- **Use custom recovery URL**


### BitLocker fixed data-drive settings

- **Write access to fixed data-drive not protected by BitLocker** - If enabled, BitLocker protection must be enabled on all fixed, or built-in data drives to be able to write to them.
- **Fixed drive recovery** - Enable this setting to control how BitLocker-protected fixed drives are recovered when the required start-up information is not available.
	- **Data recovery agent** - Enable this setting if you want data recovery agents to be used with BitLocker-protected fixed drives.
	- **User creation of recovery password** - Configure whether users are allowed, required, or not allowed to generate a 48-digit recovery password.  
	- **User creation of recovery key** - Configure whether users are allowed, required, or not allowed to generate a 256-bit recovery key.
	- **Recovery options in the BitLocker setup wizard** - Enable this setting to prevent users from seeing, or changing recovery options when they turn on BitLocker.
	- **Save BitLocker recovery information to AD DS** - Enables the storage of BitLocker recovery information in Active Directory.
	- **BitLocker recovery Information to AD DS** - Configure what parts of BitLocker recovery information are stored in Active Directory. Choose from:
		- **Backup recovery passwords and key packages**
		- **Backup recovery passwords only**
	- **Store recovery information in AD DS before enabling BitLocker** - Enable this setting to stop users from turning on BitLocker unless the device is domain-joined, and BitLocker recovery information has been successfully stored in Active Directory.

### BitLocker removable data-drive settings

- **Write access to removable data-drive not protected by BitLocker** - Specify whether BitLocker encryption is required for removable storage drives.
  - **Write access to devices configured in another organization** - Specify whether removable data drives that belong to another organization can be written to.

## Windows Defender Exploit Guard https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionMenu/deviceConfiguration/menuContent/configuration

### Attack Surface Reduction

### Controlled folder access

### Network filtering

### Exploit protection

## Windows Defender Application Control

## Windows Defender Security Center



### Network isolation policies (find a place for these somewhere in the docs if not here)





### Windows Defender Device Guard


### Windows Hello for Business

[Windows Hello for Business](windows-hello.md) lets you use a *user gesture* to sign in, instead of a password.



### Windows Defender Security Center




## Windows Defender Advance Threat Protection

Brief explanation of WDATP

### Onboarding and offboarding



### Configuring settings


## Next steps

If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).
