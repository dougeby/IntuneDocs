---
# required metadata

title: Intune VPN settings for Android devices | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn about the Intune settings you can use to configure VPN connections on Android devices."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/02/2017
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
#ms.custom:

---

# VPN settings for Android devices in Intune Azure preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Depending on the settings you choose, not all values in the list below will be configurable.

**Connection name** - Enter a name for this connection. End users will see this name when they browse their device for the list of available VPN connections.
- **IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to. Examples: **192.168.1.1**, **vpn.contoso.com**.
- **Authentication method** - Choose how devices will authenticate to the VPN server from:
	- **Certificates** - Select a SCEP or PKCS certificate profile you previously created to authenticate the connection. For more details about certificate profiles, see [How to configure certificates](how-to-configure-certificates.md).
	- **Username and password** - End users must supply a user name and password to log into the VPN server.
- **Connection type** - Select the VPN connection type from the following list of vendors:
	- **Check Point Capsule VPN**
	- **Cisco AnyConnect**
	- **Dell SonicWALL Mobile Connect**
	- **F5 Edge Client**
	- **Pulse Secure**
	- **Citrix**
