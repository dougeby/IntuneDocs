---
# required metadata

title: Custom configurations for Microsoft Intune VPN profiles 
description: Use custom configurations to create VPN profiles in Intune.
keywords:
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: karanda
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Custom configurations for Microsoft Intune VPN profiles

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## Create a custom configuration
You can use Intune custom configuration polices to create VPN profiles for:

* Devices that run Android 4 and later
* Android for Work devices
* Enrolled devices that run Windows 8.1 and later
* Devices that run Windows Phone 8.1 and later
* Enrolled devices that run Windows 10 desktop
* Device that run Windows 10 Mobile

This type of policy can be useful when the standard Intune VPN policies do not contain the settings you want to use.

## To create a custom configuration policy:

   1. In the [Intune admin console](https://manage.microsoft.com), choose **Policy** > **Add Policy** > *Expand platform* > **Custom configuration** > **Create Policy**.
   2. Enter a name for the policy.
   3. For each URI setting you want to specify, choose **Add**, and provide the requested information. Here's an example:

   ![VPN profile custom configuration dialog box](./media/Intune_Add_VPN_URI.png)

   4.  After you've entered all of URI settings, choose **Save policy**, and then deploy the policy.

Then, [deploy the policy](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy) as normal.

## Example URI settings

These settings can be used to create a custom configuration for a VPN in a fictitious company called Contoso.
For full details about all the settings you can use, see [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776.aspx).

**Native Contoso VPN (IKEv2):**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

**vpn.contoso.com**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

**Ikev2<br />**
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

**SplitTunnel**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

**Eap**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration
``` xml
<EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
   <EapMethod>
      <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type>
      <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId>
      <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType>
      <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId>
   </EapMethod>
   <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
      <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1">
         <Type>13</Type>
         <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1">
            <CredentialsSource>
               <CertificateStore>
                  <SimpleCertSelection>true</SimpleCertSelection>
               </CertificateStore>
            </CredentialsSource>
            <ServerValidation>
               <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation>
               <ServerNames></ServerNames>
            </ServerValidation>
            <DifferentUsername>false</DifferentUsername>
            <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </PerformServerValidation>
            <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </AcceptServerName>
         </EapType>
      </Eap>
   </Config>
</EapHostConfig>
```
**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**<br />
True

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**<br />
1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**<br />
10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**<br />
8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**<br />
true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**<br />
%PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

For any questions about how these settings should be used or more details about what they do, customers should refer to the [configuration service provider (CSP) documentation](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx).

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


### See also
[VPN connections in Microsoft Intune](vpn-connections-in-microsoft-intune.md)
