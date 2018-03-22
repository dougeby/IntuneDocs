---
# required metadata

title: VPN settings for iOS devices in Microsoft Intune - Azure | Microsoft Docs
description: View the avialable virtual private network (VPN) configuration settings, including the connection details, authentication methods, and split tunneling in the base settings; the custom VPN settings with the identifier, and the key and value pairs; the per-app VPN settings that include Safari URLs, and on-demand VPNs with SSIDs or DNS search domains; and the proxy settings to include a configuration script, IP or FQDN address, and TCP port in Microsoft Intune on devices running iOS.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/22/2018
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

# Configure VPN settings in Microsoft Intune for devices running iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

This article shows you the Intune settings you can use to configure VPN connections on devices running iOS.

Depending on the settings you choose, not all values in the following list are configurable.

## Base VPN settings

- **Connection name**: Enter a name for this connection. End users see this name when they browse their device for a list of available VPN connections.
- **IP address or FQDN**: Enter the IP address or fully qualified domain name (FQDN) of the VPN server that devices connect. For example, enter **192.168.1.1** or **vpn.contoso.com**.
- **Authentication method**: Choose how devices authenticate to the VPN server from:
  - **Certificates**: Under **Authentication certificate**, choose an existing SCEP or PKCS certificate profile to authenticate the connection. [Configure certificates](certificates-configure.md) provides some guidance on certificate profiles.
  - **Username and password**: End users must enter a username and password to sign in to the VPN server.
- **Connection type**: Select the VPN connection type from the following list of vendors:
  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **Cisco Legacy AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Cisco (IPSec)**
  - **Citrix**
  - **Custom VPN**

    > [!NOTE]
    > - **Cisco Legacy AnyConnect VPN** profiles are for the [Cisco Legacy AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) app version 4.0.5x, and older versions
    > - **Cisco AnyConnect VPN** profiles are for the [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) app version 4.0.7x, and newer versions

- **Split tunneling**: **Enable** or **Disable** to let devices decide which connection to use depending on the traffic. For example, a user in a hotel uses the VPN connection to access work files, but use the hotel's standard network for regular web browsing.

## Custom VPN settings

If you selected **Custom VPN** as the connection type, also configure the following settings:

- **VPN identifier**: An identifier for the VPN app you're using, and is supplied by your VPN provider.
- **Enter key and value pairs for the custom VPN attributes**: Add or import **Keys** and **Values** that customize your VPN connection. Again, these values are typically supplied by your VPN provider.

## Apps (per-app VPN) settings

- **Per-app VPN**: Enable this option to use URLs that enable the VPN connection when they are visited from the Safari browser. To configure per-app VPN, you must select **Certificates** as the authentication method in the base VPN settings.
  - **Safari URLs that will trigger this VPN**: Select to add one or more web site URLs. When these URLs are visited, the VPN connection is enabled.

- **On-demand VPN**: Configure conditional rules that control when the VPN connection is initiated. For example, create a condition where the VPN connection is only used when a device is not connected to a company Wi-Fi network. Or, create a condition where, if a device can't access a DNS search domain you specify, then the VPN connection is not initiated.

  - **SSIDs or DNS search domains**: Select whether this condition uses wireless network **SSIDs**, or **DNS search domains**. Choose **Add** to configure one or more SSIDs or search domains.
  - **URL string probe**: Optional. Enter a URL that the rule uses as a test. If the device where this profile is installed can access this URL without redirection, then the VPN connection is initiated, and the device connects to the target URL. The user does not see the URL string probe site. A URL string probe example is the address of an auditing Web server that checks device compliance before connecting the VPN. Another possibility is that the URL tests the ability of the VPN to connect to a site before connecting the device to the target URL through the VPN.
  - **Domain action**: Choose one of the following items:
    - Connect if needed
    - Never connect
  - **Action**: Choose one of the following items:
    - Connect
    - Evaluate connection
    - Ignore
    - Disconnect

## Proxy settings

- **Automatic configuration script**: Use a file to configure the proxy server. Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) that contains the configuration file.
- **Address**: Enter the IP address of fully qualified host name of the proxy server.
- **Port number**: Enter the port number associated with the proxy server.