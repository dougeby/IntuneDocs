---
# required metadata

title: Add custom settings to macOS devices in Microsoft Intune - Azure | Microsoft Docs
titleSuffix:
description: Export macOS settings from Apple Configurator or Apple Profile Manager tools, and then import these settings into Microsoft Intune. These settings can create, use, and control custom settings and features on macOS devices. This custom profile can then be assigned or distributed to macOS devices in your organization to create a baseline or standard.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
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

# Use custom settings for macOS devices in Microsoft Intune

Using Microsoft Intune, you can add or create custom settings for your macOS devices using a "custom profile". Custom profiles are a feature in Intune. They are designed to add device settings and features that aren't built in to Intune.

When using macOS devices, there are two ways to get custom settings into Intune:

- [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12)
- [Apple Profile Manager](https://support.apple.com/profile-manager)

You can use these tools to export settings to a configuration profile. In Intune, you import this file, and then assign the profile to your macOS users and devices. Once assigned, the settings are distributed, and also create a baseline or standard for macOS in your organization.

This article shows you how to create a custom profile for macOS devices. It also provides some guidance on using Apple Configurator and Apple Profile Manager.

## Before you begin

- When using **Apple Configurator** to create the configuration profile, be sure the settings you export are compatible with the macOS version on the devices you're using. For information on resolving incompatible settings, search for **Configuration Profile Reference** and **Mobile Device Management Protocol Reference** on the [Apple Developer](https://developer.apple.com/) website.

- When using **Apple Profile Manager**, be sure to:

  - Enable [mobile device management](https://help.apple.com/serverapp/mac/5.7/#/apd05B9B761-D390-4A75-9251-E9AD29A61D0C) in Profile Manager.
  - Add [macOS devices](https://help.apple.com/profilemanager/mac/5.7/#/pm9onzap1984) in Profile Manager.
  - After you add a device in Profile Manager, go to **Under the Library** > **Devices** > select your device > **Settings**. Enter the general, security, privacy, directory, and certificate settings for the device.

    Download and save this file. You'll enter this file in the Intune profile. 

  - Be sure the settings you export from the Apple Profile Manager are compatible with the macOS version on the devices you're using. For information on resolving incompatible settings, search for **Configuration Profile Reference** and **Mobile Device Management Protocol Reference** on the [Apple Developer](https://developer.apple.com/) website.

## Create the profile

1. Sign in to [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Select **Device configuration** > **Profiles** > **Create profile**.
3. Enter the following settings:

    - **Name**: Enter a name for the profile, such as `macos custom profile`.
    - **Description**: Enter a description for the profile.
    - **Platform**: Choose **macOS**.
    - **Profile type**: Choose **Custom**.

4. In **Custom configuration**, enter the following settings:

    - **Custom configuration profile name**: Enter a name for the policy. This name is shown on the device, and in the Intune status.
    - **Configuration profile file**: Browse to the configuration profile you created using the Apple Configurator or Apple Profile Manager. The file you imported is shown in the **File contents** area.

5. Select **OK** > **Create** to create the Intune profile. When complete, your profile is shown in the **Device configuration - Profiles** list.

## Next steps

The profile is created, but it's not doing anything yet. Next, [assign the profile](device-profile-assign.md).

See how to [create the profile on iOS devices](custom-settings-ios.md).
