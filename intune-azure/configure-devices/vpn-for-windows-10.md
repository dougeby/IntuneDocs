---
# required metadata

title: Intune VPN settings for Windows 10 devices | Microsoft Docs
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
ms.assetid: 495e4ed6-b2ef-47cc-a110-13fa9b5f85a6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# VPN for iOS

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Depending on the settings you choose, not all values in the list below will be configurable.

**Base VPN Settings**


**Connection name** - Enter a name for this connection. End users will see this name when they browse their device for the list of available VPN connections.
**Servers** - Add one or more VPN servers that devices will connect to.

- **Add** - Opens the **Add Row** blade where you can specify the following information:
	- **Description** - 
	- **IP address or FQDN** - 
	- **Default server** - Enables this server as the default server that devices will use to establish the connection. Make sure to set only one server as the default.
- **Import** - Browse to a file containing a comma-seperated list of servers in the format description, IP address or FQDN, Default server. Choose **OK** to import these into the **Servers** list.
- **Export** - Exports the list of servers to a comma-seperated-values (csv) file.

Connection type

**Split tunneling** - **Enable** or **Disable** this option which lets devices decide which connection to use depending on the traffic. For example, a user in a hotel will use the VPN connection to access work files, but use the hotel's standard network for regular web browsing.

**Apps and Traffic Rules**

Restrict VPN connection to these apps
Associated Apps
- Add
- Import
- Export

Network traffic rules for this VPN connection




**Conditional Access**

Conditional access for this VPN connection
Single sign-on (SSO) with alternate certificate
Extended key usage
Issuer hash
EAP XML


**DNS Settings**

DNS Triggers
- Add
- Import
- Export

DNS names and servers for this VPN connection
- Add
- Import
- Export
- 

**Proxy settings**

Automatically detect proxy settings
Automatic configuration script
Use proxy server
Address
Port number
Bypass proxy for local addresses
