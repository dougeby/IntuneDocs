---
# required metadata

title: Intune VPN settings for Windows 8.1 devices
titleSuffix: "Azure portal"
description: Learn about the Intune settings you can use to configure VPN connections on Windows 8.1 devices."
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 12/15/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: karanda
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# VPN settings for Windows 8.1 devices in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Depending on the settings you choose, not all values in the list below will be configurable.

## Base VPN settings


- **Apply all settings to Windows 8.1 only** - This is a setting you can configure in the Intune classic portal. In the Azure portal, this setting cannot be changed. If this is set to **Configured**, any settings will only be applied to Windows 8.1 devices. If set to **Not Configured**, these settings will also apply to Windows 10 devices.
- **Connection name** - Enter a name for this connection. End users will see this name when they browse their device for the list of available VPN connections.
- **Servers** - Add one or more VPN servers that devices will connect to.
	- **Add** - Opens the **Add Row** blade where you can specify the following information:
		- **Description** - Specify a descriptive name for the server like **Contoso VPN server**.
		- **IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to. Examples: **192.168.1.1**, **vpn.contoso.com**.
		- **Default server** - Enables this server as the default server that devices will use to establish the connection. Make sure to set only one server as the default.
	- **Import** - Browse to a file containing a comma-seperated list of servers in the format description, IP address or FQDN, Default server. Choose **OK** to import these into the **Servers** list.
	- **Export** - Exports the list of servers to a comma-seperated-values (csv) file.

- **Connection type** - Select the VPN connection type from the following list of vendors:
- **Check Point Capsule VPN**
- **Dell SonicWALL Mobile Connect**
- **F5 Edge Client**
- **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **Login group or domain** (Dell SonicWALL Mobile Connect only) - Specify the name of the login group or domain that you want to connect to.

- **Role** (Pulse Secure only) - Specify the name of the user role that has access to this connection. A user role defines personal settings and options, and it enables or disables certain access features.

- **Realm** (Pulse Secure only) - Specify the name of the authentication realm that you want to use. An authentication realm is a grouping of authentication resources that the Pulse Secure connection type uses.


- **Custom XML** - Specify any custom XML commands that configure the VPN connection.

**Example for Pulse Secure:**

```
	<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>

```

**Example for CheckPoint Mobile VPN:**
```
	<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />

```

**Example for Dell SonicWALL Mobile Connect:**
```
	<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>

```

**Example for F5 Edge Client:**

```
	<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>

```

Refer to each manufacturer's VPN documentation for more information about how to write custom XML commands.


## Proxy settings

- **Automatically detect proxy settings** - If your VPN server requires a proxy server for the connection, specify whether you want devices to automatically detect the connection settings. For more information, see your Windows Server documentation.
- **Automatic configuration script** - Use a file to configure the proxy server. Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.
- **Use proxy server** - Enable this option if you want to manually enter the proxy server settings.
	- **Address** - Enter the proxy server address (as an IP address).
	- **Port number** - Enter the port number associated with the proxy server.
- **Bypass proxy for local addresses** - If your VPN server requires a proxy server for the connection, select this option if you do not want to use the proxy server for local addresses that you specify. For more information, see your Windows Server documentation.
