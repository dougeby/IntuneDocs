---
# required metadata

title: VPN connections | Microsoft Intune
description: Use VPN profiles to deploy VPN settings to users and devices in your organization.
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: abc57093-7351-408f-9f41-a30877f96f73

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: karanda
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# VPN connections in Microsoft Intune
 Virtual Private Networks (VPN) let you give your users secure remote access to your company network. Remote users can work as if their device is physically connected to the network. Devices use a VPN connection profile to initiate a connection with the VPN server. Use **VPN profiles** in Microsoft Intune to deploy VPN settings to users and devices in your organization. By deploying these settings, you minimize the end-user effort required to connect to resources on the company network.

For example, you want to provision all iOS devices with the settings required to connect to a file share on the corporate network. You create a VPN profile containing the settings necessary to connect to the corporate network and then deploy this profile to all users with iOS devices. The users will see the VPN connection in the list of available networks and can connect with the minimum of effort.

You can configure the following device types with VPN profiles:

* Devices that run Android 4 and later
* Devices that run iOS 7.1 and later
* Devices that run Mac OS X 10.9 and later
* Enrolled devices that run Windows 8.1 and later
* Devices that run Windows Phone 8.1 and later
* Devices that run Windows 10 desktop and mobile.

The VPN profile configuration options will differ depending on the device type you select.

## VPN connection types

Intune supports creating VPN profiles that use the following connection types:




Connection type |iOS and Mac OS X  |Android|Windows 8.1|Windows RT|Windows RT 8.1|Windows Phone 8.1|Windows 10 Desktop and Mobile |
----------------|------------------|-------|-----------|----------|--------------|-----------------|----------------------|
Cisco AnyConnect|Yes |Yes   |No    |     No    |No  |No    | Yes, (OMA-URI, Mobile only)|     
Pulse Secure|Yes  |Yes |Yes   |No  |Yes  |Yes| Yes|        
F5 Edge Client|Yes |Yes |Yes |No  |Yes  |   Yes |  Yes|   
Dell SonicWALL Mobile Connect|Yes |Yes |Yes |No  |Yes |Yes |Yes|         
CheckPoint Mobile VPN|Yes |Yes |Yes |Yes |Yes|Yes|Yes|
Microsoft SSL (SSTP)|No |No |No |No |No|No|VPNv1 OMA-URI*|
Microsoft Automatic|No |No |No |No |No|Yes (OMA-URI)|Yes|
IKEv2|iOS Custom Profile|No |No |No |No|Yes (OMA-URI)|Yes|
PPTP|iOS Custom Profile|No |No |No |No|No|Yes|
L2TP|iOS Custom Profile|No |No |No |No|Yes (OMA-URI)|Yes|

\* Without additional settings that are otherwise available for Windows 10.

> [!IMPORTANT] Before you can use VPN profiles deployed to a device, you must install the applicable VPN app for the profile. You can use the information in the [Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md) topic to help you deploy the applicable app using Intune.  

 Learn how to  create custom VPN profiles using URI settings in [Custom configurations for VPN profiles](custom-configurations-for-vpn-profiles.md).     

## How VPN profiles are secured

VPN profiles can use a number of different connection types and protocols from different manufacturers. These connections are typically secured using one of two methods:

### Certificates

When you create the VPN profile, you choose a SCEP or .PFX certificate profile that you have previously created in Intune.

This is known as the identity certificate and is used to authenticate against a trusted certificate profile (or a root certificate) you created to establish that the user’s device is allowed to connect. The trusted certificate is deployed to the computer that authenticates the VPN connection, typically, the VPN server.

For more information about how to create and use certificate profiles in Intune, see [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md).

### Username and password

The user authenticates to the VPN server by providing their username and password.

## Create a VPN profile

1. In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy > Add Policy**.
2. Select a template for the new policy by expanding the relevant device type, then choose the VPN profile for that device:
	* **VPN Profile (Android 4 and later)**
	* **VPN Profile (iOS 7.1 and later)**
	* **VPN Profile (Mac OS X 10.9 and later)**
	* **VPN Profile (Windows 8.1 and later)**
	* **VPN Profile (Windows Phone 8.1 and later)**
	* **VPN Profile (Windows 10 Desktop and Mobile and later)**

	You can only create and deploy a custom VPN profile policy. Recommended settings are not available.

3. Use the following table to help you configure the VPN profile settings:

