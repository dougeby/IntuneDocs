---
# required metadata

title: Intune VPN settings for Windows 8.1 devices | Microsoft Docs
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
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# VPN settings for Windows 8.1 devices

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Depending on the settings you choose, not all values in the list below will be configurable.

## Base VPN settings


**Connection name** - Enter a name for this connection. End users will see this name when they browse their device for the list of available VPN connections.
**Servers** - Add one or more VPN servers that devices will connect to.

- **Add** - Opens the **Add Row** blade where you can specify the following information:
	- **Description** - 
	- **IP address or FQDN** - 
	- **Default server** - Enables this server as the default server that devices will use to establish the connection. Make sure to set only one server as the default.
- **Import** - Browse to a file containing a comma-seperated list of servers in the format description, IP address or FQDN, Default server. Choose **OK** to import these into the **Servers** list.
- **Export** - Exports the list of servers to a comma-seperated-values (csv) file.

Connection type

Custom XML


## Proxy settings

- **Automatically detect proxy settings** - If your VPN server requires a proxy server for the connection, specify whether you want devices to automatically detect the connection settings. For more information, see your Windows Server documentation.
- **Automatic configuration script** - Use a file to configure the proxy server. Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.
- **Use proxy server** - Enable this option if you want to manually enter the proxy server settings.
	- **Address** - Enter the proxy server address (as an IP address).
	- **Port number** - Enter the port number associated with the proxy server.
- **Bypass proxy for local addresses** - If your VPN server requires a proxy server for the connection, select this option if you do not want to use the proxy server for local addresses that you specify. For more information, see your Windows Server documentation.
