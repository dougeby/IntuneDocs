---
# required metadata

title: Wi-Fi settings for Windows 10 devices in Microsoft Intune - Azure | Microsoft Docs
description: Add or create Wi-Fi configuration profile using Wi-Fi settings for Windows 10 and later devices in Microsoft Intune. You can configure Basic settings, or enterprise-level settings. 
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/27/2018
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

## Wi-Fi settings for Windows 10 and later devices in Intune

Wi-Fi settings are used in a configuration profile that applies to devices running Windows 10 and later. Your options include:

- **Not configured**
- **Basic**
- **Enterprise**

## Before you begin

[Create a device profile](device-profile-create.md).

## Basic settings

- **Wi-Fi name (SSID)**: Enter the correct service set identifier name of the existing wireless network. When users connect, users see the **Connection name** on the devices.
- **Connection name**: Enter a user-friendly name for this Wi-Fi connection. The text you enter is the name users see when they browse the available connections on their device.
- **Connect automatically when in range​**: When **Yes**, devices connect automatically when they're in range of this network. When **No**, devices don't automatically connect.
  - **Connect to more preferred network if available​**: If the devices are in range of a more preferred network, then choose **Yes** to use this preferred network instead of this Wi-Fi network. Choose **No** to use the Wi-Fi network in this configuration profile.

    For example, you create a **ContosoCorp** Wi-Fi network, and use **ContosoCorp** within this configuration profile. You also have a **ContosoGuest** Wi-Fi network within range. When your corporate devices are within range, you want them to automatically connect to **ContosoCorp**. In this scenario, set this property to **No**.

  - **Connect to this network, even when it is not broadcasting its SSID**: Choose **Yes** if want this configuration profile to automatically connect to your network, even when it is hidden (meaning its SSID is not broadcast publicly). Choose **No** if you do not want this configuration profile to connect to your network if the network is hidden.

- **Wireless Security Type**: Enter the security protocol used to authenticate devices on your network. Your options are:
  - **Open (no authentication)**: Only use this option if the network is unsecured.
  - **WPA/WPA2 - Personal

- **Company Proxy settings**: Choose to use the proxy settings within your organization. Your options:
  - **None**: No proxy settings are configured.
  - **Manually configure**: Enter the **Proxy server IPaddress** and its **Port number**.
  - **Automatically configure**: Enter the URL pointing to a proxy auto-configuration (PAC) script. For example, enter `http://proxy.contoso.com/proxy.pac`.

<!--- **Force Wi-Fi profile to be compliant with the Federal Information Processing Standard (FIPS)**: Validates against the FIPS 140-2 standard. The FIPS 140-2 standard is required for all US federal government agencies that use cryptography-based security systems. This standard helps protect sensitive but unclassified information stored digitally.--->

## Enterprise settings

- **Wi-Fi name (SSID)**: Enter the correct service set identifier name of the existing wireless network. When users connect, users see the **Connection name** on the devices.
- **Connection name**: Enter a user-friendly name for this Wi-Fi connection. The text you enter is the name users see when they browse the available connections on their device.
- **Connect automatically when in range​**: When **Yes**, devices connect automatically when they're in range of this network. When **No**, devices don't automatically connect.
  - **Connect to more preferred network if available​**: If the devices are in range of a more preferred network, then choose **Yes** to use this preferred network instead of this Wi-Fi network. Choose **No** to use the Wi-Fi network in this configuration profile.

    For example, you create a **ContosoCorp** Wi-Fi network, and use **ContosoCorp** within this configuration profile. You also have a **ContosoGuest** Wi-Fi network within range. When your corporate devices are within range, you want them to automatically connect to **ContosoCorp**. In this scenario, set this property to **No**.
​
- **Connect to this network, even when it is not broadcasting its SSID**: NEED A DESCRIPTION, AND EXPLAIN WHAT "YES" AND "NO" OPTIONS DO.

- **Single sign-on (SSO)**: This allows you to configure single sign-on (SSO), where credentials are shared for computer and Wi-Fi network logon. Your options are:
  - **Disable** - Disables SSO behavior and the user needs to authenticate to the network separately.
  - **Enable before user signs into device** - Uses SSO to authenticate to the network just prior to the user logon process.
  - **Enable after user signs into device** - Uses SSO to authenticate to the network immediately after the user logon process completes.
  
   - **Maximum time to authenticate before timeout** - Indicates the maximum amount of time to wait before authenticating to the network, from 1-120 seconds.
   - **Allow Windows to prompt user for additional authentication credentials** - Choose **Yes** to allow the Windows system to display prompts for the user to input additional credentials if the authentication method requires it. Choose **No** to suppress these prompts.

#### Fast roaming settings

- **Enable pairwise master key (PMK) caching**: Select **Yes** to cache the PMK used in authentication. This caching typically allows the authentication to the network to complete faster. Choose **No** to force the authentication handshake when connecting to the Wi-Fi network every time.

  - **Maximum time a PMK is stored in cache**: Enter the number of minutes a pairwise master key (PMK) is stored in the cache, from 5-1440 minutes.
  - **Maximum number of PMKs stored in cache**: Enter the number of keys stored in cache, from 1-255.

- **Enable pre-authentication**: Pre-authentication allows the profile to authenticate to all access points for the network specified by the profile before connecting to them, in order to reconnect more quickly when moving between access points. Choose **Yes** to allow the profile to authenticate to all access points for this network that are within range. Choose **No** to require the user/device to authenticate to each access point separately.

  - **Maximum pre-authentication attempts**: Enter the number of tries to preauthenticate, from 1-16.

#### Extensible Authentication Protocol (EAP)

- **EAP type**: Select the Extensible Authentication Protocol type that is configured on your Wi-Fi network. Your options:
  - **EAP - SIM**
  - **EAP - TLS**
  - **EAP - TTLS**
  - **Protected EAP (PEAP)**

- **Company Proxy settings**: Choose to use the proxy settings within your organization. Your options:
  - **None**: No proxy settings are configured.
  - **Manually configure**: Enter the **Proxy server IPaddress** and its **Port number**.
  - **Automatically configure**: Enter the URL pointing to a proxy auto-configuration (PAC) script. For example, enter `http://proxy.contoso.com/proxy.pac`.

## Use an imported settings file

For any settings not available in Intune, you can export Wi-Fi settings from another Windows device. This export creates an XML file with all the settings. Then, import this file in to Intune, and use it as the Wi-Fi profile. See [Export and import Wi-Fi settings for Windows devices](wi-fi-settings-import-windows-8-1.md).

## Next steps
[Configure Wi-Fi settings in Intune](wi-fi-settings-configure.md)
