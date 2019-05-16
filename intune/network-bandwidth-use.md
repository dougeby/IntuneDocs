---
# required metadata

title: Network requirements and bandwidth details for Microsoft Intune
titleSuffix: 
description: Review network configuration requirements and bandwidth details for Intune.
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/17/2019
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
---

# Intune network configuration requirements and bandwidth

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

This guidance helps Intune admins understand the network requirements for the Intune service. You can use this information to understand bandwidth requirements and IP address and port settings needed for proxy settings.

## Average network traffic
This table lists the approximate size and frequency of common content that travels across the network for each client.

> [!NOTE]
> To ensure devices receive the updates and content from Intune, they must periodically connect to the Internet. The time required to receive updates or content can vary, but they should remain continuously connected to the Internet for at least one hour each day.

|Content type|Approximate size|Frequency and details|
|----------------|--------------------|-------------------------|
|Intune client installation<br /><br />**The following requirements are in addition to the Intune client installation**|125 MB|**One time**<br /><br />The size of the client download varies depending on the operating system of the client computer.|
|Client enrollment package|15 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Endpoint Protection agent|65 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Operations Manager agent|11 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Policy agent|3 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Remote Assistance via Microsoft Easy Assist agent|6 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Daily client operations|6 MB|**Daily**<br /><br />The Intune client regularly communicates with the Intune service to check for updates and policies, and to report the client’s status to the service.|
|Endpoint Protection malware definition updates|Varies<br /><br />Typically 40 KB to 2 MB|**Daily**<br /><br />Up to three times a day.|
|Endpoint Protection engine update|5 MB|**Monthly**|
|Software updates|Varies<br /><br />The size depends on the updates you deploy.|**Monthly**<br /><br />Typically, software updates release on the second Tuesday of each month.<br /><br />A newly enrolled or deployed computer can use more network bandwidth while downloading the full set of previously released updates.|
|Service packs|Varies<br /><br />The size varies for each service pack you deploy.|**Varies**<br /><br />Depends on when you deploy service packs.|
|Software distribution|Varies<br /><br />The size depends on the software you deploy.|**Varies**<br /><br />Depends on when you deploy software.|

## Ways to reduce network bandwidth use
You can use one or more of the following methods to reduce network bandwidth use for Intune clients.

### Use a proxy server to cache content requests
A proxy server can cache content to reduce duplicate downloads and reduce network bandwidth from content from the Internet.

A caching proxy server that receives content requests from clients can retrieve that content and cache both web responses and downloads. The server uses cached data to answer subsequent requests from clients.

The following are typical settings to use for a proxy server that caches content for Intune clients.


|          Setting           |           Recommended value           |                                                                                                  Details                                                                                                  |
|----------------------------|---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         Cache size         |             5 GB to 30 GB             | The value varies based on the number of client computers in your network and the configurations you use. To prevent files from being deleted too soon, adjust the size of the cache for your environment. |
| Individual cache file size |                950 MB                 |                                                                     This setting might not be available in all caching proxy servers.                                                                     |
|   Object types to cache    | HTTP<br /><br />HTTPS<br /><br />BITS |                                               Intune packages are CAB files retrieved by Background Intelligent Transfer Service (BITS) download over HTTP.                                               |
> [!NOTE]
> If you use a proxy server to cache content requests, communication is only encrypted between the client and the proxy and from the proxy to Intune. The connection from the client to Intune will not be encrypted end-to-end.

For information about using a proxy server to cache content, see the documentation for your proxy server solution.

### Use Background Intelligent Transfer Service (BITS) on computers
During hours that you configure, you can use BITS on a Windows computer to reduce the network bandwidth. You can configure BITS policy on the **Network bandwidth** page of the Intune Agent policy.

> [!NOTE]
> For MDM management on Windows, only the OS’s management interface for the MobileMSI app type uses BITS to download. AppX/MsiX use their own non-BITS download stack and Win32 apps via the Intune agent use Delivery Optimization rather than BITS.

