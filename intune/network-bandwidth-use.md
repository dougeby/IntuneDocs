---
# required metadata

title: Intune network bandwidth use
description: intune network bandwidth usage
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/07/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: angerobe
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Intune network bandwidth use

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

This guidance helps Intune admins understand the network requirements for the Intune service. You can use this information to understand bandwidth requirements and IP address and port settings needed for proxy settings.

## Average network traffic
This table lists the approximate size and frequency of common content that travels across the network for each client.

> [!NOTE]
> To ensure devices receive the updates and content from Intune, they must periodically connect to the Internet. The time required to receive updates or content can vary, but they should remain continuously connected to the Internet for at least one hour each day.

|Content type|Approximate size|Frequency and details|
|----------------|--------------------|-------------------------|
|Intune client installation<br /><br />**The following requirements are in addition to the Intune client installation**|125 MB|**One time**<br /><br />The size of the client download varies depending on the operating system of the client computer.|
|Client enrollment package|15 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Endpoint Protection agent|65 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Operations Manager agent|11 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Policy agent|3 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Remote Assistance via Microsoft Easy Assist agent|6 MB|**One time**<br /><br />Additional downloads are possible when there are updates for this content type.|
|Daily client operations|6 MB|**Daily**<br /><br />The Intune client regularly communicates with the Intune service to check for updates and policies, and to report the client’s status to the service.|
|Endpoint Protection malware definition updates|Varies<br /><br />Typically 40 KB to 2 MB|**Daily**<br /><br />Up to three times a day.|
|Endpoint Protection engine update|5 MB|**Monthly**|
|Software updates|Varies<br /><br />The size depends on the updates you deploy.|**Monthly**<br /><br />Typically, software updates release on the second Tuesday of each month.<br /><br />A newly enrolled or deployed computer can use more network bandwidth while downloading the full set of previously released updates.|
|Service packs|Varies<br /><br />The size varies for each service pack you deploy.|**Varies**<br /><br />Depends on when you deploy service packs.|
|Software distribution|Varies<br /><br />The size depends on the software you deploy.|**Varies**<br /><br />Depends on when you deploy software.|

## Ways to reduce network bandwidth use
You can use one or more of the following methods to reduce network bandwidth use for Intune clients.

### Use a proxy server to cache content requests
A proxy server can cache content to reduce duplicate downloads and reduce network bandwidth from content from the Internet.

A caching proxy server that receives content requests from clients can retrieve that content and cache both web responses and downloads. The server uses cached data to answer subsequent requests from clients.

The following are typical settings to use for a proxy server that caches content for Intune clients.

|Setting|Recommended value|Details|
|-----------|---------------------|-----------|
|Cache size|5 GB to 30 GB|The value varies based on the number of client computers in your network and the configurations you use. To prevent files from being deleted too soon, adjust the size of the cache for your environment.|
|Individual cache file size|950 MB|This setting might not be available in all caching proxy servers.|
|Object types to cache|HTTP<br /><br />HTTPS<br /><br />BITS|Intune packages are CAB files retrieved by Background Intelligent Transfer Service (BITS) download over HTTP.|
For information about using a proxy server to cache content, see the documentation for your proxy server solution.

### Use Background Intelligent Transfer Service on computers
Intune supports using Background Intelligent Transfer Service (BITS) on a Windows computer to reduce the network bandwidth that is used during the hours that you configure. You can configure policy for BITS on the **Network bandwidth** page of the Intune Agent policy.