Setting name  |More information  
---------|---------
**Name**     |Enter a unique name for the VPN profile to help you identify it in the Intune console.         
**Description**     |Provide a description that gives an overview of the VPN profile and other relevant information that helps you to locate it.         
**VPN connection name (displayed to users)**     |Specify a name for the VPN profile. This is the name that users will see in the list of available VPN connections on their devices.         
**Connection type**     |  Select one of the following connection types to use in the VPN profile: **Cisco AnyConnect** (not available for Windows 8.1 or Windows Phone 8.1), **Pulse Secure**, **F5 Edge Client**, **Dell SonicWALL Mobile Connect**, **CheckPoint Mobile VPN**
**VPN server description**     | Specify a description for the VPN server that devices will connect to. **Example:** Contoso VPN Server. When the connection type is **F5 Edge Client**, use the **Server list** field to specify a list of server descriptions and IP addresses.
**Server IP address or FQDN**    |Provide the IP address or fully qualified domain name of the VPN server that devices will connect to. **Examples:** 192.168.1.1, vpn.contoso.com.  When the connection type is **F5 Edge Client**, use the **Server list** field to specify a list of server descriptions and IP addresses.         |         
**Server list**     |Choose **Add** to add a new VPN server to use for the VPN connection. You can also specify which server is to be the default server for the connection. This option is displayed only when the connection type is **F5 Edge Client**.         
**Send all network traffic through the VPN connection**     |If you select this option, all network traffic is sent through the VPN connection. If you do not select this option, the client will dynamically negotiate the routes for split tunneling upon connecting to the 3rd party VPN server. Only connections to the company network are sent over a VPN tunnel. VPN tunneling is not used when you connect to resources on the Internet.
**Authentication method**| Select the authentication method used by the VPN connection: **Certificates** or **Username and Password**. (Username and Password is not available when the connection type is Cisco AnyConnect.) The **Authentication method** option is not available for Windows 8.1.
**Remember the user credentials at each logon**|Select this option to ensure that the user credentials are remembered so that the user does not have to enter credentials each time a connection is established.
**Select a client certificate for client authentication (Identity Certificate)**|Select the client SCEP certificate that you previously created that will be used to authenticate the VPN connection. For more information about how to use certificate profiles in Intune, see [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md). This option is displayed only when the authentication method is **Certificates**.
**Role**| Specify the name of the user role that has access to this connection. A user role defines personal settings, options, and enables or disables certain access features. This option is displayed only when the connection type is **Pulse Secure**.
**Realm**|Specify the name of the authentication realm that you want to use. An authentication realm is a grouping of authentication resources that is used by the Pulse Secure connection type. This option is displayed only when the connection type is **Pulse Secure**.
**Login group or domain**|Specify the name of the login group or domain that you want to connect to. This option is displayed only when the connection type is **Dell SonicWALL Mobile Connect**.
**Fingerprint**|Specify a string, for example "Contoso Fingerprint Code" that will be used to verify the VPN server can be trusted. A fingerprint can be: Sent to the client so it knows to trust any server presenting that same fingerprint when connecting. If the device doesn’t already have the fingerprint it will prompt the user to trust the VPN server they are connecting to while showing the fingerprint (the user manually verifies the fingerprint and chooses **trust** to connect). This option is displayed only when the connection type is **CheckPoint Mobile VPN**.
**Per App VPN**|Select this option if you want to associate this VPN connection with an iOS of Mac OS X app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you deploy the software. For more information, see [Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md)
**Automatically detect proxy settings** (iOS, Mac OS X, Windows 8.1 and Windows Phone 8.1 only)|If your VPN server requires a proxy server for the connection, specify whether you would like devices to automatically detect the connection settings. For more information, see your Windows Server documentation.
**Use automatic configuration script** (iOS, Mac OS X, Windows 8.1 and Windows Phone 8.1 only)|If your VPN server requires a proxy server for the connection, specify whether you would like to use an automatic configuration script to define the settings and then specify a URL to the file containing the settings. For more information, see your Windows Server documentation.
**Use proxy server** (iOS, Mac OS X, Windows 8.1 and Windows Phone 8.1 only)|If your VPN server requires a proxy server for the connection, select this option, then specify the address and port number of the proxy server. For more information, see your Windows Server documentation.
**Bypass proxy settings for local addresses** (iOS, Mac OS X, Windows 8.1 and Windows Phone 8.1 only)|If your VPN server requires a proxy server for the connection, select this option if you do not want to use the proxy server for local addresses that you specify. For more information, see your Windows Server documentation.
**Custom XML** (Windows 8.1 and later, and Windows Phone 8.1 and later)|Allows you to specify custom XML commands that configure the VPN connection. Examples. For **Pulse Secure**: &lt;pulse-schema&gt;&lt;isSingleSignOnCredential&gt;true&lt;/isSingleSignOnCredential&gt;&lt;/pulse-schema&gt;. For **CheckPoint Mobile VPN**: &lt;CheckPointVPN port="443" name="CheckPointSelfhost" sso="true"  debug="3" /&gt;. For **Dell SonicWALL Mobile Connect**: &lt;MobileConnect&gt;&lt;Compression&gt;false&lt;/Compression&gt;&lt;debugLogging&gt;True&lt;/debugLogging&gt;&lt;packetCapture&gt;False&lt;/packetCapture&gt;&lt;/MobileConnect&gt;. For **F5 Edge Client**: &lt;f5-vpn-conf&gt;&lt;single-sign-on-credential /&gt;&lt;/f5-vpn-conf&gt;. Refer to each manufacturers VPN documentation for more information about how to write custom XML commands.
**DNS Suffix search list** (Windows Phone 8.1 only)|Specify one DNS suffix on each line. Each DNS suffix you specify will be searched when connecting to a website using a short name. For example, specify the DNS suffices **domain1.contoso.com** and **domain2.contoso.com**, visit the URL **http://mywebsite**, and the URLs **http://mywebsite.domain1.contoso.com** and **http://mywebsite.domain2.contoso.com** will be searched.
**Bypass VPN when connected to company Wi-Fi network** (Windows Phone 8.1 only)|Specifies that the VPN connection will not be used when the device is connected to the company Wi-Fi network.
**Bypass VPN when connected to home Wi-Fi network** (Windows Phone 8.1 only)|Specifies that the VPN connection will not be used when the device is connected to a home Wi-Fi network.

