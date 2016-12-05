---
# required metadata

title: How to configure Microsoft Intune custom device settings | Intune Azure preview | Microsoft Docs
description: Learn how to use Intune to configure custom settings on devices you manage.
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
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
#ms.custom:

---

# How to configure custom device settings in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use the information in this topic to learn the basics about configuring profiles with custom settings, and then read further topics for each platform to learn about device specifics.

## Create a device profile containing custom settings

1. In the Azure Portal, select the **Device Configurations** workload.
2. On the **Device configuration** blade, select **Manage** > **Profiles**.
3. On the profiles blade, click **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the custom profile.
5. From the **Platform** drop-down list, select the device platform to which you want to apply custom settings. Currently, you can choose one of the following platforms for custom device settings:
	- **Android**
	- **iOS**
	- **macOS**
	- **Windows Phone 8.1**
	- **Windows 10 and later**
6. From the **Profile** type drop-down list, choose **Custom**.
7. Depending on the platform you chose, the settings you can configure will be different. Go to one of the following topics for detailed settings for each platform:
	- [Android settings](custom-for-android.md)
	- [iOS settings](custom-for-ios.md)
	- [macOS settings](custom-for-macos.md)
	- [Windows Phone 8.1 settings](custom-for-windows-phone-8-1.md)
	- [Windows 10 settings](custom-for-windows-10.md)
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.

