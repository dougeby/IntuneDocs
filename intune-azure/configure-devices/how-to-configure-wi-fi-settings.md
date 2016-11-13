---
# required metadata

title: How to configure Microsoft Intune Wi-Fi settings | Microsoft Docs
description: Description.
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1fadb488-9c6c-43c1-ba23-8c69db633b96

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# How to configure WI-Fi settings in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]



## Create a device profile containing Wi-Fi settings

1. In the Azure Portal, select the **Device Configurations** workload.
2. On the **Device configuration** blade, select **Manage** > **Profiles**.
3. On the profiles blade, click **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the Wi-Fi profile.
5. From the **Platform** drop-down list, select the device platform to which you want to apply Wi-Fi settings. Currently, you can choose one of the following platforms for Wi-Fi settings:
	- **Android**
	- **iOS**
	- **macOS**
	- **Windows 8.1 and later (import a profile)**
6. From the **Profile** type drop-down list, choose **Wi-Fi basic** or **Wi-Fi enterprise**.
	>[!TIP]
	>Use **Wi-fi basic** to supply basic features like the network name, and the SSID. **Wi-Fi enterprise** lets you supply more advanced information like the  Extensible Authentication Protocol (EAP) if your Wi-Fi network uses this. **Wi-Fi import** (for Windows 8.1 and Windows 10) lets you import Wi-Fi settings as an XML file that you previusly exported from a different device.
7. Depending on the platform you chose, the settings you can configure will be different. Go to one of the following topics for detailed settings for each platform:
	- [Android settings](wi-fi-for-android.md)
	- [iOS settings](wi-fi-for-ios.md)
	- [macOS settings](wi-fi-for-macos.md)
	- [Windows Phone 8.1 settings](wi-fi-import-for-windows-8-1.md)
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.

