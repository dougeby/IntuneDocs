---
# required metadata

title: Intune VPN settings for iOS devices
titleSuffix: "Intune on Azure"
description: Learn about the Intune settings you can use to configure VPN connections on iOS devices."
keywords:
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
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

Depending on the settings you choose, not all values in the list below will be configurable.

## Base VPN settings


**Connection name** - Enter a name for this connection. End users will see this name when they browse their device for the list of available VPN connections.
- **IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to. Examples: **192.168.1.1**, **vpn.contoso.com**.
- **Authentication method** - Choose how devices will authenticate to the VPN server from:
	- **Certificates** - Under **Authentication certificate**, Choose a SCEP or PKCS certificate profile you previously created to authenticate the connection. For more details about certificate profiles, see [How to configure certificates](certificates-configure.md).
	- **Username and password** - End users must supply a username and password to log into the VPN server.
- **Connection type** - Select the VPN connection type from the following list of vendors:
	- **Check Point Capsule VPN**
	- **Cisco AnyConnect**
	- **Dell SonicWALL Mobile Connect**
	- **F5 Edge Client**
	- **Pulse Secure**
	- **Cisco (IPSec)**
	- **Citrix**
	- **Custom VPN**
- **Split tunneling** - **Enable** or **Disable** this option which lets devices decide which connection to use depending on the traffic. For example, a user in a hotel will use the VPN connection to access work files, but use the hotel's standard network for regular web browsing.


## Custom VPN settings

If you selected **Custom VPN** as the connection type, configure these further settings:

- **VPN identifier** This is an identifier for the VPN app you are using, and is supplied by your VPN provider.
- **Enter key and value pairs for the custom VPN attributes** Add or import **Keys** and **Values** that customize your VPN connection. Again, these values are typically supplied by your VPN provider.

## Apps (per-app VPN) settings

- **Per-app VPN** - Enable this option if you want to URLs that will enable the VPN connection when they are visited from the Safari browser. To configure this, you must have selected **Certificates** as the authentication method in the base VPN settings.
- **URLs that will enable the VPN connection while using the Safari browser** - Click add to add one or more web site URLs. When these URL's are visited, the VPN connection will be enabled.

- **On-demand rules** - This lets you configure conditional rules that control when the VPN connection is initiated. For example, you could create a condition where the VPN connection is only used when a device is not connected to one of your company Wi-Fi networks. Alternatively, you could create a condition where, if a device cannot access a DNS search domain you specify, then the VPN connection is not initiated.

	- **SSIDs or DNS search domains** - Select whether this condition will use wireless network **SSIDs**, or **DNS search domains**. Choose Add to configure one or more SSIDs or search domains.
	- **URL string probe** - Optionally, provide a URL that the rule uses as a test. If the device on which this profile is installed is able to access this URL without redirection, the VPN connection will be initiated and the device will connect to the target URL. The user will not see the URL string probe site. An example of a URL string probe is the address of an auditing Web server that checks device compliance before connecting the VPN. Another possibility is that the URL tests the ability of the VPN to connect to a site, before connecting the device to the target URL through the VPN.
	- **Domain action** - Choose one of the following:
		- Connect if needed - 
		- Never connect - 
	- **Action** - Choose one of the following:
		- Connect - 
		- Evaluate connection - 
		- Ignore - 
		- Disconnect - 


## Proxy settings

- **Automatic configuration script** - Use a file to configure the proxy server. Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.
- **Address** - Enter the proxy server address (as an IP address).
- **Port number** - Enter the port number associated with the proxy server.

<!--
## Set Up Per-App VPN using Microsoft Intune for iOS

With the release of iOS 7, Apple introduced the Per-App VPN feature which caters to both IT Professional and end user experiences. With this feature, IT Professionals can specify which managed apps can use VPN on an Intune managed iOS device. It also makes the connection experience seamless for the user by abstracting the steps taken to connect to a VPN server when accessing corporate documents. This blog post will teach you how to set up Per-App VPN for your enterprise using Microsoft Intune (cloud only) and deliver that awesome experience to your users.

### On the VPN Server

 - Make sure you’re using Certificate based Authentication.
 - Make sure you add the Certificate Authority (CA) that issues certificates for authentication to mobile devices.

