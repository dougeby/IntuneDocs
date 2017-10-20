---
# required metadata

title: How to configure Intune Wi-Fi settingstitleSuffix: "Azure portal"
description: Learn how to use Intune to configure Wi-Fi connections on devices you manage."
keywords:
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1fadb488-9c6c-43c1-ba23-8c69db633b96

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: karanda
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to configure Wi-Fi settings in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use Microsoft Intune Wi-Fi profiles to assign wireless network settings to users and devices in your organization. When you assign a Wi-Fi profile, your users will have access to your corporate Wi-Fi network without having to configure it themselves.

For example, you install a new Wi-Fi network named Contoso Wi-Fi and want to set up all iOS devices to connect to this network. Here's the process:

1. Create a Wi-Fi profile containing the settings necessary to connect to the Contoso Wi-Fi wireless network.
2. Assign the profile to a group containing all users of iOS devices.
3. Users find the new Contoso Wi-Fi network in the list of wireless networks on their device and can easily connect to it.

Wi-Fi profiles support the following device platforms:

- Android 4 and later
- Android for Work
- iOS 8.0 and later
- macOS (Mac OS X 10.9 and later)

For devices running Windows 8.1, Windows 10, and Windows 10 Mobile, you can import a Wi-Fi configuration that was previously exported from another device.

Use the information in this topic to learn the basics about configuring a Wi-Fi profile, and then read further topics for each platform to learn about device specifics.

## Create a device profile containing Wi-Fi settings

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device configuration**.
2. On the **Device Configuration** blade, choose **Manage** > **Profiles**.
3. On the profiles blade, choose **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the Wi-Fi profile.
5. From the **Platform** drop-down list, select the device platform to which you want to apply Wi-Fi settings. Currently, you can choose one of the following platforms for Wi-Fi settings:
	- **Android**
	- **Android for Work**
	- **iOS**
	- **macOS**
	- **Windows 8.1 and later (import a profile)**
6. From the **Profile** type drop-down list, choose **Wi-Fi basic** or **Wi-Fi enterprise**.
	>[!TIP]
	>Use **Wi-fi basic** to supply basic features like the network name, and the SSID. **Wi-Fi enterprise** lets you supply more advanced information like the  Extensible Authentication Protocol (EAP) if your Wi-Fi network uses this. **Wi-Fi import** (for Windows 8.1 and Windows 10) lets you import Wi-Fi settings as an XML file that you previusly exported from a different device.
7. Depending on the platform you chose, the settings you can configure will be different. Go to one of the following topics for detailed settings for each platform:
	- [Android and Android for Work settings](wi-fi-settings-android.md)
	- [iOS settings](wi-fi-settings-ios.md)
	- [macOS settings](wi-fi-settings-macos.md)
	- [Windows Phone 8.1 settings](wi-fi-settings-import-windows-8-1.md)
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.
If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).
