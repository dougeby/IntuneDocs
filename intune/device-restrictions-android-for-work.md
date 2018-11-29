---
# required metadata

title: Device restrictions for Android work profiles in Microsoft Intune - Azure | Microsoft Docs
description: On Android Enterprise profile devices, you can restrict some settings on the device, including copy and paste, show notifications, app permissions, data sharing, password length, sign-in failures, using fingerprint to unlock, reuse passwords, and enable bluetooth sharing of work contacts. 
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/2/2018
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

# Work device restriction settings in Intune

This article lists the Microsoft Intune device restrictions settings that you can configure for Android Enterprise profile devices.

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## Work profile settings

### General Settings

- **Copy and paste between work and personal profiles**: Controls copy and paste behavior between work and personal apps. Select **Block** to enabling blocking. Select **Not configured** to disable blocking.
- **Data sharing between work and personal profiles**: Control whether apps in the work profile can share with apps in the personal profile. If this setting is enabled, the user can press the **Share** action to be shown Work Profile applications in the available apps that the user can share into from the personal profile. This setting doesn't apply to copy or paste clipboard behavior. Unlike [app protection policy settings](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), device restriction settings are managed from the Intune portal and use the Android work profile partition to isolate managed apps. Select from the following setting options:
  - **Default sharing restrictions**: The default sharing behavior of the device, which varies depending on the Android version. By default, sharing from the personal profile to the work profile is allowed. Also by default, sharing from the work profile to the personal profile is blocked. This setting prevents sharing of data from the work to the personal profile. On devices running versions 6.0 and later, Google doesn't block sharing from the personal profile to the work profile.
  - **Apps in work profile can handle sharing request from personal profile**: Enables the built-in Android feature that allows sharing from the personal to work profile. When enabled, a sharing request from an app in the personal profile can share with apps in the work profile. This setting is the default behavior for Android devices running versions earlier than 6.0.
  - **Allow sharing across boundaries**: Enables sharing across the work profile boundary in both directions. When you select this setting, apps in the work profile can share data with unbadged apps in the personal profile. This setting allows managed apps in the work profile to share with apps on the unmanaged side of the device. So, use this setting carefully.

- **Work profile notifications while device locked**: Controls whether apps in the work profile can display data in notifications when the device is locked.
- **Default app permissions**: Sets the default permission policy for all apps in the work profile. Starting with Android 6, the user is prompted to grant certain permissions required by apps when the app is launched. This policy setting lets you decide if users are prompted to grant permissions for all apps in the work profile. For example, you assign an app to the work profile that requires location access. Normally that app prompts the user to approve or deny location access to the app. Use this policy to automatically grant permissions without a prompt, automatically deny permissions without a prompt, or let the end user decide. Select from the following options:
  - **Device default**
  - **Prompt**
  - **Auto grant**
  - **Auto deny**

	You can also use an App Configuration policy to grant permissions for individual apps (**Client Apps** > **App configuration policies**).

- **Add and remove accounts**

   Prevents end users from manually adding or removing accounts in the work profile.

   For example, when you deploy the Gmail app into an Android work profile, you can prevent end users from adding or removing accounts in this work profile.

- **Contact sharing via Bluetooth**: Enables access to work contacts from another device, such as a car, that is paired using Bluetooth. By default, this setting isn't configured, and work profile contacts aren't shown. Select **Enable** to allow this sharing, and show work profile contacts. This setting applies to Android work profile devices on Android OS v6.0 and newer. Enabling this setting may allow certain Bluetooth devices to cache work contacts upon first connection. Disabling this policy after an initial pairing/sync may not remove work contacts from a Bluetooth device.

- **Screen capture**: Blocks the screen capture on the device in the work profile. It also prevents the content from being shown on display devices that don't have a secure video output.

- **Display work contact caller-id in personal profile**: When enabled (Not configured), the work contact caller details are displayed in the personal profile. When blocked, the work contact caller number isn't displayed in the personal profile. Applies to Android OS v6.0 and newer versions.

- **Camera**: Blocks the camera on the device in the work profile. The camera on the personal side is not affected by the setting.

### Work profile password

