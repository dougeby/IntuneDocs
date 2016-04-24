---
# required metadata

title: Control Microsoft Passport settings on devices with Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 402bc5a1-ada3-4c4c-a0de-292d026b4444

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Control Microsoft Passport settings on devices with Microsoft Intune
Microsoft Intune lets you integrate with **Microsoft Passport for Work** which is an alternative sign-in method that uses Active Directory, or an Azure Active Directory account to replace a password, smart card, or virtual smart card.

Passport lets you use a **user gesture** to log in, instead of a password. A user gesture might be a simple PIN, biometric authentication such as Windows Hello, or an external device such as a fingerprint reader.

Intune integrates with Passport for Work in two ways:

-   You can use an Intune policy to control which gestures users can and cannot use to login.

-   You can store authentication certificates in the Passport for Work key storage provider (KSP). For more information, see [Secure resource access with certificate profiles in Microsoft Intune](secure-resource-access-with-certificate-profiles.md).

## To create a Passport for Work policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Admin** &gt; **Mobile Device Management** &gt; **Windows** &gt; **Passport for Work** to open the Passport for Work page as shown below.

	![Passport for Work Page](../media/passport.png)

2.  Choose one of the following settings:
	- **Disable Passport for Work on enrolled devices** - If you don't want to use Passport for Work on Windows 10 devices, select this setting. All other settings on the screen are disabled.
	- **Enable Passport for Work on enrolled devices** - Select this setting if you want to configure Passport for Work settings on all Windows 10 devices.
	- **Not configured** - Select this setting if you don't want to use Intune to control Passport for Work settings. Any existing Passport for Work settings on Windows 10 devices will not be changed. All other settings on the screen are disabled.
3.  If you selected **Enable Passport for Work on enrolled devices**, configure the required  settings that will be applied to all enrolled Windows 10 and Windows 10 Mobile devices.
3.  When you are finished, click **Save**.

## Passport for Work: PIN settings

  
- **Require minimum PIN length**/**Require maximum PIN length** - Configures devices to use the minimum and maximum PIN lengths you specify to help ensure secure sign-in. The default PIN length is 6 characters, but you can enforce a minimum length of 4 characters. The maximum PIN length is 127 characters.
- **Require lowercase letters in PIN**/**Require uppercase letters in PIN**/**Require special characters in PIN** - Additionally, you can enforce a stronger PIN by by requiring the use of uppercase, lowercase, and special characters in the PIN. Choose from:
	- **Allowed** - Users can use the character type in their PIN, but it is not mandatory.
	- **Required** - Users must include at least one of the character types in their PIN. For example, it's common practice to require at least one uppercase, and one special character.
	- **Not allowed** (default) - Users must not use these character types in their PIN (this is also the behavior if the setting is not configured).
	> [!TIP]
    > Special characters include: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**.
- **PIN expiration (days)** - It is good practice to specify an expiration period for a PIN after which end users must change it. The default is 41 days. 
- **Remember PIN history** - Use this setting to restrict the re-use of previously used PINS. By default, the last 5 PINS used cannot be reused.


## Passport for Work: Other settings

- **Use a Trusted Platform Module (TPM)** - A Trusted Platform Module (TPM) chip provides an additional layer of data security.<br>Choose one of the following values:
	- **Required** (default) - Only devices with an accessible TPM can provision Passport for Work.
	- **Preferred** - Devices first attempt to use a TPM. If this is not available, they can use software encryption
- **Allow biometric authentication** - Enables biometric authentication such as facial recognition or fingerprint as an alternative to a PIN for Passport for Work. Users must still configure a work PIN in case biometric authentication fails. Choose from:
	- **Yes** - Passport for Work allows biometric authentication.
	- **No** - Passport for Work prevents biometric authentication (for all account types).
- **Use enhanced anti-spoofing, when available** - Configures whether the anti-spoofing features of Windows Hello are used on devices that support it (for example, detecting a photograph of a face instead of a real face).<br>If set to **Yes**, Windows requires all users to use anti-spoofing for facial features when supported.
- **Use Remote Passport** - If this option is set to **Yes**, users can use a remote passport to serve as a portable companion device for desktop computer authentication. The desktop computer must be Azure Active Directory joined, and the companion device must be configured with a Passport for Work PIN.

## Further information
For more information about Microsoft Passport, see [the guide](https://technet.microsoft.com/library/mt589441.aspx) in the Windows 10 documentation.


