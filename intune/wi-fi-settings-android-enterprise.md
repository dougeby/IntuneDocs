---
# required metadata

title: Configure Wi-Fi settings for Android Enterprise and kiosk devices
titleSuffix: Microsoft Intune
description: Create or add a WiFi device configuration profile for Android Enterprise and Android Kiosk. See the different settings, including adding certificates, choosing an EAP type, and selecting an authentication method in Microsoft Intune. For kiosk devices, also enter the Pre-shared key of your network.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
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
ms.custom: seodec18

---

# Add Wi-Fi settings for devices running Android Enterprise and Android kiosk in Microsoft Intune

You can create a profile with specific WiFi settings, and then deploy this profile to your Android Enterprise and Android kiosk devices. Microsoft Intune offers many features, including authenticating to your network, using a pre-shared key, and more.

This article describes these settings.

## Before you begin

[Create a device profile](device-profile-create.md).

## Device owner only - kiosk

Select this option if using an Android Enterprise device as a kiosk.

- **Network name**: Enter a name for this Wi-Fi connection. This value is the name that users see when they browse the list of available connections on their device.
- **SSID**: Short for **service set identifier**. This setting is the real name of the wireless network that devices connect to. However, users only see the **network name** you configured when they choose the connection.
- **Connect automatically**: Choose **Enable** to automatically connect to this network when the device is in range. Choose **Disable** to prevent devices from automatically connecting.
- **Hidden network**: Choose **Enable** to hide this network from the list of available networks on the device. The SSID isn't broadcasted. Choose **Disable** to show this network in the list of available networks on the device.
- **Wi-Fi type**: Select the security protocol to authenticate to the Wi-Fi network. Your options:

  - **Open (no authentication)**: Only use this option if the network is unsecured.
  - **WEP-Pre-shared key**: Enter the password in **Pre-shared key**. When your organization's network is set up or configured, a password or network key is also configured. Enter this password or network key for the PSK value.
  - **WPA-Pre-shared key**: Enter the password in **Pre-shared key**. When your organization's network is set up or configured, a password or network key is also configured. Enter this password or network key for the PSK value.

Select **OK** to save your changes.

## Work profile only

### Basic settings

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

- See the settings available for Android devices at [Wi-Fi settings for devices running Android](wi-fi-settings-android.md).
- [Wi-Fi settings overview](wi-fi-settings-configure.md), including other platforms.