To learn more about BITS and Windows computers, see [Background Intelligent Transfer Service](http://technet.microsoft.com/library/bb968799.aspx) in the TechNet Library.

### Use BranchCache on computers
Intune clients can use BranchCache to reduce wide area network (WAN) traffic. The following operating systems support BranchCache:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

To use BranchCache, the client computer must have BranchCache enabled, and then be configured for **distributed cache mode**.

By default, BranchCache and distributed cache mode are enabled on computers when the Intune client is installed. However, if Group Policy has disabled BranchCache, Intune does not override that policy and BranchCache remains disabled.

If you use BranchCache, work with other administrators in your organization to manage Group Policy and Intune Firewall policy. Ensure they do not deploy policy that disables BranchCache or Firewall exceptions. For more about BranchCache, see [BranchCache Overview](http://technet.microsoft.com/library/hh831696.aspx).

## Network communication requirements

Enable network communications between the devices you manage and the websites required for cloud-based services.

Intune uses no on-premises infrastructure such as servers running Intune software, but there are options to use on-premises infrastructure including Exchange and Active Directory synchronization tools.

To manage computers behind firewalls and proxy servers, you must enable communication for Intune.

-   The proxy server must support both **HTTP (80)** and **HTTPS (443)** because Intune clients use both protocols
-   Intune requires unauthenticated proxy server access to manage.microsoft.com for some tasks such as downloading software and updates

You can modify proxy server settings on individual client computers, or you can use Group Policy settings to change settings for all client computers that are located behind a specified proxy server.


<!--
> [!NOTE] If Windows 8.1 devices haven't cached proxy server credentials, enrollment might fail because the request doesn't prompt for credentials. Enrollment fails without warning as the request wait for a connection. If users might experience this issue, instruct them to open their browser settings and save proxy server settings to enable a connection.   -->

Managed devices require configurations that let **All Users** access services through firewalls.

The following tables list the ports and services that the Intune client accesses:

|**Domains**|**IP address**|
|---------------------|-----------|
|portal.manage.microsoft.com<br> m.manage.microsoft.com |40.86.181.86<br>13.82.59.78<br>13.74.184.100<br>40.68.188.2<br>13.75.42.6<br>52.230.25.184 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 104.40.82.191 <br>13.82.96.212 <br>52.169.9.87 <br>52.174.26.23 <br>40.83.123.72 <br>13.76.177.110 |
|portal.fei.msua01.manage.microsoft.com<br>m.fei.msua01.manage.microsoft.com |13.64.196.170|
|fei.msua01.manage.microsoft.com<br> portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com |40.71.34.120 |
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com |13.64.198.190|
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br> m.fei.msua02.manage.microsoft.com |	13.64.198.190|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |13.64.188.173|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |40.71.32.174|
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |13.64.197.181 |
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |40.71.38.205|
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |13.64.191.182 |
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |40.71.37.51 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |40.118.250.246 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |13.90.142.194 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.64.250.226 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.90.151.142 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.169.155.165 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.174.188.97 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.178.190.24 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.174.16.215 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |40.69.69.27 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |52.166.196.199 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |40.69.71.164 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |52.174.182.102 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |40.69.78.145 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |52.174.192.105 |
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |13.94.46.250|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |52.163.119.15 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |13.75.124.145 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |52.163.119.5|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.175.35.226|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.163.119.6|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.175.38.24|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.163.119.3|
|fef.msua01.manage.microsoft.com|138.91.243.97|
|fef.msua02.manage.microsoft.com|52.177.194.236|
|fef.msua04.manage.microsoft.com|23.96.112.28|
|fef.msua05.manage.microsoft.com|138.91.244.151|
|fef.msua06.manage.microsoft.com|13.78.185.97|
|fef.msua07.manage.microsoft.com|52.175.208.218|
|fef.msub01.manage.microsoft.com|137.135.128.214|
|fef.msub02.manage.microsoft.com|137.135.130.29|
|fef.msub03.manage.microsoft.com|23.97.165.17|
|fef.msub05.manage.microsoft.com|23.97.166.52|
|fef.msuc01.manage.microsoft.com|52.230.19.86|
|fef.msuc02.manage.microsoft.com|23.98.66.118|
|fef.msuc03.manage.microsoft.com|23.101.0.100|
|fef.msuc05.manage.microsoft.com|52.230.16.180|

### Apple device network information
| Hostname  | URL (IP address/subnet) | Protocol | Port | Device |
| --- | --- | --- | --- | --- |
|  Admin Console  | gateway.push.apple.com (17.0.0.0/8) | TCP | 2195 | Apple iOS and macOS |
| Admin Console  | feedback.push.apple.com(17.0.0.0/8) | TCP | 2196 | Apple iOS and macOS |
| Admin Console  | Apple iTunesitunes.apple.com, \*.mzstatic.com, \*.phobos.apple.com, \*.phobos.apple.com.edgesuite.net | HTTP | 80 | Apple iOS and macOS  |
| PI Server  | gateway.push.apple.com(17.0.0.0/8) feedback.push.apple.com(17.0.0.0/8) | TCP | 2195, 2196 | For Apple iOS and macOS cloud messaging. |
| Device Services  | gateway.push.apple.com | TCP | 2195 | Apple  |
| Device Services  | feedback.push.apple.com | TCP | 2196 | Apple  |
| Device Services  | Apple iTunesitunes.apple.com \*.mzstatic.com\*.phobos.apple.com \*.phobos.apple.com.edgesuite.net | HTTP | 80 | Apple  |
| Devices (Internet/Wi-Fi) | #-courier.push.apple.com(17.0.0.0/8) | TCP | 5223 and 443 | Apple only. &#39;#&#39; is a random number from 0 to 200. |
| Devices (Internet/Wi-Fi) | phobos.apple.comocsp.apple.comax.itunes.apple.com | HTTP/HTTPS | 80 or 443 | Apple only |
