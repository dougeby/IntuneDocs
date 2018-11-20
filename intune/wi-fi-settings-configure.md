---
# required metadata

title: Create a Wi-Fi profile for devices in Microsoft Intune - Azure | Microsoft Docs
description: See the steps to create a Wi-Fi device configuration profile in Microsoft Intune. Ceate profiles for Android, Android Enterprise, Android kiosk, iOS, macOS, Windows 10 and later, and Windows Holographic for Business. Use these profiles to create a WiFi connection to use certificates, choose an EAP type, select an authentication method, enable a proxy, and more.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Add and use Wi-Fi settings on your devices in Microsoft Intune

Use Microsoft Intune Wi-Fi profiles to assign wireless network settings to users and devices in your organization. When you assign a Wi-Fi profile, your users can access your organization's Wi-Fi network without configuring it themselves.

For example, you install a new Wi-Fi network named Contoso Wi-Fi. You then want to set up all iOS devices to connect to this network. Here's the process:

1. Create a Wi-Fi profile that includes the settings to connect to the Contoso Wi-Fi wireless network.
2. Assign the profile to a group that contains all users of iOS devices.
3. Users find the new Contoso Wi-Fi network in the list of wireless networks on their device. They can then connect to the network, using the authentication method of your choosing.

Use the steps in this article to create a Wi-Fi profile. Then, review topics on platform-specific settings and details.

## Supported device platforms

Wi-Fi profiles support the following device platforms:

- Android 4 and later
- Android Enterprise and kiosk
- iOS 8.0 and later
- macOS (Mac OS X 10.11 and later)
- Windows 10 and later, Windows 10 Mobile, and Windows Holographic for Business

> [!NOTE]
> For devices running Windows 8.1, you can import a Wi-Fi configuration that was previously exported from another device.

## Create a Wi-FI device profile

1. In the [Azure portal](https://portal.azure.com), select **All services** > filter on **Intune**, and select **Microsoft Intune**. 
2. Select **Device configuration** > **Profiles** > **Create profile**.
3. Enter a **Name** and **Description** for the Wi-Fi profile.
4. In the **Platform** drop-down list, select the device platform to apply the Wi-Fi settings. Your options:

    - **Android**
    - **Android enterprise**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 and later**
    - **Windows 10 and later**

5. In **Profile Type**, choose **Wi-Fi**.

    - For **Android Enterprise** devices running as a kiosk, you can choose **Device owner only** > **Wi-Fi**.
    - For **Windows 8.1 and later**, you can choose **Wi-Fi import**. This option lets you import Wi-Fi settings as an XML file that you previously exported from a different device.

6. Some of the Wi-Fi settings are different for each platform. To see the settings for a specific platform, choose:

    - [Android](wi-fi-settings-android.md)
    - [Android Enterprise and kiosk](wi-fi-settings-android-enterprise.md)
    - [iOS](wi-fi-settings-ios.md)
    - [macOS](wi-fi-settings-macos.md)
    - [Windows 10 and later](wi-fi-settings-windows.md)
    - [Windows 8.1 and later](wi-fi-settings-import-windows-8-1.md), including Windows Holographic for Business

    Most platforms have **Basic** and **Enterprise** settings. **Basic** includes features such as the network name and the SSID. **Enterprise** lets you supply more advanced information, such as the Extensible Authentication Protocol (EAP).

7. When finished adding your Wi-Fi settings, select **Create Profile** > **Create** to add the configuration profile. The profile is created and is shown in the profiles list (**Device configuration** > **Profiles**).

## Next steps

The profile is created, but it's not doing anything. Next, [assign this profile](device-profile-assign.md).
