---
# required metadata

title: Intune network bandwidth use | Microsoft Docs
description: intune network bandwidth usage
keywords:
author: nathbarnms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: classic-portal

---

# Intune network bandwidth use

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

This guidance is for system administrators responsible for device management in the enterprise. For help using Intune on your mobile device, see [frequently asked questions about the Intune Company Portal](https://docs.microsoft.com/intune/enduser/company-portal-frequently-asked-questions).

Before you set up Microsoft Intune, review this topic and other requirements listed in [What to know before you start Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).

Use the information in the following sections to plan for network traffic for Microsoft Intune clients.

## Average network traffic
This table lists the approximate size and frequency of common content that travels across the network for each client.

> [!NOTE]
> To ensure that computers and mobile devices receive the necessary updates and content from the Intune service, they must be periodically connected to the Internet. The time taken to receive updates or content will vary, but as a guideline, they should remain continuously connected to the Internet for at least 1 hour each day.

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
You can use a proxy server that can cache content to reduce duplicate downloads and reduce the use of network bandwidth by clients that request content from the Internet.

A caching proxy server receives requests for content from client computers on your network, retrieves that content from the Internet, and can then cache both HTTP responses and binary downloads. The server uses the cached information to answer subsequent requests from Intune client computers.

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
Intune clients can use BranchCache to reduce wide area network (WAN) traffic. The following operating systems that are supported as clients also support BranchCache:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

To use BranchCache, the client computer must have BranchCache enabled, and then be configured for **distributed cache mode**.

By default, BranchCache and distributed cache mode are enabled on a computer when the Intune client is installed. However, if the client already has Group Policy that disables BranchCache, Intune does not override that policy and BranchCache will remains disabled on that computer.

If you use BranchCache, you should communicate with other administrators in your organization who manage Group Policy and Intune Firewall policy to ensure they do not deploy policy that disables BranchCache or Firewall exceptions. For more about BranchCache, see [BranchCache Overview](http://technet.microsoft.com/library/hh831696.aspx).

## Network communication requirements

You must enable network communications between the devices you manage and use to manage your Intune subscription, and the websites required for cloud-based services.

Intune uses no on-premises infrastructure such as servers running Intune software, but there are options to use on-premises infrastructure including Exchange and Active Directory synchronization tools.

To manage computers that are behind firewalls and proxy servers, you must set up firewalls and proxy servers to allow communications for Intune.

### Requirements for proxy servers
To manage computers that are behind a proxy server, be aware that:

-   The proxy server must support both **HTTP** and **HTTPS** because Intune clients use both protocols
-   Intune supports unauthenticated proxy servers

You can modify proxy server settings on individual client computers, or you can use Group Policy settings to change settings for all client computers that are located behind a specified proxy server.

### Requirements for firewalls, ports, and domains
Managed devices require configurations that let **All Users** access services through firewalls.

The following table lists the ports and services that the Intune client accesses.

|**Domain**|**Ports**|**IP address**|
|------|----|---|
|manage.microsoft.com<br>a.manage.microsoft.com<br>admin.manage.microsoft.com<br>enterpriseenrollment.manage.microsoft.com<br>enterpriseenrollment-s.manage.microsoft.com<br>i.manage.microsoft.com<br>p.manage.microsoft.com<br>r.manage.microsoft.com|80 and 443|134.170.168.254<br>134.170.51.126
|m.manage.microsoft.com|80 and 443| 13.91.59.243<br>40.68.30.140
|portal.manage.microsoft.com|80 and 443|40.121.50.69<br>52.169.30.159
|account.manage.microsoft.com|80 and 443|157.56.13.59
|fef.msua01.manage.microsoft.com|80 and 443|138.91.243.97
|fef.msua02.manage.microsoft.com|80 and 443|23.96.112.46
|fef.msua04.manage.microsoft.com|80 and 443|23.96.112.28
|fef.msua05.manage.microsoft.com|80 and 443|138.91.244.151
|fef.msub01.manage.microsoft.com|80 and 443|137.135.128.214
|fef.msub02.manage.microsoft.com|80 and 443|137.135.130.29
|fef.msub03.manage.microsoft.com|80 and 443|23.97.165.17
|fef.msub05.manage.microsoft.com|80 and 443|23.97.166.52
|fef.msuc01.manage.microsoft.com|80 and 443|207.46.225.1
|fef.msuc02.manage.microsoft.com|80 and 443|23.98.66.118
|fef.msuc03.manage.microsoft.com|80 and 443|23.101.0.100
|fef.msuc05.manage.microsoft.com|80 and 443|207.46.154.33
|fef.msua06.manage.microsoft.com|80 and 443|104.42.188.1
|fei.msua01.manage.microsoft.com|80 and 443|138.91.240.131
|fei.msua02.manage.microsoft.com|80 and 443|23.96.112.143
|fei.msua04.manage.microsoft.com|80 and 443|23.96.112.147
|fei.msua05.manage.microsoft.com|80 and 443|138.91.240.163
|fei.msub01.manage.microsoft.com|80 and 443|137.135.130.85
|fei.msub02.manage.microsoft.com|80 and 443|137.135.132.149
|fei.msub03.manage.microsoft.com|80 and 443|23.97.160.232
|fei.msub05.manage.microsoft.com|80 and 443|23.97.162.250
|fei.msuc01.manage.microsoft.com|80 and 443|207.46.224.73
|fei.msuc02.manage.microsoft.com|80 and 443|23.98.66.194
|fei.msuc03.manage.microsoft.com|80 and 443|23.101.2.105
|fei.msuc05.manage.microsoft.com|80 and 443|207.46.147.126
|fei.msua06.manage.microsoft.com|80 and 443|138.91.149.190
|m.fei.msua01.manage.microsoft.com|80 and 443|138.91.240.131
|m.fei.msua02.manage.microsoft.com|80 and 443|23.96.112.143
|m.fei.msua04.manage.microsoft.com|80 and 443|23.96.112.147
|m.fei.msua05.manage.microsoft.com|80 and 443|138.91.240.163
|m.fei.msub01.manage.microsoft.com|80 and 443|137.135.130.85
|m.fei.msub02.manage.microsoft.com|80 and 443|137.135.132.149
|m.fei.msub03.manage.microsoft.com|80 and 443|23.97.160.232
|m.fei.msub05.manage.microsoft.com|80 and 443|23.97.162.250
|m.fei.msuc01.manage.microsoft.com|80 and 443|207.46.224.73
|m.fei.msuc02.manage.microsoft.com|80 and 443|23.98.66.194
|m.fei.msuc03.manage.microsoft.com|80 and 443|23.101.2.105
|m.fei.msuc05.manage.microsoft.com|80 and 443|207.46.147.126
|m.fei.msua06.manage.microsoft.com|80 and 443|138.91.149.190
|m.msua01.manage.microsoft.com|80 and 443|157.55.50.182
|m.msua02.manage.microsoft.com|80 and 443|134.170.49.121
|m.msua04.manage.microsoft.com|80 and 443|134.170.49.126
|m.msua05.manage.microsoft.com|80 and 443|157.55.240.190
|m.msua06.manage.microsoft.com|80 and 443|134.170.49.114
|m.msub01.manage.microsoft.com|80 and 443|94.245.121.50
|m.msub02.manage.microsoft.com|80 and 443|94.245.121.58
|m.msub03.manage.microsoft.com|80 and 443|94.245.121.56
|m.msub05.manage.microsoft.com|80 and 443|157.56.113.123
|m.msuc01.manage.microsoft.com|80 and 443|104.44.84.187
|m.msuc02.manage.microsoft.com|80 and 443|104.44.84.188
|m.msuc03.manage.microsoft.com|80 and 443|104.44.84.189
|m.msuc05.manage.microsoft.com|80 and 443|111.221.76.60
|msua01.manage.microsoft.com|80 and 443|157.55.50.182
|msua02.manage.microsoft.com|80 and 443|134.170.49.121
|msua04.manage.microsoft.com|80 and 443|134.170.49.126
|msua05.manage.microsoft.com|80 and 443|157.55.240.190
|msub01.manage.microsoft.com|80 and 443|94.245.121.50
|msub02.manage.microsoft.com|80 and 443|94.245.121.58
|msub03.manage.microsoft.com|80 and 443|94.245.121.56
|msub05.manage.microsoft.com|80 and 443|157.56.113.123
|msuc01.manage.microsoft.com|80 and 443|104.44.84.187
|msuc02.manage.microsoft.com|80 and 443|104.44.84.188
|msuc03.manage.microsoft.com|80 and 443|104.44.84.189
|msuc05.manage.microsoft.com|80 and 443|111.221.76.60
|msua06.manage.microsoft.com|80 and 443|134.170.49.114
|ncufun.account.manage.microsoft.com|80 and 443|157.55.252.224
|neufun.account.manage.microsoft.com|80 and 443|65.52.229.134
|portal.fei.msua01.manage.microsoft.com|80 and 443|138.91.240.131
|portal.fei.msua02.manage.microsoft.com|80 and 443|23.96.112.143
|portal.fei.msua04.manage.microsoft.com|80 and 443|23.96.112.147
|portal.fei.msua05.manage.microsoft.com|80 and 443|138.91.240.163
|portal.fei.msub01.manage.microsoft.com|80 and 443|137.135.130.85
|portal.fei.msub02.manage.microsoft.com|80 and 443|137.135.132.149
|portal.fei.msub03.manage.microsoft.com|80 and 443|23.97.160.232
|portal.fei.msub05.manage.microsoft.com|80 and 443|23.97.162.250
|portal.fei.msuc01.manage.microsoft.com|80 and 443|207.46.224.73
|portal.fei.msuc02.manage.microsoft.com|80 and 443|23.98.66.194
|portal.fei.msuc03.manage.microsoft.com|80 and 443|23.101.2.105
|portal.fei.msuc05.manage.microsoft.com|80 and 443|207.46.147.126
|portal.fei.msua06.manage.microsoft.com|80 and 443|138.91.149.190
|portal.msua01.manage.microsoft.com|80 and 443|157.55.50.182
|portal.msua02.manage.microsoft.com|80 and 443|134.170.49.121
|portal.msua04.manage.microsoft.com|80 and 443|134.170.49.126
|portal.msua05.manage.microsoft.com|80 and 443|157.55.240.190
|portal.msub01.manage.microsoft.com|80 and 443|94.245.121.50
|portal.msub02.manage.microsoft.com|80 and 443|94.245.121.58
|portal.msub03.manage.microsoft.com|80 and 443|94.245.121.56
|portal.msub05.manage.microsoft.com|80 and 443|157.56.113.123
|portal.msuc01.manage.microsoft.com|80 and 443|104.44.84.187
|portal.msuc02.manage.microsoft.com|80 and 443|104.44.84.188
|portal.msuc03.manage.microsoft.com|80 and 443|104.44.84.189
|portal.msuc05.manage.microsoft.com|80 and 443|111.221.76.60
|portal.msua06.manage.microsoft.com|80 and 443|134.170.49.114
|ssu2.manage.microsoft.com|80 and 443|157.55.99.181
|status.manage.microsoft.com|80 and 443|157.55.99.170
|swda01.manage.microsoft.com<br>swda02.manage.microsoft.com<br>swdb01.manage.microsoft.com<br>swdb02.manage.microsoft.com<br>swdc01.manage.microsoft.com<br>swdc02.manage.microsoft.com|80 and 443|93.184.215.200
|*.microsoftonline-p.com|80 and 443||
|has.spserv.microsoft.com<br>Required for device health attestation service|443||
|*.microsoftonline-p.net|80 and 443||
|*.portal.office.com|80 and 443||
|*.spynet2.microsoft.com|443||
|c.microsoft.com|80 and 443||
|c1.microsoft.com|80 and 443||
|blob.core.windows.net|80 and 443||
|ajax.aspnetcdn.com|80 and 443||
|*.googleapis.com<br>This domain is required for JQuery support when you use the company portal website.|80 and 443||
|wustat.microsoft.com|80 and 443||
|Microsoft Update Services|\*.update.microsoft.com<br>download.microsoft.com<br>update.microsoft.com<br>\*.download.windowsupdate.com<br>download.windowsupdate.com<br>\*.windowsupdate.com<br>windowsupdate.microsoft.com<br>ntservicepack.microsoft.com|80 and 443|
|DNS lookup requests|manage.microsoft.com.nsatc.net|80|
|Samsung KNOX Standard device communication through the firewall|To enable Samsung KNOX Standard devices to contact KNOX Standard servers through the firewall, follow the instructions on the Samsung KNOX Standard FAQ.||
|Conditional access communication|443|204.79.197.200|
|Documentation, Help, and support:</br></br>*.livemeeting.com<br>\*.microsoftonline.com<br>\*.social.technet.microsoft.com<br>blogs.technet.com<br>go.microsoft.com<br>onlinehelp.microsoft.com<br>www.microsoft.com|80|||

>[!div class="step-by-step"]

>[&larr; **Prerequisites**](what-to-know-before-you-start-microsoft-intune.md)     [**Subscription** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)  
