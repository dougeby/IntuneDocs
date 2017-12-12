---
# required metadata

title: Configure Intune device feature settings
titleSuffix: "Azure portal"
description: Learn how to use Intune to configure features on devices you manage."
keywords:
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/7/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to configure device feature settings in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Device restrictions let you control features on iOS and macOS devices like AirPrint, notifications, and shared device configurations.

Use the information in this topic to learn the basics about configuring device feature profiles, and then read further topics for each platform to learn about device specifics.

## Create a device profile containing device restriction settings

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device configuration**.
2. On the **Device Configuration** blade, choose **Manage** > **Profiles**.
3. On the profiles blade, choose **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the device features profile.
5. From the **Platform** drop-down list, select the device platform to which you want to apply the settings. Currently, you can choose one of the following platforms for device features:
	- **iOS**
	- **macOS**
6. From the **Profile type** drop-down list, choose **Device features**. 
7. Depending on the platform you chose, the settings you can configure will be different. Go to one of the following topics for detailed settings for each platform:
	- [AirPrint settings for iOS and MacOS](air-print-settings-ios-macos.md)
 	- [AirPlay settings for iOS](airplay-settings-ios.md)
	- [Home screen layout settings for iOS](home-screen-settings-ios.md)
	- [App notification settings for iOS](app-notification-settings-ios.md)
	- [Shared device configuration settings for iOS](shared-device-settings-ios.md)
	- [Configure Intune for iOS device Single Sign-on](sso-ios.md)
	- [Web content filter settings for iOS](web-content-filter-settings-ios.md)

8. When you're done, go back to the **Create Profile** blade, and click **Create**.

The profile is created and appears on the profiles list blade.
If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).



