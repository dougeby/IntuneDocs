---
# required metadata

title: VPN settings for iOS devices in Microsoft Intune - Azure | Microsoft Docs
description: View the available virtual private network (VPN) configuration settings, including the connection details, authentication methods, and split tunneling in the base settings; the custom VPN settings with the identifier, and the key and value pairs; the per-app VPN settings that include Safari URLs, and on-demand VPNs with SSIDs or DNS search domains; and the proxy settings to include a configuration script, IP or FQDN address, and TCP port in Microsoft Intune on devices running iOS.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/28/2018
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

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

This article shows you the Intune settings you can use to configure VPN connections on devices running iOS.

Depending on the settings you choose, not all values in the following list are configurable.

## Base VPN settings
The actual settings you see from the list below are determined by the VPN connection type you select.  
- **Connection name**: End users see this name when they browse their device for a list of available VPN connections.
- **Custom domain name** (Zscaler only): Prepopulate the Zscaler app's sign-in field with the domain your users belong to. For example, if a username is **Joe@contoso.net**, the domain **contoso.net** would statically appear in the field when the app opens. If you do not type in a domain name, the domain portion of the UPN in Azure Active Directory will be used.
- **IP address or FQDN**: The IP address or fully qualified domain name (FQDN) of the VPN server that devices connect with. For example, enter **192.168.1.1** or **vpn.contoso.com**. 
- **Organization's cloud name** (Zscaler only): Type in the name of the cloud where your organization is provisioned. Look in the URL you use to sign in to Zscaler to find the name.  
- **Authentication method**: Choose how devices authenticate to the VPN server. 
  - **Certificates**: Under **Authentication certificate**, select an existing SCEP or PKCS certificate profile to authenticate the connection. [Configure certificates](certificates-configure.md) provides some guidance about certificate profiles.
  - **Username and password**: End users must enter a username and password to sign in to the VPN server.  

    > [!NOTE]
    > If username and password are used as the authentication method for Cisco IPsec VPN, they must deliver the SharedSecret through a custom Apple Configurator profile.
  
- **Connection type**: Select the VPN connection type from the following list of vendors:
  - **Check Point Capsule VPN**
  - **Cisco Legacy AnyConnect**: Applicable to [Cisco Legacy AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) app version 4.0.5x and earlier.
  - **Cisco AnyConnect**: Applicable to [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) app version 4.0.7x and later.
  - **SonicWall Mobile Connect**
  - **F5 Access Legacy**: Applicable to F5 Access app version 2.1 and earlier.
  - **F5 Access**: Applicable to F5 Access app version 3.0 and later.
  - **Palo Alto Networks GlobalProtect (Legacy)**: Applicable to Palo Alto Networks GlobalProtect app version 4.1 and earlier.
  - **Palo Alto Networks GlobalProtect**: Applicable to Palo Alto Networks GlobalProtect app version 5.0 and later.
  - **Pulse Secure**
  - **Cisco (IPSec)**
  - **Citrix VPN**
  - **Citrix SSO**
  - **Zscaler**: Requires you to integrate Zscaler Private Access (ZPA) with your Azure Active Directory account. For detailed steps, see the [Zscaler documentation](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad#Azure_UserSSO). 
  - **Custom VPN**    

    > [!NOTE]
    > Cisco, Citrix, F5, and Palo Alto have announced that their legacy clients will not work on the upcoming release of iOS 12. You should migrate to the new apps as soon as possible. For more information, see the [Microsoft Intune Support Team Blog](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409).

* **Excluded URLs** (Zscaler only): When connected to the Zscaler VPN, the listed URLs are accessible outside the Zscaler cloud. 

- **Split tunneling**: **Enable** or **Disable** to let devices decide which connection to use, depending on the traffic. For example, a user in a hotel uses the VPN connection to access work files, but uses the hotel's standard network for regular web browsing.   

## Custom VPN settings

If you selected **Custom VPN** as the connection type, configure the following settings. These settings are also visible for Zscaler and Citrix connections.

- **VPN identifier**: An identifier for the VPN app you're using, and is supplied by your VPN provider.
- **Enter key/value pairs for your organization's custom VPN attributes**: Add or import **Keys** and **Values** that customize your VPN connection. Again, these values are typically supplied by your VPN provider.

## Automatic VPN settings

- **Per-app VPN**: Choosing this option enables per-app VPN, which allows the VPN connection to be triggered automatically when certain apps are opened. In addition to choosing this option, you also need to associate the apps with this VPN profile. See the [instructions for setting up per-app VPN for iOS](vpn-setting-configure-per-app.md) for more details. 
  - The **Provider Type** setting is only available for Pulse Secure and Custom VPN.
  - When using iOS **per-app VPN** profiles with Pulse Secure or a Custom VPN, you can choose to use app-layer tunneling (app-proxy) or packet-level tunneling (packet-tunnel). Set the **ProviderType** value to **app-proxy** for app-layer tunneling or **packet-tunnel** for packet-layer tunneling.If you are not sure which value to use, consult your VPN provider's documentation. 
  - **Safari URLs that will trigger this VPN**: Select to add one or more web site URLs. When these URLs are visited using the Safari browser on the device, the VPN connection is automatically established.

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
If you're using a proxy, configure the following settings. Proxy settings are not available for Zscaler VPN connections.  

- **Automatic configuration script**: Use a file to configure the proxy server. Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) that contains the configuration file.
- **Address**: Enter the IP address of fully qualified host name of the proxy server.
- **Port number**: Enter the port number associated with the proxy server.

## Next step
[Create VPN profiles in Intune](vpn-settings-configure.md)  
