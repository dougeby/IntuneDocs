---
# required metadata

title: Configure Windows 10 VPN settings in Microsoft Intune - Azure | Microsoft Docs
description: Learn and read about the available VPN settings in Microsoft Intune, what they are used for, and what they do, including traffic rules, conditional access, and DNS and proxy settings for Windows 10 devices and Windows Holographic for Business devices.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 5/16/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
ms.reviewer: tycast
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Windows 10 VPN settings in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

You can configure VPN connections using Intune. This article describes these settings, the traffic rules, conditional access, and DNS & proxy settings.

These settings apply to:

- Devices running Windows 10
- Devices running Windows Holographic for Business

Depending on the settings you choose, not all values may be configurable.

## Base VPN settings

- **Connection name**: Enter a name for this connection. End users see this name when they browse their device for the list of available VPN connections.
- **Servers**: Add one or more VPN servers that devices connect to. When you add a server, you enter the following information:
  - **Description**: Enter a descriptive name for the server, such as **Contoso VPN server**
  - **IP address or FQDN**: Enter the IP address or fully qualified domain name of the VPN server that devices connect to, such as **192.168.1.1** or **vpn.contoso.com**
  - **Default server**: Enables this server as the default server that devices use to establish the connection. Set only one server as the default.
  - **Import**: Browse to a comma-separated file that contains a list of servers in the format: description, IP address or FQDN, Default server. Choose **OK** to import these servers into the **Servers** list.
  - **Export**: Exports the list of servers to a comma-separated-values (csv) file

- **Connection type**: Select the VPN connection type from the following list of vendors:

  - **Pulse Secure**
  - **F5 Edge Client**
  - **SonicWALL Mobile Connect**
  - **Check Point Capsule VPN**
  - **Citrix**
  - **Palo Alto Networks GlobalProtect**
  - **Automatic**
  - **IKEv2**
  - **L2TP**
  - **PPTP**

  When you choose a VPN connection type, you may also be asked for the following settings:  
    - **Always On**: Enable to automatically connect to the VPN connection when the following happens: 
      - Users sign into their devices
      - The network on the device changes
      - The screen on the device turns back on after being turned off 

    - **Authentication method**: Select how you want users to authenticate to the VPN server. Using **certificates** provides enhanced capabilities, such as zero-touch experience, on-demand VPN, and per-app VPN.
    - **Remember credentials at each logon**: Choose to cache the authentication credentials.
    - **Custom XML**: Enter any custom XML commands that configure the VPN connection.
    - **EAP Xml**: Enter any EAP XML commands that configure the VPN connection

#### Pulse Secure example

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

#### F5 Edge Client example

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

#### SonicWALL Mobile Connect example
**Login group or domain**: This property can't be set in the VPN profile. Instead, Mobile Connect parses this value when the user name and domain are entered in the `username@domain` or `DOMAIN\username` formats.

Example:

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

#### CheckPoint Mobile VPN example

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

#### Writing custom XML
For more information about writing custom XML commands, see each manufacturer's VPN documentation.

For more information about creating custom EAP XML, see [EAP configuration](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration).

## Apps and Traffic Rules

- **Associate WIP or apps with this VPN**: Enable this setting if you only want some apps to use the VPN connection. Your options:

  - **Associate a WIP with this connection**: Enter a **WIP domain for this connection**
  - **Associate apps with this connection**: You can **Restrict VPN connection to these apps**, and then add **Associated Apps**. The apps you enter automatically use the VPN connection. The type of app determines the app identifier. For a universal app, enter the package family name. For a desktop app, enter the file path of the app.
  >[!IMPORTANT]
  >We recommend that you secure all app lists created for per-app VPNs. If an unauthorized user changes this list, and you import it into the per-app VPN app list, then you potentially authorize VPN access to apps that shouldn't have access. One way you can secure app lists is using an access control list (ACL).

- **Network traffic rules for this VPN connection**: Select which protocols, and which local & remote port and address ranges, are enabled for the VPN connection. If you don't create a network traffic rule, then all protocols, ports, and address ranges are enabled. After you create a rule, the VPN connection uses only the protocols, ports, and address ranges that you enter in that rule.

## Conditional Access

- **Conditional access for this VPN connection**: Enables device compliance flow from the client. When enabled, the VPN client attempts to communicate with Azure Active Directory (AD) to get a certificate to use for authentication. The VPN should be set up to use certificate authentication, and the VPN server must trust the server returned by Azure AD.

- **Single sign-on (SSO) with alternate certificate**: For device compliance, use a certificate different from the VPN authentication certificate for Kerberos authentication. Enter the certificate with the following settings:

  - **Name**: Name for extended key usage (EKU)
  - **Object Identifier**: Object identifier for EKU
  - **Issuer hash**: Thumbprint for SSO certificate

## DNS Settings

**Domain and servers for this VPN connection**: Add domain and DNS server for the VPN to use. You can choose which DNS servers the VPN connection uses after the connection is established. For each server, enter:
- **Domain**
- **DNS Server**
- **Proxy**

## Proxy settings

- **Automatic configuration script**: Use a file to configure the proxy server. Enter the **Proxy server URL**, such as `http://proxy.contoso.com`, that contains the configuration file.
- **Address**: Enter the proxy server address, such as an IP address or `vpn.contoso.com`
- **Port number**: Enter the TCP port number used by your proxy server
- **Bypass proxy for local addresses**: If you don't want to use a proxy server for local addresses, then choose Enable. This setting applies if your VPN server requires a proxy server for the connection.

## Split Tunneling

- **Split tunneling**: **Enable** or **Disable** to let devices decide which connection to use depending on the traffic. For example, a user in a hotel uses the VPN connection to access work files, but uses the hotel's standard network for regular web browsing.
- **Split tunneling routes for this VPN connection**: Add optional routes for third-party VPN providers. Enter a destination prefix, and a prefix size for each connection.
