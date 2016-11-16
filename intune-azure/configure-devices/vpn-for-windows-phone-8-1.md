---
# required metadata

title: Intune VPN settings for Windows Phone 8.1 devices | Microsoft Docs
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
ms.assetid: c1a9053f-02a7-4735-bc0d-fe4573b31ed4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# VPN settings for Windows Phone 8.1 devices

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

Bypass VPN on company Wi-Fi network
Bypass VPN on home Wi-Fi network
Connection type

**VPN identifier** (if you selected the connection type **Custom VPN**) - This value identifies the VPN connection type for a custom VPN connection and is provided to you by the VPN vendor.

Enter key and value pairs for the custom VPN attributes (if you selected the connection type **Custom VPN**) - 
- Add
- Import
- Export

DNS suffix search list

Custom XML



**Split tunneling** - **Enable** or **Disable** this option which lets devices decide which connection to use depending on the traffic. For example, a user in a hotel will use the VPN connection to access work files, but use the hotel's standard network for regular web browsing.




**Proxy settings**

- **Automatically detect proxy settings** - 
- **Automatic configuration script** - Use a file to configure the proxy server. Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.
- **Use proxy server** - Enable this option if you want to manually enter the proxy server settings.
	- **Address** - Enter the proxy server address (as an IP address).
	- **Port number** - Enter the port number associated with the proxy server.
- **Bypass proxy for local addresses** - 
