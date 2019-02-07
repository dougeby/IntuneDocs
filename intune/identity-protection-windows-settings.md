---
# required metadata

title: Windows Hello for Business settings in Microsoft Intune - Azure | Microsoft Docs
description: See a list of all the PIN, biometric, and anti-spoofing settings in an identity protection profile to use and configure Windows Hello for Business on Windows 10 devices in Microsoft Intune.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Windows 10 (and newer) device settings to enable Windows Hello for Business in Intune

This article lists and describes the Windows Hello for Business settings you can control on Windows 10 devices in Intune. As part of your mobile device management (MDM) solution, use these settings to use a PIN or fingerprint to sign in, and more.

As an Intune administrator, you can create and assign these settings to Windows 10 and later devices.

To learn more about Windows Hello for Business profiles in Intune, see [configure identity protection](identity-protection-configure.md).

## Before you begin

[Create a configuration profile](identity-protection-configure.md#create-the-device-profile).

## Windows Hello for Business

- **Configure Windows Hello for Business**: To use this feature and configure its settings, choose **Enable**.
- **Minimum PIN length**: Enter the minimum PIN length you want to allow on the devices. The default PIN length is six characters. The minimum PIN length is four (4) characters.
- **Maximum PIN length**: Enter the maximum PIN length you want to allow on the devices. The default PIN length is six (6) characters. The maximum PIN length is 127 characters.  
- **Lowercase letters in PIN**: You can enforce a stronger PIN by requiring end users include lowercase letters. Your options:

  - **Not allowed** (default): Block users from using lowercase letters in the PIN. This behavior also occurs if the setting isn't configured.
  - **Allowed**: Allow users to use lowercase letters in the PIN, but it's not required.
  - **Required**: Users must include at least one lowercase letter in the PIN. For example, it's common practice to require at least one uppercase letter and one special character.

- **Uppercase letters in PIN**: You can enforce a stronger PIN by requiring end users include uppercase letters. Your options:

  - **Not allowed** (default): Block users from using uppercase letters in the PIN. This behavior also occurs if the setting isn't configured.
  - **Allowed**: Allow users to use uppercase letters in the PIN, but it's not required.
  - **Required**: Users must include at least one uppercase letter in the PIN. For example, it's common practice to require at least one uppercase letter and one special character.

- **Special characters in PIN**: You can enforce a stronger PIN by requiring end users include special characters. Your options:

  - **Not allowed** (default): Block users from using special characters in the PIN. This behavior also occurs if the setting isn't configured.
    Special characters include: `! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~`
  - **Allowed**: Allow users to use uppercase letters in the PIN, but it's not required.
  - **Required**: Users must include at least one uppercase letter in the PIN. For example, it's common practice to require at least one uppercase letter and one special character.

- **PIN expiration (days)**: It's a good practice to specify an expiration period for a PIN, after which users must change it. The default is 41 days.

- **Remember PIN history**: Restricts the reuse of previously used PINs. By default, the last 5 PINs can't be reused.  
- **Enable PIN recovery**: Allows the user to change their PIN by using the Windows Hello for Business PIN recovery service.

       - **Enable**: The cloud service encrypts a PIN recovery secret to store on the device. The user can change their PIN if needed.  
       - **Not configured** (default): A PIN recovery secret is not created or stored. If the user's PIN is forgotten, the only way to get a new PIN is by deleting the existing PIN and creating a new one. The user will need to re-register with any services the old PIN provided access to.  

- **Use a Trusted Platform Module (TPM)**: A TPM chip provides an additional layer of data security. Choose one of the following values:  
  - **Enable**: Only devices with an accessible TPM can provision Windows Hello for Business.
  - **Not configured**: All devices can provision Windows Hello for Business, even when there's no usable TPM. Devices will first try to use a TPM, but if one is unavailable, devices can use software encryption.  

- **Allow biometric authentication**: Enables biometric authentication, such as facial recognition or fingerprint, as an alternative to a PIN for Windows Hello for Business. Users must still configure a work PIN in case biometric authentication fails. Choose from:

  - **Enable**: Windows Hello for Business allows biometric authentication.
  - **Not configured** (default): Windows Hello for Business prevents biometric authentication (for all account types).

- **Use enhanced anti-spoofing, when available**: Choose if anti-spoofing features of Windows Hello are used on devices that support it. For example, detect a photograph of a face instead of a real face.

  - **Enable**: Windows requires all users to use anti-spoofing for facial features when that is supported.  
  - **Not configured** (default): Windows honors the anti-spoofing configurations on the device.

- **Certificate for on-premise resources**: 

  - **Enable**: Allows Windows Hello for Business to use certificates to authenticate to resources on-premises.
  - **Not configured** (default): Prevents Windows Hello for Business from using certificates to authenticate to resources on-premises.  

## Next steps

[Assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).