The following additional settings are available for Windows 10 Desktop and Mobile devices

Setting name  |More information  
---------|---------
**Network traffic rules**| Set which protocols, local and remote port and address ranges will be enabled for the VPN connection. If you do not create a network traffic rule, all protocols, ports and address ranges are enabled. Once you create a rule, only the protocols, ports and address ranges that you specify in that rule or in additional rules will be used by the VPN connection.
**Routes**|Which routes will use the VPN connection.
**DNS servers**| Which DNS servers are used by the VPN connection once the connection has been established.         
**Associated apps**     | You can provide a list of apps that will automatically use the VPN connection. The type of app will determine the app identifier. For universal apps – provide the Package Family Name, and for desktop apps – provide the file path of the app.          


> [!IMPORTANT] We recommend that you secure all lists of apps that you compile for use in configuration of per-app VPN. If an unauthorized user modifies your list and you import it into the per-app VPN app list, you will potentially authorize VPN access to apps that should not have access. One way you can secure app lists is by using an access control list (ACL).

Here's an example of when you might use corporate boundaries settings. If you want to enable VPN only for remote desktop, you would create a network traffic rule that allows traffic for protocol number 27 on external port 3996. No other traffic will use the VPN.

Defining routes in corporate boundaries is useful when your VPN connection type does not allow you to define how traffic is handled in split tunneling. In that case, use **Routes** to list the routes that will use the VPN.

You can restrict Windows 10 device VPN usage to specific apps by creating a custom OMA-URI setting.

The new policy displays in the **Configuration Policies** node of the **Policy** workspace.

## Deploy the policy

1.  In the **Policy** workspace, select the policy you want to deploy, then choose **Manage Deployment**.

2.  In the **Manage Deployment** dialog box:

    -   **To deploy the policy** - Select one or more groups to which you want to deploy the policy, then choose **Add** &gt; **OK**.

    -   **To close the dialog box without deploying it** - Choose **Cancel**.


After successful deployment, users will see the VPN connection name you specified in the list of VPN connections on their device.

A status summary and alerts on the **Overview** page of the **Policy** workspace identify issues with the policy that require your attention. Additionally, a status summary appears in the Dashboard workspace.

### See also
[Custom configurations for VPN profiles](Custom-configurations-for-VPN-profiles.md)
[Per-app VPN for Android Pulse Secure](per-app-vpn-for-android-pulse-secure.md)
