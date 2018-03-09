---
# required metadata

title: View the VPN settings in Microsoft Intune - Azure | Microsoft Docs
description: Learn and read about the available VPN settings in Microsoft Intune, what they are used for, and what they do, including traffic rules, conditional access, and DNS and proxy settings for Windows 10 devices and Windows Holographic for Business devices.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/8/2018
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

# Read about the VPN settings in Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

You can configure VPN connections using Intune. This article describes these settings, the traffic rules, conditional access, and DNS & proxy settings.

These settings apply to:

- Devices running Windows 10
- Devices running Windows Holographic for Business

Depending on the settings you choose, not all values may be configurable.

## Base VPN settings

- **Connection name**: Enter a name for this connection. End users see this name when they browse their device for the list of available VPN connections.
- **Servers**: Add one or more VPN servers that devices connect to.
  - **Add**: Opens **Add Row** where you enter the following information:
    - **Description**: Enter a descriptive name for the server, such as **Contoso VPN server**
    - **IP address or FQDN**: Enter the IP address or fully qualified domain name of the VPN server that devices connect to, such as **192.168.1.1** or **vpn.contoso.com**
    - **Default server**: Enables this server as the default server that devices use to establish the connection. Set only one server as the default.
  - **Import**: Browse to a comma-separated file that contains a list of servers in the format: description, IP address or FQDN, Default server. Choose **OK** to import these severs into the **Servers** list.
  - **Export**: Exports the list of servers to a comma-separated-values (csv) file

**Connection type**: Select the VPN connection type from the following list of vendors:

- **Automatic**
- **Check Point Capsule VPN**
- **Citrix VPN**
- **SonicWALL Mobile Connect**
- **F5 Edge Client**
- **IKEv2**
- **L2TP**
- **PPTP**
- **Pulse Secure**

**Login group or domain** (SonicWALL Mobile Connect only): This property can't be set in the VPN profile. Instead, Mobile Connect parses this value when the user name and domain are entered in the `username@domain` or `DOMAIN\username` formats.

**Custom XML**/**EAP XML**: Enter any custom XML commands that configure the VPN connection.

**Example for Pulse Secure:**

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**Example for CheckPoint Mobile VPN:**

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Example for SonicWALL Mobile Connect:**

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**Example for F5 Edge Client:**

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

For more information about writing custom XML commands, see each manufacturer's VPN documentation.

For more information about creating custom EAP XML, see [EAP configuration](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration).

**Split tunneling**: **Enable** or **Disable** to let devices decide which connection to use depending on the traffic. For example, a user in a hotel uses the VPN connection to access work files, but uses the hotel's standard network for regular web browsing.
- **Split tunneling routes for this VPN connection**: Add optional routes for third-party VPN providers. Enter a destination prefix, and a prefix size for each.

## Apps and Traffic Rules

**Restrict VPN connection to these apps**: Enable this setting if you only want some apps to use the VPN connection.
**Associated Apps**: Enter a list of apps that automatically use the VPN connection. The type of app determines the app identifier. For a universal app, enter the package family name. For a desktop app, enter the file path of the app.

>[!IMPORTANT]
>We recommend that you secure all app lists created for per-app VPNs. If an unauthorized user changes this list, and you import it into the per-app VPN app list, then you potentially authorize VPN access to apps that shouldn't have access. One way you can secure app lists is using an access control list (ACL).

**Network traffic rules for this VPN connection**: Select which protocols, and which local & remote port and address ranges, are enabled for the VPN connection. If you don't create a network traffic rule, then all protocols, ports, and address ranges are enabled. After you create a rule, the VPN connection uses only the protocols, ports, and address ranges that you enter in that rule.

## Conditional Access

**Conditional access for this VPN connection**: Enables device compliance flow from the client. When enabled, the VPN client attempts to communicate with Azure Active Directory to get a certificate to use for authentication. The VPN should be set up to use certificate authentication, and the VPN server must trust the server returned by Azure Active Directory.

**Single sign-on (SSO) with alternate certificate**: For device compliance, use a certificate different from the VPN authentication certificate for Kerberos authentication. Enter the certificate with the following settings:

- **Extended key usage**: Name for extended key usage (EKU)
- **Object Identifier**: Object identifier for EKU
- **Issuer hash**: Thumbprint for SSO certificate

## DNS Settings

**DNS names and servers for this VPN connection**: Select which DNS servers the VPN connection use after the connection is established.
For each server, enter:
- **DNS Name**
- **DNS Server**
- **Proxy**

## Proxy settings

- **Automatically detect proxy settings**: If your VPN server requires a proxy server for the connection, choose if you want devices to automatically detect the connection settings.
- **Automatic configuration script**: Use a file to configure the proxy server. Enter the **Proxy server URL**, such as `http://proxy.contoso.com`, that contains the configuration file.
- **Use proxy server**: Enable this option to manually enter the proxy server settings.
  - **Address**: Enter the proxy server address (as an IP address)
  - **Port number**: Enter the port number associated with the proxy server
- **Bypass proxy for local addresses**: If your VPN server requires a proxy server for the connection, then select this setting if you don't want to use the proxy server for local addresses that you enter.
