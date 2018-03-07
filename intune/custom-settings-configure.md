---
# required metadata

title: Use custom device settings in Microsoft Intune - Azure | Microsoft Docs
description: Add or create a profile to use custom settings for Windows, Android, and iOS devices using Microsoft Intune
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
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

# Create a profile with custom settings in Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune may not have all the built-in settings you need or want. Or you may want to use a setting available in other device profiles. To add these settings, create a device profile, and configure the profile with custom device settings.

This article lists the basic steps to create a profile with custom settings. It also includes links to dig deeper into creating custom settings with the different platforms.

## Custom settings on different platforms
Custom settings are configured differently for each platform. For example, to control features on Android and Windows devices, you can enter Open Mobile Alliance Uniform Resource Identifier (OMA-URI) values. For Apple devices, you can import a file you created with the [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

## Create the profile

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services**, filter on **Intune**, and select **Microsoft Intune**.
3. Select **Device configuration**, select **Profiles**, and then choose **Create profile**.
4. Enter a **Name** and **Description** for the custom profile.
5. From the **Platform** drop-down list, select the device platform to apply the custom settings. You can choose any of the following platforms:

    - **Android**
	- **Android for Work**
	- **iOS**
	- **macOS**
	- **Windows Phone 8.1**
	- **Windows 8.1 and later**
	- **Windows 10 and later**

6. From the **Profile** type drop-down list, choose **Custom**.
7. Depending on the platform you choose, the settings you can configure are different. The following links provide more details on the custom settings for each platform:

	- [Android settings](custom-settings-android.md)
	- [iOS settings](custom-settings-ios.md)
	- [macOS settings](custom-settings-macos.md)
	- [Windows Phone 8.1 settings](custom-settings-windows-phone-8-1.md)
	- [Windows 10 settings](custom-settings-windows-10.md)
	- [Windows Holographic for Business settings](custom-settings-windows-holographic.md)
	- [Android for Work settings](custom-settings-android-for-work.md)

8. When you're done, select **Create**.

The profile is created and appears on the profiles list. To assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).
