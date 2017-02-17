---
# required metadata

title: How to create custom VPN profiles with Microsoft Intune | Microsoft Docs
description: Use custom configurations to create VPN profiles in Intune.
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: karanda
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to create custom VPN profiles in Microsoft Intune

## Create a custom configuration
You can use Intune custom configuration polices to create VPN profiles for:

* Devices that run Android 4 and later
* Enrolled devices that run Windows 8.1 and later
* Devices that run Windows Phone 8.1 and later
* Enrolled devices that run Windows 10 desktop 
* Devices that run Windows 10 Mobile

This type of policy can be useful when the standard Intune VPN policies do not contain the settings you want to use.

## To create a custom configuration policy:

1. Sign into the Azure portal.
2. Choose **More Services** > **Other** > **Intune**.
3. On the **Intune** blade, choose **Configure devices**.
4. On the **Device Configuration** blade, choose **Manage** > **Profiles**.
5. On the profiles blade, choose **Create Profile**.
6. On the **Create Profile** blade, enter a **Name** and **Description** for the VPN profile.
7. From the **Platform** drop-down list, select the device platform to which you want to apply VPN settings. Currently, you can choose one of the following platforms for custom device settings:
	- **Android**
	- **iOS** (configured using a file you exported from Apple Configurator).
	- **macOS** (configured using a file you exported from Apple Configurator).
	- **Windows Phone 8.1**
	- **Windows 10 and later**
6. From the **Profile** type drop-down list, choose **Custom**.
7. On the **Custom OMA-URI Settings** blade, for each URI setting you want to specify, choose **Add**, provide the requested information, then choose **OK**. Here's an example:

   ![VPN profile custom configuration dialog box](./media/Intune_Add_VPN_URI.png)

4.  After you've entered all of URI settings you need, choose **OK**, and then, on the **Create Profile** blade, choose **Create**.

The profile will be created and appears on the profiles list blade.
If you want to go ahead and assign this profile to groups, see [How to assign device profiles](how-to-assign-device-profiles.md).

## Example URI settings

These settings can be used to create a custom configuration for a VPN in a fictitious company called Contoso.
For full details about all the settings you can use, see [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx).

Native Contoso VPN (IKEv2):
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

vpn.contoso.com
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

Ikev2
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

SplitTunnel
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

Eap
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration
&lt;EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;EapMethod&gt;&lt;Type xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;13&lt;/Type&gt;&lt;VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorId&gt;&lt;VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorType&gt;&lt;AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/AuthorId&gt;&lt;/EapMethod&gt;&lt;Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"&gt;&lt;Type&gt;13&lt;/Type&gt;&lt;EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"&gt;&lt;CredentialsSource&gt;&lt;CertificateStore&gt;&lt;SimpleCertSelection&gt;true&lt;/SimpleCertSelection&gt;&lt;/CertificateStore&gt;&lt;/CredentialsSource&gt;&lt;ServerValidation&gt;&lt;DisableUserPromptForServerValidation&gt;false&lt;/DisableUserPromptForServerValidation&gt;&lt;ServerNames&gt;&lt;/ServerNames&gt;&lt;/ServerValidation&gt;&lt;DifferentUsername&gt;false&lt;/DifferentUsername&gt;&lt;PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/PerformServerValidation&gt;&lt;AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/AcceptServerName&gt;&lt;/EapType&gt;&lt;/Eap&gt;&lt;/Config&gt;&lt;/EapHostConfig&gt;

**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**
True

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**
1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**
10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**
8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**
true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**
%PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

For any questions about how these settings should be used or more details about what they do, customers should refer to the configuration service provider (CSP) documentation:
https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776(v=vs.85).aspx.

## URI settings for Android per-app VPN on PulseSecure
### CUSTOM URI FOR PACKAGE LIST
-  Data type = String
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/Name/PackageList
-  Value = Delimiter separated package list.
   - Delimiters:  semicolon (;), colon (:), comma (,), Pipe (|)

Examples:
- com.android.chrome
- com.android.chrome;com.android.browser

### CUSTOM URI FOR MODE (OPTIONAL)
- Data Type = String
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode

> Notes
> - Use the same *name* that you assigned to the custom profile
> - Possible values: *GLOBAL*, *WHITELIST*, *BLACKLIST*
> - Defaults to *GLOBAL* if no PackageList is provided (backward compatibility with system-wide profiles)
> - Defaults to *WHITELIST* if a PackageList is provided



