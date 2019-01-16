---
# required metadata

title: Create iOS or macOS device profile with Microsoft Intune - Azure | Microsoft Docs
description: Add or create an iOS or macOS device profile, and then configure settings for AirPrint, layout of the home screen, app notifications, shared device, single sign-in, and web content filter settings in Microsoft Intune.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/05/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
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

---

# Add iOS or macOS device feature settings in Intune

Intune includes many features and settings that help administrators control iOS and macOS devices. For example, administrators can:

- Allow users access to AirPrint printers in your network
- Add apps and folders to the home screen, including adding new pages
- Choose if and how app notifications are shown
- Configure the lock screen to show a message or the asset tag, especially for shared devices
- Give users a secure single sign-on experience to share credentials between apps
- Filter web sites that use adult language and allow or block specific web sites

<<<<<<< HEAD
These features are available in Intune, and are configurable by the administrator. Intune uses "configuration profiles" to create and customize these settings for your organization's needs. After you add these features in a profile, you can then push or deploy the profile to iOS and macOS devices in your organization.
=======
- AirPrint and AirPlay settings
- Home screen layout
- Notifications from apps
- Lock Screen Message
- Setting up single sign-on
- Filtering web content
>>>>>>> 07c6c9ab46c807fcb088a2b02aae898aa7e79ab6

This article shows you how to create a device configuration profile. You can also see all the available settings for [iOS](ios-device-features-settings.md) and [macOS](macos-device-features-settings.md) devices.

## Create a device profile

1. In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune** > select **Intune**.
2. Select **Device configuration** > **Profiles** > **Create profile**.
3. Enter the following properties:

   - **Name**: Enter a descriptive name for the new profile.
<<<<<<< HEAD
   - **Description**: Enter a description for the profile. This setting is optional, but recommended.
   - **Platform**: Select your platform:
=======
   - **Description**: Enter a description for the profile. (This setting is optional, but recommended.)
   - **Platform**: Select your platform type:
>>>>>>> 07c6c9ab46c807fcb088a2b02aae898aa7e79ab6
     - **iOS**
     - **macOS**
   - **Profile type**: Select **Device features**.
   - **Settings**: The settings depend on the platform you choose. For a list of all settings, and what they do, see [iOS](ios-device-features-settings.md) and [macOS](macos-device-features-settings.md) device feature settings.

<<<<<<< HEAD
4. When you're done, select **OK**, and choose **Create** to save your changes.
=======
     - [AirPrint settings for iOS and MacOS](air-print-settings-ios-macos.md)
     - [AirPlay settings for iOS](airplay-settings-ios.md)
     - [Home screen layout settings for iOS](home-screen-settings-ios.md)
     - [App notification settings for iOS](app-notification-settings-ios.md)
     - [Lock Screen Message settings for iOS](shared-device-settings-ios.md)
     - [Configure Intune for iOS device single sign-on](sso-ios.md)
     - [Web content filter settings for iOS](web-content-filter-settings-ios.md)
>>>>>>> 07c6c9ab46c807fcb088a2b02aae898aa7e79ab6

## Next steps

- View all the settings for [iOS](ios-device-features-settings.md) and [macOS](macos-device-features-settings.md) devices.
- Assign this profile to groups; see [assign device profiles](device-profile-assign.md).