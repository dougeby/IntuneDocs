---
# required metadata

title: Intune VPN settings for iOS devices
titlesuffix: "Azure portal"
description: Learn about the Intune settings you can use to configure VPN connections on iOS devices."
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 12/15/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1447c123-ea33-4ea0-aab4-69577cdb8d00

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: karanda
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# VPN settings for iOS devices in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Depending on the settings you choose, not all values in the following list are configurable.

## Base VPN settings


**Connection name** - Enter a name for this connection. End users see this name when they browse their device for the list of available VPN connections.
- **IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices connect to. Examples: **192.168.1.1**, **vpn.contoso.com**.
- **Authentication method** - Choose how devices authenticate to the VPN server from:
	- **Certificates** - Under **Authentication certificate**, Choose a SCEP or PKCS certificate profile you previously created to authenticate the connection. For more information about certificate profiles, see [How to configure certificates](certificates-configure.md).
	- **Username and password** - End users must supply a username and password to log in to the VPN server.
- **Connection type** - Select the VPN connection type from the following list of vendors:
	- **Check Point Capsule VPN**
	- **Cisco AnyConnect**
	- **Dell SonicWALL Mobile Connect**
	- **F5 Edge Client**
	- **Pulse Secure**
	- **Cisco (IPSec)**
	- **Citrix**
	- **Custom VPN**
- **Split tunneling** - **Enable** or **Disable** this option, which lets devices decide which connection to use depending on the traffic. For example, a user in a hotel uses the VPN connection to access work files, but use the hotel's standard network for regular web browsing.


## Custom VPN settings

If you selected **Custom VPN** as the connection type, configure these further settings:

- **VPN identifier** This is an identifier for the VPN app you are using, and is supplied by your VPN provider.
- **Enter key and value pairs for the custom VPN attributes** Add or import **Keys** and **Values** that customize your VPN connection. Again, these values are typically supplied by your VPN provider.

## Apps (per-app VPN) settings

- **Per-app VPN** - Enable this option if you want to URLs that enable the VPN connection when they are visited from the Safari browser. To configure this, you must have selected **Certificates** as the authentication method in the base VPN settings.
- **URLs that enable the VPN connection while using the Safari browser** - Click add to add one or more web site URLs. When these URLs are visited, the VPN connection is enabled.

- **On-demand rules** - This lets you configure conditional rules that control when the VPN connection is initiated. For example, you could create a condition where the VPN connection is only used when a device is not connected to one of your company Wi-Fi networks. Alternatively, you could create a condition where, if a device cannot access a DNS search domain you specify, then the VPN connection is not initiated.

	- **SSIDs or DNS search domains** - Select whether this condition uses wireless network **SSIDs**, or **DNS search domains**. Choose Add to configure one or more SSIDs or search domains.
	- **URL string probe** - Optionally, provide a URL that the rule uses as a test. If the device on which this profile is installed is able to access this URL without redirection, the VPN connection is initiated and the device connects to the target URL. The user will not see the URL string probe site. An example of a URL string probe is the address of an auditing Web server that checks device compliance before connecting the VPN. Another possibility is that the URL tests the ability of the VPN to connect to a site before connecting the device to the target URL through the VPN.
	- **Domain action** - Choose one of the following items:
		- Connect if needed - 
		- Never connect - 
	- **Action** - Choose one of the following items:
		- Connect - 
		- Evaluate connection - 
		- Ignore - 
		- Disconnect - 


## Proxy settings

- **Automatic configuration script** - Use a file to configure the proxy server. Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.
- **Address** - Enter the proxy server address (as an IP address).
- **Port number** - Enter the port number associated with the proxy server.