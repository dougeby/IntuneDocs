---
# required metadata

title: Configure identity protection settings in Microsoft Intune - Azure | Microsoft Docs
description: Add a device profile to set Windows Hello for Business settings on Windows 10 devices in Microsoft Intune
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/29/2018
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

---

# Configure identity protection settings in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Identity protection profiles control how Windows Hello for Business is provisioned and configured on managed Windows 10 devices. Create this profile to configure:  
* Windows Hello for Business availability for devices and users.
* Device pin requirements.
* Gestures users can and can't use to sign in to their devices.  

 You can assign this profile to select user and device groups, or to all users and to all devices. Groups receive the identity protection profile when they check-in to Intune.    

Use the information in this article to create an identity protection profile. Then [assign your profile](device-profile-assign.md) to user and device groups.

This feature applies to device running:  
- Windows 10 and later
- Windows Holographic for Business  

## Create a device profile with identity protection settings

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services**, filter on **Intune**, and select **Microsoft Intune**.
3. Select **Device configuration** > **Profiles** > **Create profile**.
4. Enter a **Name** and **Description** for the identity protection profile.
5. From the **Platform** drop-down list, select **Windows 10 and later**. Windows Hello for Business is only supported on devices running Windows 10 and later.
6. From the **Profile type** drop-down list, choose **Identity protection**.
7. On the Windows Hello for Business pane, choose from the following options for Configure Windows Hello for Business:
    * Disabled. If you don't want to use Windows Hello for Business, select this setting. All other settings on the screen are then unavailable.
    * Enabled. Select this setting if you want to configure Windows Hello for Business settings.  

8. If you selected **Enabled** in the previous step, configure the required settings that are applied to targeted enrolled Windows 10 and Windows 10 Mobile devices and users.

> [!NOTE]
> When assigning identity protection profiles to users only, the device context defaults to **Not configured**.  

   - **Minimum PIN length**/**Maximum PIN length**. Configures devices to use the minimum and maximum PIN lengths that you specify to help ensure secure sign-in. The default PIN length is six characters, but you can enforce a minimum length of four characters. The maximum PIN length is 127 characters.  

   - **Lowercase letters in PIN**/**Uppercase letters in PIN**/**Special characters in PIN**. You can enforce a stronger PIN by requiring the use of uppercase letters, lowercase letters, and special characters in the PIN. Choose from:

	 - **Allowed**. Users can use the character type in their PIN, but it is not mandatory.

	 - **Required**. Users must include at least one of the character types in their PIN. For example, it's common practice to require at least one uppercase letter and one special character.

	 - **Not allowed** (default). Users must not use these character types in their PIN. (This behavior also occurs if the setting isn't configured.)<br>Special characters include: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**

   - **PIN expiration (days)**. It's a good practice to specify an expiration period for a PIN, after which users must change it. The default is 41 days.

   - **Remember PIN history**. Restricts the reuse of previously used PINs. By default, the last 5 PINs cannot be reused.  
   - **Enable PIN recovery**: Allows the user to change their PIN by using the Windows Hello for Business PIN recovery service. 
       - **Enable**. The cloud service encrypts a PIN recovery secret to store on the device. The user can change their PIN if needed.  
       - **Not configured** (default). A PIN recovery secret is not created or stored. If the user's PIN is forgotten, the only way to get a new PIN is by deleting the existing PIN and creating a new one. The user will need to re-register with any services the old PIN provided access to.  
   
   - **Use a Trusted Platform Module (TPM)**. A TPM chip provides an additional layer of data security. Choose one of the following values:  
	 - **Enable**. Only devices with an accessible TPM can provision Windows Hello for Business.
	 - **Not configured**. All devices can provision Windows Hello for Business, even when there's no usable TPM. Devices will first try to use a TPM, but if one is unavailable, devices can use software encryption.  

   - **Allow biometric authentication**. Enables biometric authentication, such as facial recognition or fingerprint, as an alternative to a PIN for Windows Hello for Business. Users must still configure a work PIN in case biometric authentication fails. Choose from:

	 - **Enable**. Windows Hello for Business allows biometric authentication.
	 - **Not configured** (default). Windows Hello for Business prevents biometric authentication (for all account types).

   - **Use enhanced anti-spoofing, when available**. Configures whether the anti-spoofing features of Windows Hello are used on devices that support it (for example, detecting a photograph of a face instead of a real face).
       - **Enable**. Windows requires all users to use anti-spoofing for facial features when that is supported.  
       - **Not configured** (default). Windows honors the anti-spoofing configurations on the device.

   - **Certificate for on-premise resources**. 
       - **Enable**. Allows Windows Hello for Business to use certificates to authenticate to resources on-premises.
       - **Not configured** (default). Prevents Windows Hello for Business from using certificates to authenticate to resources on-premises.  
9. Click **OK** to save your profile.  

The profile is created and appears in the **Device configuration - Profiles** list. To go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).  

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
