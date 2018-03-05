---
# required metadata

title: How to configure Intune custom device settings
titleSuffix: "Azure portal"
description: Learn how to use Intune to configure custom settings on devices you manage."
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 02/22/2018
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

# How to configure custom device settings in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## When to use custom settings

Custom device settings can be useful when Intune doesn't have the settings you want to configure built-in, and available from other device profiles.
Custom settings are configured differently for each platform. For example, with Android and Windows devices, you can specify Open Mobile Alliance Uniform Resource Identifier (OMA-URI) values to control features on devices. For Apple devices, you can import a file you created with the [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

Use the information in this topic to learn the basics about configuring profiles with custom settings, and then read further topics for each platform to learn about device specifics.

## Create a device profile containing custom settings

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** pane, choose **Device configuration**.
2. On the **Device configuration** pane, choose **Manage** > **Profiles**.
3. On the profiles pane, choose **Create profile**.
4. On the **Create profile** pane, enter a **Name** and **Description** for the custom profile.
5. From the **Platform** drop-down list, select the device platform to which you want to apply custom settings. Currently, you can choose one of the following platforms for custom device settings:
	- **Android**
	- **Android for Work**
	- **iOS**
	- **macOS**
	- **Windows Phone 8.1**
	- **Windows 8.1 and later**
	- **Windows 10 and later**
6. From the **Profile** type drop-down list, choose **Custom**.
7. Depending on the platform you chose, the settings you can configure are different. Go to one of the following topics for detailed settings for each platform:
	- [Android settings](custom-settings-android.md)
	- [iOS settings](custom-settings-ios.md)
	- [macOS settings](custom-settings-macos.md)
	- [Windows Phone 8.1 settings](custom-settings-windows-phone-8-1.md)
	- [Windows 10 settings](custom-settings-windows-10.md)
	- [Windows Holographic for Business settings](custom-settings-windows-holographic.md)
	- [Android for Work settings](custom-settings-android-for-work.md)
8. When you're done, go back to the **Create profile** pane, and hit **Create**.

The profile is created and appears on the profiles list pane.
If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).
