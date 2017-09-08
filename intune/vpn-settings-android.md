---
# required metadata

title: Intune VPN settings for Android devices
titlesuffix: "Azure portal"
description: Learn about the Intune settings you can use to configure VPN connections on Android devices
keywords:
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 16c056ca-320e-4107-ad03-a0cf96c28885

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: karanda
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# VPN settings for Android devices in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

As an Intune admin, you can configure VPN settings for the following platforms:

- [Android](#android-vpn-settings)
- [Android for Work](#android-for-work-vpn-settings)

Depending on the settings you choose, not all values listed below are configurable.

## Android VPN settings
**Connection name** - Enter a name for this connection. End users will see this name when they browse their device for the list of available VPN connections.
- **IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to. Examples: **192.168.1.1**, **vpn.contoso.com**.
- **Authentication method** - Choose how devices will authenticate to the VPN server from:
	- **Certificates** - Select a SCEP or PKCS certificate profile you previously created to authenticate the connection. For more details about certificate profiles, see [How to configure certificates](certificates-configure.md).
	- **Username and password** - End users must supply a user name and password to log into the VPN server.
- **Connection type** - Select the VPN connection type from the following list of vendors:
	- **Check Point Capsule VPN**
	- **Cisco AnyConnect**
	- **Dell SonicWALL Mobile Connect**
	- **F5 Edge Client**
	- **Pulse Secure**
	- **Citrix**

- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint (The user manually verifies the fingerprint and chooses trust to connect).
- **Enter key and value pairs for the Citrix VPN attributes** (Citrix only) - Enter key and value pairs, provided by Citrix, to configure the properties of the VPN connection.

## Android for Work VPN settings

**Connection name** - Enter a name for this connection. End users will see this name when they browse their device for the list of available VPN connections.
- **IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to. Examples: **192.168.1.1**, **vpn.contoso.com**.
- **Authentication method** - Choose how devices will authenticate to the VPN server from:
	- **Certificates** - Select a SCEP or PKCS certificate profile you previously created to authenticate the connection. For more details about certificate profiles, see [How to configure certificates](certificates-configure.md).
	- **Username and password** - End users must supply a user name and password to log into the VPN server.
- **Connection type** - Select the VPN connection type from the following list of vendors:
	- **Check Point Capsule VPN**
	- **Cisco AnyConnect**
	- **Dell SonicWALL Mobile Connect**
	- **F5 Edge Client**
	- **Pulse Secure**

- **Split tunneling** - Enable to let certain web traffic use the VPN connection when the VPN while other traffic uses the internet. Disable this setting if you want all traffic to use the VPN when active.
