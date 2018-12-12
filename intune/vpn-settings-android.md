---
# required metadata

title: Configure VPN settings for Android devices in Microsoft Intune - Azure | Microsoft Docs
description: When creating a VPN configuration profile for Android and Android for work devices, enter the connection name, the IP address or FQDN of the VPN server, choose how users authenticate with the VPN server, and then choose Citrix, SonicWall, Check Point Capsule, Pulse Secure, and Microsoft Edge connection types.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/26/2018
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

# Configure VPN settings for devices running Android in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

This article shows you the Intune settings you can use to configure VPN connections on devices running Android.

You can configure VPN settings for the following platforms:

- [Android](#android-vpn-settings)
- [Android for work](#android-for-work-vpn-settings)

Depending on the settings you choose, not all the following values are configurable.

## Android VPN settings

- **Connection name**: Enter a name for this connection. End users see this name when they browse their device for the available VPN connections.
- **IP address or FQDN**: Enter the IP address or fully qualified domain name (FQDN) of the VPN server that devices connect. For example, enter **192.168.1.1** or **vpn.contoso.com**.

  - **Authentication method**: Choose how devices authenticate to the VPN server. Your options:

    - **Certificates**: Select an existing SCEP or PKCS certificate profile to authenticate the connection. [Configure certificates](certificates-configure.md) lists the steps to create a certificate profile.
    - **Username and password**: When signing into the VPN server, end users are prompted to enter a user name and password.

- **Connection type**: Select the VPN connection type. Your options:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Citrix**

- **Fingerprint** (Check Point Capsule VPN only): Enter a string, such as **Contoso Fingerprint Code**, to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that has the same fingerprint when connecting. If the device doesn’t have the fingerprint, it prompts the user to trust the VPN server while showing the fingerprint. The user manually verifies the fingerprint, and chooses trust to connect.
- **Enter key and value pairs for the Citrix VPN attributes** (Citrix only): Enter key and value pairs, provided by Citrix. These values configure the properties of the VPN connection.

## Android for work VPN settings

- **Connection name**: Enter a name for this connection. End users see this name when they browse their device for the available VPN connections.
- **IP address or FQDN**: Enter the IP address or fully qualified domain name (FQDN) of the VPN server that devices connect. For example, enter **192.168.1.1** or **vpn.contoso.com**.

  - **Authentication method**: Choose how devices authenticate to the VPN server. Your options:
  
    - **Certificates**: Select an existing SCEP or PKCS certificate profile to authenticate the connection. [Configure certificates](certificates-configure.md) lists the steps to create a certificate profile.
    - **Username and password**: When signing into the VPN server, end users are prompted to enter a user name and password.

- **Connection type**: Select the VPN connection type. Your options:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**

## Next steps
[VPN profiles in Intune](vpn-settings-configure.md)
