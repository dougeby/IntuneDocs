---
# required metadata

title: Intune VPN settings for iOS devices | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn about the Intune settings you can use to configure VPN connections on iOS devices."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1447c123-ea33-4ea0-aab4-69577cdb8d00

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# VPN settings for iOS devices

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Depending on the settings you choose, not all values in the list below will be configurable.

## Base VPN settings


**Connection name** - Enter a name for this connection. End users will see this name when they browse their device for the list of available VPN connections.
**Servers** - Adds one or more VPN servers that devices will connect to with the following options:
- **Add** - Opens the **Add Row** blade where you can specify the following information:
	- **Description** - Specify a descriptive name for the entry like **Contoso VPN server**.
	- **IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to. Examples: **192.168.1.1**, **vpn.contoso.com**. 
	- **Default server** - Enables this server as the default server that devices will use to establish the connection. Make sure to set only one server as the default.
- **Import** - Browse to a file containing a comma-seperated list of servers in the format description, IP address or FQDN, Default server. Choose **OK** to import these into the **Servers** list.
- **Export** - Exports the list of servers to a comma-seperated-values (csv) file.

**Authentication method** - 
- **Certificates** - Choose a SCEP or PKCS certificate profile you previously created to authenticate the connection. For more details about certificate profiles, see [How to configure certificates](how-to-configure-certificates.md).
- **Username and password** - End users must supply a username and password to log into the VPN server.

**Connection type** - Select the VPN connection type from the following list of vendors:
- **Check Point Capsule VPN**
- **Cisco AnyConnect**
- **Dell SonicWALL Mobile Connect**
- **F5 Edge Client**
- **Pulse Secure**
- **Cisco (IPSec)**
- **Citrix**
- **Custom VPN**

**Split tunneling** - **Enable** or **Disable** this option which lets devices decide which connection to use depending on the traffic. For example, a user in a hotel will use the VPN connection to access work files, but use the hotel's standard network for regular web browsing.

## Custom VPN settings

If you selected **Custom VPN**, configure these further settings:

- **VPN identifier** This is an identifier for the VPN app you are using, and is supplied by your VPN provider. 
- **Enter key and value pairs for the custom VPN attributes** Add or import **Keys** and **Values** that customize your VPN connection. Again, these values are typically supplied by your VPN provider.


## Proxy settings

- **Automatic configuration script** - Use a file to configure the proxy server. Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.
- **Use proxy server** - Enable this option if you want to manually enter the proxy server settings.
	- **Address** - Enter the proxy server address (as an IP address).
	- **Port number** - Enter the port number associated with the proxy server.