If the Certificate Authority presented by the device matches one of the CAs in the Trusted CA list of the VPN server, then the VPN server successfully authenticates the device.
   
### In the Intune Admin Console

#### Provision a Trusted Certificate Profile

This is the Root Certificate that is issued by the Certificate Authority to the VPN server. To prove its identity the VPN server presents this Certificate Authority which must be accepted automatically by the device. To ensure automatic approval of the Certificate Authority you must provision a Trusted Certificate Profile that contains the Root Certificate issued by the Certificate Authority. In the following screenshots the “MicrosoftRootCA.cer” is the Root Certificate.

The Certificate Authority (CA) that provisions the identity certificate to the VPN server must be trusted by the iOS device. To do so, create a Trusted Certificate Profile. Go to your VPN’s admin console and export the certificate it presents you to trust its identity. Import that certificate here and deploy the Trusted Certificate Profile to all iOS devices you expect to run Per-App VPN. This profile instructs the iOS device to automatically trust the CA that the VPN server presents.
 
Once you deploy this profile along with the VPN profile to your iOS device, test out the trust establishment process:

1. Install a 3rd party VPN app to connect to specific VPN (e.g., Junos Pulse app to connect to Juniper VPN)
2. Open the Junos Pulse app and create a VPN connection that will connect to your Juniper VPN host
3. If you have successfully completed the steps mentioned above, you should be able to connect to the Juniper VPN instantly without any notifications to trust the VPN server. Note: this is crucial because it helps establish automatic trust with the VPN server and puts you on the right path for creating a zero-touch experience for per-app VPN connections. 

#### Provision a SCEP Cert Profile

Once you have established automatic trust with the VPN server, you need to provide credentials to the iOS device that can be utilized by the VPN client and not prompt the user for any authentication details. To do so, create and deploy a SCEP Profile.
 
Once you have deployed the SCEP profile, make sure you take a note of the CA that provisions this certificate.

1. If the SCEP CA is different from the VPN’s CA – you need to add the SCEP CA to a list of trusted CA’s in your VPN Server
2. If not, you do not need to do anything.

#### Provision a Per-App VPN Profile

Now that you have fulfilled both phases of the zero-touch experience, create and deploy a VPN profile for iOS devices. A couple of points to keep in mind here:
1. Select **Certificates** as the authentication method
2. Select the SCEP certificate you created earlier – this will ensure that user credentials will get tagged along with this VPN profile
3. Check the **Per App VPN** checkbox. Your VPN profile should look similar to screenshot below:
 
### Associate an App with the VPN Profile

Once you create a Per-App VPN profile, navigate to the **Software** node and [add a managed app](http://technet.microsoft.com/library/dn646972.aspx?WT.mc_id=Blog_Intune_General_PCIT). Select the app and click on **Manage Deployments**. Then click on the VPN Profile tab and you will notice the VPN you just created will appear in the dropdown for VPN Policy.

Select the Per-App VPN Profile and finish the wizard. This will ensure that the managed app (Bing for iPad in screenshot) will be associated with [Test] iOS Per-App VPN when this policy is deployed to iOS device users. Ensure you deploy this app to the same group of users that have been targeted for the Per-App VPN profile you created earlier. 

### On the iOS Device

  -  Make sure you’re running iOS 7 or later
  -  Make sure you deploy ALL of the above mentioned policies to the SAME group of users. Failure to do so will most definitely break the Per-App VPN experience  
  -  Must have the appropriate 3rd party app installed:
o	Juniper
o	Checkpoint
o	F5
o	SonicWall
  -  Make sure you have a zero-touch experience:
    -  User taps on the 3rd party VPN app
    -  Taps on **Connect**
    -  VPN successfully connects without any extra prompts.
      -  User must not be asked to trust the VPN server (i.e., User must not see the Dynamic Trust dialog box)
      -  User must not enter any credentials
      -  User must be connected to VPN upon tapping the connect button

### Troubleshooting

Overall the entire Per-App VPN experience on the iOS device is invisible to the user. While it creates a great user experience, it also makes it difficult to troubleshoot any issues.

If you’d like to take a deeper look into the logs/events created by the iOS device, connect your iOS device to a PC and open IPCU (iPhone Configuration Utility). You can install it from [here](http://www.microsoft.com/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1). Once you connect your iOS device, open the console on IPCU and voila – you should get a live log from the device.

-->