To learn more about BITS and Windows computers, see [Background Intelligent Transfer Service](http://technet.microsoft.com/library/bb968799.aspx) in the TechNet Library.

### Use BranchCache on computers
Intune clients can use BranchCache to reduce wide area network (WAN) traffic. The following operating systems support BranchCache:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

To use BranchCache, the client computer must have BranchCache enabled, and then be configured for **distributed cache mode**.

When the Intune client is installed on computers, BranchCache and distributed cache mode are enabled by default. However, if Group Policy has disabled BranchCache, Intune doesn't override that policy and BranchCache remains disabled.

If you use BranchCache, work with other administrators in your organization to manage Group Policy and Intune Firewall policy. Ensure they don't deploy policy that disables BranchCache or Firewall exceptions. For more about BranchCache, see [BranchCache Overview](http://technet.microsoft.com/library/hh831696.aspx).

> [!NOTE]
> You can use Microsoft Intune to manage Windows PCs either [as mobile devices with mobile device management (MDM)](windows-enroll.md) or as computers with the Intune software client. Microsoft recommends that customers [use the MDM management solution](windows-enroll.md) whenever possible. When managed this way, BranchCache is not supported. For more information, see [Compare managing Windows PCs as computers or mobile devices](pc-management-comparison.md).

### Delivery Optimization
Delivery Optimization lets you use Intune to reduce bandwidth consumption when your Windows 10 devices download applications and updates. By using a self-organizing distributed cache, downloads can be pulled from traditional servers and alternate sources (like network peers).

To see the full list of Windows 10 versions and content types supported by Delivery Optimization, see the [Delivery Optimization for Windows 10 updates article](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#requirements).

You can [set up Delivery Optimization](delivery-optimization-settings.md) as part of your device configuration profiles.


## Network communication requirements

Enable network communications between the devices you manage and the endpoints required for cloud-based services.

As a cloud-only service, Intune doesn't require on-premises infrastructure such as servers or gateways.

To manage devices behind firewalls and proxy servers, you must enable communication for Intune.

- The proxy server must support both **HTTP (80)** and **HTTPS (443)** because Intune clients use both protocols
- For some tasks (like downloading software updates), Intune requires unauthenticated proxy server access to manage.microsoft.com

You can modify proxy server settings on individual client computers. You can also use Group Policy settings to change settings for all client computers located behind a specified proxy server.


<!--
> [!NOTE] If Windows 8.1 devices haven't cached proxy server credentials, enrollment might fail because the request doesn't prompt for credentials. Enrollment fails without warning as the request wait for a connection. If users might experience this issue, instruct them to open their browser settings and save proxy server settings to enable a connection.   -->

Managed devices require configurations that let **All Users** access services through firewalls.

The following tables list the ports and services that the Intune client accesses:

|**Domains**|**IP address**|
|---------------------|-----------|
|login.microsoftonline.com | More information [Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) |
|portal.manage.microsoft.com<br> m.manage.microsoft.com |52.175.12.209<br>20.188.107.228<br>52.138.193.149<br>51.144.161.187<br>52.160.70.20<br>52.168.54.64 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 40.83.123.72<br>13.76.177.110<br>52.169.9.87<br>52.174.26.23<br>104.40.82.191<br>13.82.96.212|
|fei.msua01.manage.microsoft.com<br>portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com<br>fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>fei.msua04.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.amsua0202.manage.microsoft.com <br>portal.fei.amsua0202.manage.microsoft.com <br>m.fei.amsua0202.manage.microsoft.com<br>fei.amsua0402.manage.microsoft.com <br>portal.fei.amsua0402.manage.microsoft.com <br>m.fei.amsua0402.manage.microsoft.com|52.160.70.20<br>52.168.54.64 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>fei.amsub0202.manage.microsoft.com <br>portal.fei.amsub0202.manage.microsoft.com <br>m.fei.amsub0202.manage.microsoft.com<br>fei.amsub0302.manage.microsoft.com <br>portal.fei.amsub0302.manage.microsoft.com <br>m.fei.amsub0302.manage.microsoft.com|52.138.193.149<br>51.144.161.187|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com<br>fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com<br>fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com<br>fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com|52.175.12.209<br>20.188.107.228|
|fef.msua01.manage.microsoft.com|138.91.243.97|
|fef.msua02.manage.microsoft.com|52.177.194.236|
|fef.msua04.manage.microsoft.com|23.96.112.28|
|fef.msua05.manage.microsoft.com|138.91.244.151|
|fef.msua06.manage.microsoft.com|13.78.185.97|
|fef.msua07.manage.microsoft.com|52.175.208.218|
|fef.msub01.manage.microsoft.com|137.135.128.214|
|fef.msub02.manage.microsoft.com|137.135.130.29|
|fef.msub03.manage.microsoft.com|52.169.82.238|
|fef.msub05.manage.microsoft.com|23.97.166.52|
|fef.msuc01.manage.microsoft.com|52.230.19.86|
|fef.msuc02.manage.microsoft.com|23.98.66.118|
|fef.msuc03.manage.microsoft.com|23.101.0.100|
|fef.msuc05.manage.microsoft.com|52.230.16.180|
|fef.amsua0202.manage.microsoft.com|52.165.165.17|
|fef.amsua0402.manage.microsoft.com|40.69.157.122|
|fef.amsua0502.manage.microsoft.com|13.85.68.142|
|fef.amsua0602.manage.microsoft.com|52.161.28.64|
|fef.amsub0102.manage.microsoft.com|40.118.98.207|
|fef.amsub0202.manage.microsoft.com|40.69.208.122|
|fef.amsub0302.manage.microsoft.com|13.74.145.65|
|enterpriseregistration.windows.net|52.175.211.189|
|Admin.manage.microsoft.com|52.224.221.227<br>52.161.162.117<br>52.178.44.195<br>52.138.206.56<br>52.230.21.208<br>13.75.125.10|
|wip.mam.manage.microsoft.com|52.187.76.84<br>13.76.5.121<br>52.165.160.237<br>40.86.82.163<br>52.233.168.142<br>168.63.101.57|
|mam.manage.microsoft.com|104.40.69.125<br>13.90.192.78<br>40.85.174.177<br>40.85.77.31<br>137.116.229.43<br>52.163.215.232<br>52.174.102.180|


### Network requirements Powershell scripts and Win32 apps
If you're using Intune to deploy Powershell scripts or Win32 apps, you'll also need to grant access to endpoints in which your tenant currently resides.

|ASU | Storage name | CDN |
| --- | --- |--- |
| AMSUA0601 | prodmsua06data | https://prodmsua06data.azureedge.net |
| AMSUA0602 | prodamsua0602data | https://prodamsua0602data.azureedge.net |
| AMSUA0101 | prodmsua01data | https://prodmsua01data.azureedge.net |
| AMSUA0201 | prodmsua02data | https://prodmsua02data.azureedge.net |
| AMSUA0202 | Prodmsua0202rcdata | https://prodamsua0202data.azureedge.net/ |
| AMSUA0401 | prodmsua04data | https://prodmsua04data.azureedge.net |
| AMSUA0402 | Prodmsua0402rcdata | https://prodamsua0402data.azureedge.net/ |
| AMSUA0501 | prodmsua05data | https://prodmsua05data.azureedge.net |
| AMSUA0502 | prodmsua0502data | https://prodmsua0502data.azureedge.net |
| AMSUB0101 | prodmsub01data | https://prodmsub01data.azureedge.net |
| AMSUB0102 | prodamsub0102data | https://prodamsub0102data.azureedge.net |
| AMSUB0201 | prodmsub02data | https://prodmsub02data.azureedge.net |
| AMSUB0202 | Prodmsub0202rcdata | https://prodamsub0202data.azureedge.net |
| AMSUB0301 | Prodmsub03data2 | https://prodmsub03data2.azureedge.net |
| AMSUB0302 | Prodmsub0302rcdata | https://prodamsub0302data.azureedge.net |
| AMSUB0501 | prodmsub05data | https://prodmsub05data.azureedge.net |
| AMSUC0101 | prodmsuc01data | https://prodmsuc01data.azureedge.net |
| AMSUC0201 | prodmsuc02data | https://prodmsuc02data.azureedge.net |
| AMSUC0301 | prodmsuc03data | https://prodmsuc03data.azureedge.net |
| AMSUC0501 | prodmsuc05data | https://prodmsuc05data.azureedge.net |
| AMSUA0701 | pemsua07rcdata | https://pemsua07data.azureedge.net |

#### Port requirements
For peer-to-peer traffic, Delivery Optimization uses 7680 for TCP/IP or 3544 for NAT traversal (optionally Teredo). 
For client-service communication, it uses HTTP or HTTPS over port 80/443.

#### Proxy requirements
To use Delivery Optimization, you must allow Byte Range requests. For more information, see [Proxy requirements for Windows Update](https://docs.microsoft.com/windows/deployment/update/windows-update-troubleshooting).

#### Firewall requirements
Allow the following hostnames through your firewall to support Delivery Optimization.
For communication between clients and the Delivery Optimization cloud service:
- *.do.dsp.mp.microsoft.com.

For Delivery Optimization metadata:
- *.dl.delivery.mp.microsoft.com
- *.emdl.ws.microsoft.com

### Apple device network information


|Used for|Hostname (IP address/subnet)|Protocol|Port|
|-----|--------|------|-------|
|Receiving Push notifications from Intune service via Apple Push Notification Service (APNS). See Apple’s documentation [here](https://support.apple.com/en-us/HT203609)|                                    gateway.push.apple.com (17.0.0.0/8)                                  |    TCP     |     2195     |
|Sending feedback to Intune service via Apple Push Notification Service (APNS)|                                  feedback.push.apple.com(17.0.0.0/8)                                  |    TCP     |     2196     |
|Retrieving and displaying content from Apple servers|itunes.apple.com<br>\*.itunes.apple.com<br>\*.mzstatic.com<br>\*.phobos.apple.com<br> \*.phobos.itunes-apple.com.akadns.net |    HTTP    |      80      |
|Communications with APNS servers|#-courier.push.apple.com (17.0.0.0/8)<br>'#' is a random number from 0 to 50.|    TCP     |  5223 and 443  |
|Various functionality including accessing the World Wide Web, iTunes store, macOS app store, iCloud, messaging, etc. |phobos.apple.com<br>ocsp.apple.com<br>ax.itunes.apple.com<br>ax.itunes.apple.com.edgesuite.net| HTTP/HTTPS |  80 or 443   |

For more information, see Apple's [TCP and UDP ports used by Apple software products](https://support.apple.com/en-us/HT202944), [About macOS, iOS, and iTunes server host connections and iTunes background processes](https://support.apple.com/en-us/HT201999), and [If your macOS and iOS clients aren't getting Apple push notifications](https://support.apple.com/en-us/HT203609).