- **Require Work Profile Password**: Applies to Android 7.0 and above with work profile enabled. Define a passcode policy that applies only to the apps in the work profile. By default, the end user can use the two separately defined PINs, or users can choose to combine the PINs into the stronger of the two PINs.
- **Minimum password length**: Enter the minimum number of characters the user's password must have, from **4**-**16**.
- **Maximum minutes of inactivity until work profile locks**: Select the amount of time before the work profile locks. The user must then enter their credentials to regain access.
- **Number of sign-in failures before wiping device**: Enter the number of times an incorrect password can be entered before the work profile is wiped from the device.
- **Password expiration (days)**: Enter the number of days until an end user's password must be changed (from **1**-**255**).
- **Required password type**: Select the type of password that must be set on the device. Choose from:
  - **Device default**
  - **Low security biometric**
  - **Required**
  - **At least numeric**
  - **Numeric complex**: Repeating, or consecutive numbers like '1111' or '1234' aren't allowed
  - **At least alphabetic**
  - **At least alphanumeric**
  - **At least alphanumeric with symbols**
- **Prevent reuse of previous passwords**: Enter the number of new passwords that must be used before an old password can be reused (from **1**-**24**).
- **Fingerprint unlock**: Blocks end users from using the device fingerprint scanner to unlock the device
- **Smart Lock and other trust agents**: Control the Smart Lock feature on compatible devices. This phone feature, also known as a trust agent, lets you disable or bypass the work profile password if the device is in a trusted location. For example, bypass the work profile password when the device is connected to a specific Bluetooth device, or when it's close to an NFC tag. Use this setting to prevent users from configuring Smart Lock.

## Device password

- **Minimum password length**: Enter the minimum number of characters the user's password must have, from **4**-**14**.
- **Maximum minutes of inactivity until screen locks**: Select the amount of time before an inactive device automatically locks
- **Number of sign-in failures before wiping device**: Enter the number of times an incorrect password can be entered before all data is wiped from the device
- **Password expiration (days)**: Enter the number of days until an end user's password must be changed (from **1**-**255**)
- **Required password type**: Select the type of password that must be set on the device. Choose from:
  - **Device default**
  - **Low security biometric**
  - **Required**
  - **At least numeric**
  - **Numeric complex**: Repeating, or consecutive numbers like '1111' or '1234' are not allowed
  - **At least alphabetic**
  - **At least alphanumeric**
  - **At least alphanumeric with symbols**
- **Prevent reuse of previous passwords**: Enter the number of new passwords that must be used before an old password can be reused (from **1**-**24**).
- **Fingerprint unlock**: Blocks an end user from using the device fingerprint scanner to unlock the device
- **Smart Lock and other trust agents**: Control the Smart Lock feature on compatible devices. This phone feature, also known as a trust agent, lets you disable or bypass the device lock screen password if the device is in a trusted location. For example, bypass the work profile password when the device is connected to a specific Bluetooth device, or when it's close to an NFC tag. Use this setting to prevent users from configuring Smart Lock.

## System security

- **Threat scan on apps**: Enforce the **Verify Apps** setting is on for work and personal profiles.

   > [!Note]
   > This setting only works for devices that are Android O and above.

## Connectivity

- **Always-on VPN**: Choose **Enable** to set a VPN client to automatically connect and reconnect to the VPN. Always-on VPN connections stay connected or immediately connect when the user locks their device, the device restarts, or the wireless network changes. 

  Choose **Not configured** to disable always-on VPN for all VPN clients. 

  > [!IMPORTANT]
  > Be sure to deploy only one Always On VPN policy to a single device. Deploying multiple Always VPN policies to a single device isn't supported.

- **VPN client**: Choose a VPN client that supports Always On. Your options:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Custom
    - **Package ID**: Enter the package ID of the app in the Google Play store. For example, if the URL for the app in the Play store is `https://play.google.com/store/details?id=com.contosovpn.android.prod`, then the package ID is `com.contosovpn.android.prod`.

    > [!IMPORTANT]
    >  - The VPN client you choose must be installed on the device, and it must support per-app VPN in work profiles. Otherwise, an error occurs. 
    >  - You do need to approve the VPN client app in the **Managed Google Play Store**, sync the app to Intune, and deploy the app to the device. After you do this, then the app is installed in the user's work profile.
    >  - There are known issues when using per-app VPN with F5 Access for Android 3.0.3. See [F5's release notes for F5 Access for Android 3.0.3](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-3.html#relnotes_known_issues_f5_access_android) for more information.

- **Lockdown mode**: **Enable** to force all network traffic to use the VPN tunnel. If a connection to the VPN isn't established, then the device won't have network access.

  Choose **Not configured** to allow traffic to flow through the VPN tunnel or through the mobile network.

## Next step

[Assign profiles](device-profile-assign.md) to users and devices.
