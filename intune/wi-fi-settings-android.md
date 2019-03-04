---
# required metadata

title: Configure Wi-Fi settings for Android devices in Microsoft Intune - Azure | Microsoft Docs
titleSuffix:
description: Create or add a WiFi device configuration profile for Android. See the different settings, including adding certificates, choosing an EAP type, and selecting an authentication method in Microsoft Intune.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2018
ms.topic: conceptual
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
ms.collection: M365-identity-device-management
---

# Add Wi-Fi settings for devices running Android in Microsoft Intune

You can create a profile with specific WiFi settings, and then deploy this profile to your Android devices. Microsoft Intune offers many features, including authenticating to your network, adding a PKS or SCEP certificate, and more.

These Wi-Fi settings are separated in to two categories: Basic settings and Enterprise-level settings.

This article describes these settings.

## Before you begin

[Create a device profile](device-profile-create.md).

## Basic profile

- **Wi-Fi type**: Choose **Basic**.
- **SSID**: Short for **service set identifier**. This setting is the real name of the wireless network that devices connect to.
- **Connect automatically**: Choose **Enable** to automatically connect to this network when the device is in range. Choose **Disable** to prevent devices from automatically connecting.
- **Hidden network**: Choose **Enable** to hide this network from the list of available networks on the device. The SSID isn't broadcasted. Choose **Disable** to show this network in the list of available networks on the device.

## Enterprise profile

- **Wi-Fi type**: Choose **Enterprise**.
- **SSID**: Short for **service set identifier**. This setting is the real name of the wireless network that devices connect to.
- **Connect automatically**: Choose **Enable** to automatically connect to this network when the device is in range. Choose **Disable** to prevent devices from automatically connecting.
- **Hidden network**: Choose **Enable** to hide this network from the list of available networks on the device. The SSID isn't broadcasted. Choose **Disable** to show this network in the list of available networks on the device.
- **EAP type**: Choose the Extensible Authentication Protocol (EAP) type used to authenticate secured wireless connections. Your options: 

  - **EAP-TLS**: Also enter:

    - **Server Trust** - **Root certificate for server validation**: Choose an existing trusted root certificate profile. This certificate is presented to the server when the client connects to the network, and is used to authenticate the connection.

      Select **OK** to save your changes.

    - **Client Authentication** - **Client certificate for client authentication (Identity certificate)**: Choose the SCEP or PKCS client certificate profile that is also deployed to the device. This certificate is the identity presented by the device to the server to authenticate the connection.

      Select **OK** to save your changes.

  - **EAP-TTLS**: Also enter:

    - **Server Trust** - **Root certificate for server validation**: Choose an existing trusted root certificate profile. This certificate is presented to the server when the client connects to the network, and is used to authenticate the connection.

      Select **OK** to save your changes.

    - **Client Authentication** - Choose an **Authentication method**. Your options:

      - **Username and Password**: Prompt the user for a user name and password to authenticate the connection. Also enter:
        - **Non-EAP method (inner identity)**: Choose how you authenticate the connection. Be sure you choose the same protocol that's configured on your Wi-Fi network.

          Your options: **Unencrypted password (PAP)**, **Challenge Handshake Authentication Protocol (CHAP)**, **Microsoft CHAP (MS-CHAP)**, or **Microsoft CHAP Version 2 (MS-CHAP v2)**

      - **Certificates**: Choose the SCEP or PKCS client certificate profile that is also deployed to the device. This certificate is the identity presented by the device to the server to authenticate the connection.

        Select **OK** to save your changes.

      - **Identity privacy (outer identity)**: Enter the text sent in the response to an EAP identity request. This text can be any value, such as `anonymous`. During authentication, this anonymous identity is initially sent, and then followed by the real identification sent in a secure tunnel.

  - **PEAP**: Also enter:

    - **Server Trust** - **Root certificate for server validation**: Choose an existing trusted root certificate profile. This certificate is presented to the server when the client connects to the network, and is used to authenticate the connection.

      Select **OK** to save your changes.

    - **Client Authentication** - Choose an **Authentication method**. Your options:

      - **Username and Password**: Prompt the user for a user name and password to authenticate the connection. Also enter:
        - **Non-EAP method for authentication (inner identity)**: Choose how you authenticate the connection. Be sure you choose the same protocol that's configured on your Wi-Fi network.

          Your options: **None** or **Microsoft CHAP Version 2 (MS-CHAP v2)**

      - **Certificates**: Choose the SCEP or PKCS client certificate profile that is also deployed to the device. This certificate is the identity presented by the device to the server to authenticate the connection.

        Select **OK** to save your changes.

      - **Identity privacy (outer identity)**: Enter the text sent in the response to an EAP identity request. This text can be any value, such as `anonymous`. During authentication, this anonymous identity is initially sent, and then followed by the real identification sent in a secure tunnel.

Select **OK** > **Create** to save your changes. The profile is created and is shown in the profiles list.

## Next steps

The profile is created, but it's not doing anything. Next, [assign this profile](device-profile-assign.md).

## More resources

- [Wi-Fi settings overview](wi-fi-settings-configure.md), including other platforms.

- Using Android Enterprise or Android Kiosk devices? If yes, then look at [Wi-Fi settings for devices running Android Enterprise and Android kiosk](wi-fi-settings-android-enterprise.md).
