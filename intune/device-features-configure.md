---
# required metadata

title: Create iOS or macOS device profile with Microsoft Intune - Azure | Microsoft Docs
description: Add or create an iOS or macOS device profile, and then configure settings for AirPrint, AirPlay, layout of the home screen, app notifications, shared device, single sign-in, and web content filter settings in Microsoft Intune
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Add iOS or macOS device feature settings in Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Device features let you control a range of settings and features on iOS and macOS devices, such as:

- AirPrint and AirPlay settings
- Home screen layout
- Notifications from apps
- Shared device configuration
- Configure single sign-on
- Filtering web content

This article shows you the basics on configuring iOS device feature profiles. Then, you can step through additional articles to configure platform-specific settings for your devices.

## Create a device profile

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services**, filter on **Intune**, and then select **Microsoft Intune**.
3. Select **Device configuration**, select **Profiles**, and then select **Create profile**.
4. Enter the following properties:

  - **Name**: Enter a descriptive name for the new profile
  - **Description**: (Optional but recommended) Enter a description for the profile
  - **Platform**: Select your platforms type:
    - **iOS**
    - **macOS**
  - **Profile type**: Select **Device features**
  - **Settings**: The settings depend on the platform you choose. The following articles describe the settings for each profile type:

    - [AirPrint settings for iOS and MacOS](air-print-settings-ios-macos.md)
    - [AirPlay settings for iOS](airplay-settings-ios.md)
    - [Home screen layout settings for iOS](home-screen-settings-ios.md)
    - [App notification settings for iOS](app-notification-settings-ios.md)
    - [Shared device configuration settings for iOS](shared-device-settings-ios.md)
    - [Configure Intune for iOS device Single Sign-on](sso-ios.md)
    - [Web content filter settings for iOS](web-content-filter-settings-ios.md)

5. When you're done, select **OK**, and choose **Create** to save your changes.

The profile is created, and appears in the list.

## Next step

To assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).