---
# required metadata

title: Create iOS or macOS device profile with Microsoft Intune - Azure | Microsoft Docs
description: Add or create an iOS or macOS device profile, and then configure settings for AirPrint, layout of the home screen, app notifications, shared device, single sign-in, and web content filter settings in Microsoft Intune.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Add iOS or macOS device feature settings in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune includes many features and settings that help administrators control iOS and macOS devices. For example, administrators can:

- Allow users access to AirPrint printers in your network
- Add apps and folders to the home screen, including adding new pages
- Choose if and how app notifications are shown
- Configure the lock screen to show a message or the asset tag, especially for shared devices
- Give users a secure single sign-on experience to share credentials between apps
- Filter web sites that use adult language and allow or block specific web sites

These features are available in Intune, and are configurable by the administrator. Intune uses "configuration profiles" to create and customize these settings for your organization's needs. After you add these features in a profile, you can then push or deploy the profile to iOS and macOS devices in your organization.

This article shows you how to create a device configuration profile. You can also see all the available settings for [iOS](ios-device-features-settings.md) and [macOS](macos-device-features-settings.md) devices.

## Create a device profile

1. Sign in to [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Select **Device configuration** > **Profiles** > **Create profile**.
3. Enter the following properties:

    - **Name**: Enter a descriptive name for the policy. Name your policies so you can easily identify them later. For example, a good policy name is **macOS: Configures login screen**.
    - **Description**: Enter a description for the profile. This setting is optional, but recommended.
    - **Platform**: Choose the platform of your devices. Your options:  
        - **iOS/iPadOS**
        - **macOS**
    - **Profile type**: Select **Device features**.

4. Depending on the platform you chose, the settings you can configure are different. Choose your platform for detailed settings:

    - [iOS/iPadOS](ios-device-features-settings.md)
    - [macOS](macos-device-features-settings.md)

5. When you're done, select **OK** > **Create** to save your changes.

The profile is created and shown in the profiles list. Be sure to [assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).

## Next steps

After the profile is created, it's ready to be assigned. Next, [assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).

View all the device feature settings for [iOS](ios-device-features-settings.md) and [macOS](macos-device-features-settings.md) devices.
