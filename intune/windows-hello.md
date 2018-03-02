---
# required metadata
title: How to use Windows Hello for Business
titleSuffix: "Azure portal"
description: Learn how to create a policy for controlling use of Windows Hello for Business on managed devices."
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
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

# Use Windows Hello for Business


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune integrates with Windows Hello for Business (formerly Microsoft Passport for Work), an alternative sign-in method that uses Active Directory or an Azure Active Directory account to replace a password, smart card, or a virtual smart card.

Hello for Business lets you use a *user gesture* to sign in, instead of a password. A user gesture might be a simple PIN, biometric authentication such as Windows Hello, or an external device such as a fingerprint reader.

Intune integrates with Hello for Business in two ways:

-   You can use an Intune policy to control which gestures users can and cannot use to sign in.

<!--- -   You can store authentication certificates in the Windows Hello for Business key storage provider (KSP). For more information, see [Secure resource access with certificate profiles in Microsoft Intune](secure-resource-access-with-certificate-profiles.md). --->

> [!IMPORTANT]
> In Windows 10 desktop and mobile versions prior to the Anniversary Update, you could set two different PINS that could be used to authenticate to resources:
- The **device PIN** could be used to unlock the device and connect to cloud resources.
- The **work PIN** was used to access Azure AD resources on user’s personal devices (BYOD).

>In the Anniversary Update, these two PINS were merged into one single device PIN.
Any Intune configuration policies you set to control the device PIN, and additionally, any Windows Hello for Business policies you configured, now both set this new PIN value.
If you have set both policy types to control the PIN, the Windows Hello for Business policy is applied on both Windows 10 desktop and mobile devices.
To ensure policy conflicts are resolved and that the PIN policy is applied correctly, update your Windows Hello for Business Policy to match the settings in your configuration policy, and ask your users to sync their devices in the Company Portal app.



## Create a Windows Hello for Business policy

1.  In the the [Azure portal](https://portal.azure.com), choose **All Services** > **Monitoring + Management** > **Intune**.

2.  On the Intune pane, choose **Device enrollment**, and then choose **Windows enrollment** > **Windows Hello for Business**.

3.  On the pane that opens, choose the **Default** settings.

4.  On the **All Users** pane, click **Properties** and then enter a **Name** and optional **Description** for the Windows Hello for Business settings.

5. On the **All Users** pane, click **Settings** and then choose from the following for **Configure Windows Hello for Business**:

	- **Disabled**. If you don't want to use Windows Hello for Business, select this setting. All other settings on the screen are then unavailable.
	- **Enabled**. Select this setting if you want to configure Windows Hello for Business settings.
	- **Not configured**. Select this setting if you don't want to use Intune to control Windows Hello for Business settings. Any existing Windows Hello for Business settings on Windows 10 devices is not changed. All other settings on the pane are unavailable.

6.  If you selected **Enabled** in the previous step, configure the required settings that are applied to all enrolled Windows 10 and Windows 10 Mobile devices.

 - **Use a Trusted Platform Module (TPM)**. A TPM chip provides an additional layer of data security.<br>Choose one of the following values:

	 - **Required** (default). Only devices with an accessible TPM can provision Windows Hello for Business.
	 - **Preferred**. Devices first attempt to use a TPM. If this is not available, they can use software encryption.

 - **Minimum PIN length**/**Maximum PIN length**. Configures devices to use the minimum and maximum PIN lengths that you specify to help ensure secure sign-in. The default PIN length is six characters, but you can enforce a minimum length of four characters. The maximum PIN length is 127 characters.

 - **Lowercase letters in PIN**/**Uppercase letters in PIN**/**Special characters in PIN**. You can enforce a stronger PIN by requiring the use of uppercase letters, lowercase letters, and special characters in the PIN. Choose from:

	 - **Allowed**. Users can use the character type in their PIN, but it is not mandatory.

	 - **Required**. Users must include at least one of the character types in their PIN. For example, it's common practice to require at least one uppercase letter and one special character.

	 - **Not allowed** (default). Users must not use these character types in their PIN. (This is also the behavior if the setting is not configured.)<br>Special characters include: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**

 - **PIN expiration (days)**. It's a good practice to specify an expiration period for a PIN, after which users must change it. The default is 41 days.

 - **Remember PIN history**. Restricts the reuse of previously used PINs. By default, the last 5 PINs cannot be reused.

 - **Allow biometric authentication**. Enables biometric authentication, such as facial recognition or fingerprint, as an alternative to a PIN for Windows Hello for Business. Users must still configure a work PIN in case biometric authentication fails. Choose from:

	 - **Yes**. Windows Hello for Business allows biometric authentication.
	 - **No**. Windows Hello for Business prevents biometric authentication (for all account types).

 - **Use enhanced anti-spoofing, when available**. Configures whether the anti-spoofing features of Windows Hello are used on devices that support it (for example, detecting a photograph of a face instead of a real face).<br>If this is set to **Yes**, Windows requires all users to use anti-spoofing for facial features when that is supported.

 - **Allow phone sign-in**. If this option is set to **Yes**, users can use a remote passport to serve as a portable companion device for desktop computer authentication. The desktop computer must be Azure Active Directory joined, and the companion device must be configured with a Windows Hello for Business PIN.

## Windows Holographic for Business support

Windows Holographic for Business supports the following Windows Hello for Business settings:

- Use a Trusted Platform Module (TPM)
- Minimum PIN length
- Maximum PIN length
- Lowercase letters in PIN
- Uppercase letters in PIN
- Special characters in PIN
- PIN expiration (days)
- Remember PIN history

## Further information
For more information about Microsoft Passport, see [the guide](https://technet.microsoft.com/library/mt589441.aspx) in the Windows 10 documentation.
