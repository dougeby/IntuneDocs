---
# required metadata

title: Configure Intune device restriction settings
titleSuffix: "Azure portal"
description: Learn how to use Intune to configure settings and features on devices you manage."
keywords:
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 04/12/2017
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

# How to configure device restriction settings in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Device restrictions let you control a wide range of settings and features you manage across a range of categories including security, browser, hardware, and data sharing settings. For example, you could create a device restriction profile that prevents users of iOS devices from accessing the device camera.

Use the information in this topic to learn the basics about configuring device restriction profiles, and then read further topics for each platform to learn about device specifics.

## Create a device profile containing device restriction settings

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Configure devices**.
2. On the **Device Configuration** blade, choose **Manage** > **Profiles**.
3. On the profiles blade, choose **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the device restriction profile.
5. From the **Platform** drop-down list, select the device platform to which you want to apply custom settings. Currently, you can choose one of the following platforms for device restriction settings:
	- **Android**
	- **iOS**
	- **macOS**
	- **Windows Phone 8.1**
	- **Windows 8.1 and later**
	- **Windows 10 and later**
6. From the **Profile type** type drop-down list, choose **Device restrictions**. If you want to create a device restrictions profile for Windows 10 Team devices like a Surface Hub, choose **Device restrictions (Windows 10 Team)**.
7. Depending on the platform you chose, the settings you can configure will be different. Go to one of the following topics for detailed settings for each platform:
	- [Android settings](device-restrictions-android.md)
	- [iOS settings](device-restrictions-ios.md)
	- [macOS settings](device-restrictions-macos.md)
	- [Windows Phone 8.1 settings](device-restrictions-windows-phone-8-1.md)
	- [Windows 8.1](device-restrictions-windows-8-1.md)
	- [Windows 10 settings](device-restrictions-windows-10.md)
	- [Windows 10 Team settings](device-restrictions-windows-10-teams.md)
	- [Android for Work settings](device-restrictions-android-for-work.md)
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.
If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->