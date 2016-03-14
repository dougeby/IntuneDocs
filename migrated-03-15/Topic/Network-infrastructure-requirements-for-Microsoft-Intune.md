---
title: Network infrastructure requirements for Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid: 074de65b-84a5-4a01-a824-18ffd838eab0
author: Staciebarker
---
# Network infrastructure requirements for Microsoft Intune
The following [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] requirements enable your network infrastructure to pass communications between the devices you manage and use to manage your subscription, and the websites on the Internet that the cloud-based service uses. For [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] requirements about browsers, accounts, portals, and more, see [What to know before setting up Intune](https://technet.microsoft.com/library/dn646966.aspx).

There is no requirement to use on-premises infrastructure (like a server where you must install software), but there are options to use on-premises infrastructure including Exchange and Active Directory synchronization tools.

## <a name="BKMK_NetworkReqs"></a>Network infrastructure
To manage computers that are behind firewalls and proxy servers, you must set up firewalls and proxy servers to allow communications for [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

### <a name="BKMK_FirewallReqs"></a>Requirements for firewalls, ports, and domains
Managed devices require configurations that let **All Users** access various services through firewalls.

The following table lists the domains and services that the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client accesses.


|**Purpose**|**Domain**|**Ports**|**IP address**|
|-|-|-|-|
|Microsoft Intune and related services|manage.microsoft.com<br>a.manage.microsoft.com<br>admin.manage.microsoft.com<br>enterpriseenrollment.manage.microsoft.com<br>enterpriseenrollment-s.manage.microsoft.com<br>i.manage.microsoft.com<br>m.manage.microsoft.com<br>p.manage.microsoft.com<br>portal.manage.microsoft.com<br>r.manage.microsoft.com|80 and 443|134.170.168.254<br>134.170.51.126
||account.manage.microsoft.com|80 and 443|157.56.13.59
||fef.msua01.manage.microsoft.com|80 and 443|138.91.243.97
||fef.msua02.manage.microsoft.com|80 and 443|23.96.112.46
||fef.msua04.manage.microsoft.com|80 and 443|23.96.112.28
||fef.msua05.manage.microsoft.com|80 and 443|138.91.244.151
||fef.msub01.manage.microsoft.com|80 and 443|137.135.128.214
||fef.msub02.manage.microsoft.com|80 and 443|137.135.130.29
||fef.msub03.manage.microsoft.com|80 and 443|23.97.165.17
||fef.msub05.manage.microsoft.com|80 and 443|23.97.166.52
||fef.msuc01.manage.microsoft.com|80 and 443|207.46.225.1
||fef.msuc02.manage.microsoft.com|80 and 443|23.98.66.118
||fef.msuc03.manage.microsoft.com|80 and 443|23.101.0.100
||fef.msuc05.manage.microsoft.com|80 and 443|207.46.154.33
||fef.msua06.manage.microsoft.com|80 and 443|104.42.188.1
||fei.msua01.manage.microsoft.com|80 and 443|138.91.240.131
||fei.msua02.manage.microsoft.com|80 and 443|23.96.112.143
||fei.msua04.manage.microsoft.com|80 and 443|23.96.112.147
||fei.msua05.manage.microsoft.com|80 and 443|138.91.240.163
||fei.msub01.manage.microsoft.com|80 and 443|137.135.130.85
||fei.msub02.manage.microsoft.com|80 and 443|137.135.132.149
||fei.msub03.manage.microsoft.com|80 and 443|23.97.160.232
||fei.msub05.manage.microsoft.com|80 and 443|23.97.162.250
||fei.msuc01.manage.microsoft.com|80 and 443|207.46.224.73
||fei.msuc02.manage.microsoft.com|80 and 443|23.98.66.194
||fei.msuc03.manage.microsoft.com|80 and 443|23.101.2.105
||fei.msuc05.manage.microsoft.com|80 and 443|207.46.147.126
||fei.msua06.manage.microsoft.com|80 and 443|138.91.149.190
||m.fei.msua01.manage.microsoft.com|80 and 443|138.91.240.131
||m.fei.msua02.manage.microsoft.com|80 and 443|23.96.112.143
||m.fei.msua04.manage.microsoft.com|80 and 443|23.96.112.147
||m.fei.msua05.manage.microsoft.com|80 and 443|138.91.240.163
||m.fei.msub01.manage.microsoft.com|80 and 443|137.135.130.85
||m.fei.msub02.manage.microsoft.com|80 and 443|137.135.132.149
||m.fei.msub03.manage.microsoft.com|80 and 443|23.97.160.232
||m.fei.msub05.manage.microsoft.com|80 and 443|23.97.162.250
||m.fei.msuc01.manage.microsoft.com|80 and 443|207.46.224.73
||m.fei.msuc02.manage.microsoft.com|80 and 443|23.98.66.194
||m.fei.msuc03.manage.microsoft.com|80 and 443|23.101.2.105
||m.fei.msuc05.manage.microsoft.com|80 and 443|207.46.147.126
||m.fei.msua06.manage.microsoft.com|80 and 443|138.91.149.190
||m.msua01.manage.microsoft.com|80 and 443|157.55.50.182
||m.msua02.manage.microsoft.com|80 and 443|134.170.49.121
||m.msua04.manage.microsoft.com|80 and 443|134.170.49.126
||m.msua05.manage.microsoft.com|80 and 443|157.55.240.190
||m.msua06.manage.microsoft.com|80 and 443|134.170.49.114
||m.msub01.manage.microsoft.com|80 and 443|94.245.121.50
||m.msub02.manage.microsoft.com|80 and 443|94.245.121.58
||m.msub03.manage.microsoft.com|80 and 443|94.245.121.56
||m.msub05.manage.microsoft.com|80 and 443|157.56.113.123
||m.msuc01.manage.microsoft.com|80 and 443|104.44.84.187
||m.msuc02.manage.microsoft.com|80 and 443|104.44.84.188
||m.msuc03.manage.microsoft.com|80 and 443|104.44.84.189
||m.msuc05.manage.microsoft.com|80 and 443|111.221.76.60
||msua01.manage.microsoft.com|80 and 443|157.55.50.182
||msua02.manage.microsoft.com|80 and 443|134.170.49.121
||msua04.manage.microsoft.com|80 and 443|134.170.49.126
||msua05.manage.microsoft.com|80 and 443|157.55.240.190
||msub01.manage.microsoft.com|80 and 443|94.245.121.50
||msub02.manage.microsoft.com|80 and 443|94.245.121.58
||msub03.manage.microsoft.com|80 and 443|94.245.121.56
||msub05.manage.microsoft.com|80 and 443|157.56.113.123
||msuc01.manage.microsoft.com|80 and 443|104.44.84.187
||msuc02.manage.microsoft.com|80 and 443|104.44.84.188
||msuc03.manage.microsoft.com|80 and 443|104.44.84.189
||msuc05.manage.microsoft.com|80 and 443|111.221.76.60
||msua06.manage.microsoft.com|80 and 443|134.170.49.114
||ncufun.account.manage.microsoft.com|80 and 443|157.55.252.224
||neufun.account.manage.microsoft.com|80 and 443|65.52.229.134
||portal.fei.msua01.manage.microsoft.com|80 and 443|138.91.240.131
||portal.fei.msua02.manage.microsoft.com|80 and 443|23.96.112.143
||portal.fei.msua04.manage.microsoft.com|80 and 443|23.96.112.147
||portal.fei.msua05.manage.microsoft.com|80 and 443|138.91.240.163
||portal.fei.msub01.manage.microsoft.com|80 and 443|137.135.130.85
||portal.fei.msub02.manage.microsoft.com|80 and 443|137.135.132.149
||portal.fei.msub03.manage.microsoft.com|80 and 443|23.97.160.232
||portal.fei.msub05.manage.microsoft.com|80 and 443|23.97.162.250
||portal.fei.msuc01.manage.microsoft.com|80 and 443|207.46.224.73
||portal.fei.msuc02.manage.microsoft.com|80 and 443|23.98.66.194
||portal.fei.msuc03.manage.microsoft.com|80 and 443|23.101.2.105
||portal.fei.msuc05.manage.microsoft.com|80 and 443|207.46.147.126
||portal.fei.msua06.manage.microsoft.com|80 and 443|138.91.149.190
||portal.msua01.manage.microsoft.com|80 and 443|157.55.50.182
||portal.msua02.manage.microsoft.com|80 and 443|134.170.49.121
||portal.msua04.manage.microsoft.com|80 and 443|134.170.49.126
||portal.msua05.manage.microsoft.com|80 and 443|157.55.240.190
||portal.msub01.manage.microsoft.com|80 and 443|94.245.121.50
||portal.msub02.manage.microsoft.com|80 and 443|94.245.121.58
||portal.msub03.manage.microsoft.com|80 and 443|94.245.121.56
||portal.msub05.manage.microsoft.com|80 and 443|157.56.113.123
||portal.msuc01.manage.microsoft.com|80 and 443|104.44.84.187
||portal.msuc02.manage.microsoft.com|80 and 443|104.44.84.188
||portal.msuc03.manage.microsoft.com|80 and 443|104.44.84.189
||portal.msuc05.manage.microsoft.com|80 and 443|111.221.76.60
||portal.msua06.manage.microsoft.com|80 and 443|134.170.49.114
||ssu2.manage.microsoft.com|80 and 443|157.55.99.181
||status.manage.microsoft.com|80 and 443|157.55.99.170
||swda01.manage.microsoft.com<br>swda02.manage.microsoft.com<br>swdb01.manage.microsoft.com<br>swdb02.manage.microsoft.com<br>swdc01.manage.microsoft.com<br>swdc02.manage.microsoft.com|80 and 443|93.184.215.200
||*.microsoftonline-p.com|80 and 443||
||*.microsoftonline-p.net|80 and 443||
||*.portal.office.com|80 and 443||
||*.spynet2.microsoft.com|443||
||c.microsoft.com|80 and 443||
||c1.microsoft.com|80 and 443||
||blob.core.windows.net|80 and 443||
||ajax.aspnetcdn.com|80 and 443||
||*.googleapis.com<br>This domain is required for JQuery support when you use the company portal website.|80 and 443||
||wustat.microsoft.com|80 and 443||
Microsoft Update Services|\*.update.microsoft.com<br>download.microsoft.com<br>update.microsoft.com<br>\*.download.windowsupdate.com<br>download.windowsupdate.com<br>\*.windowsupdate.com<br>windowsupdate.microsoft.com<br>ntservicepack.microsoft.com|80 and 443||
|DNS lookup requests|manage.microsoft.com.nsatc.net|80||
Samsung KNOX device communication through the firewall|To enable Samsung KNOX devices to contact KNOX servers through the firewall, follow the instructions on the Samsung KNOX FAQ.|||
|Documentation, Help, and support|*.livemeeting.com<br>\*.microsoftonline.com<br>\*.social.technet.microsoft.com<br>blogs.technet.com<br>go.microsoft.com<br>onlinehelp.microsoft.com<br>www.microsoft.com|80||


### <a name="BKMK_ProxyReqs"></a>Requirements for proxy servers
To manage computers that are behind a proxy server, consider the following:

-   The proxy server must support both **HTTP** and **HTTPS** because [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] clients use both protocols.

-   [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] supports unauthenticated proxy servers.

You can modify proxy server settings on individual client computers, or you can use Group Policy settings to change settings for all client computers that are located behind a specified proxy server.

You can also use a proxy server that caches content to [reduce network bandwidth](http://technet.microsoft.com/library/dn646966.aspx#BKMK_reduceBandwidth) use by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] clients.

## <a name="BKMK_OnPremisesReqs"></a>On-premises infrastructure
The following table identifies on-premises infrastructure you can use with [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)].

|Infrastructure|More information|
|------------------|--------------------|
|On-Premises Connector|If your instance of Exchange Server is on-premises, you must download, install, and [Configure Microsoft Intune on-premises connector for on-premises or hosted Exchange](../Topic/Mobile-device-management-with-Exchange-ActiveSync-and-Microsoft-Intune.md#bkmk_EX_OP) on a computer in your infrastructure. This connector can also connect to Exchange in the cloud.<br /><br />If your instance of Exchange Server is hosted in a cloud-based service, you can install and configure the On-Premises Connector, or you can [Configure Intune service to service connector for hosted Exchange](../Topic/Mobile-device-management-with-Exchange-ActiveSync-and-Microsoft-Intune.md#bkmk_S_S) which does not require an on-premises server to host the connector.<br /><br />Before you can use either connector to connect [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to your Exchange Server, you must [set up Active Directory synchronization](http://technet.microsoft.com/library/dn646983.aspx#BKMK_SyncUsersFromAD) so that your local users and security groups are synchronized with your instance of Azure AD.|
|Proxy server|If you manage clients that access the Internet through a proxy server, see [Requirements for proxy servers](../Topic/Network-infrastructure-requirements-for-Microsoft-Intune.md#BKMK_ProxyReqs).<br /><br />You can also use a proxy server that caches content to reduce network bandwidth. For more information, see [Reduce network bandwidth use](../Topic/What-to-know-before-setting-up-Microsoft-Intune.md#BKMK_ReduceBandwidth) in the [What to know before setting up Microsoft Intune](../Topic/What-to-know-before-setting-up-Microsoft-Intune.md) topic.|

### <a name="BKMK_ExchanceConnectorReqs"></a>Requirements for the On-Premises Connector
The following table lists the requirements for the computer where you install the On-Premises Connector.

|Requirement|More information|
|---------------|--------------------|
|Operating systems|[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] supports the On-Premises Connector on a computer that runs any edition of [!INCLUDE[longhornshort](../Token/longhornshort_md.md)] SP2 64 bit, [!INCLUDE[nextref_server_7](../Token/nextref_server_7_md.md)], [!INCLUDE[win8_server_2](../Token/win8_server_2_md.md)], or  [!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)].<br /><br />The connector is not supported on any Server Core installation.|
|Microsoft Exchange version|The On-Premises Connector requires Microsoft Exchange 2010 SP1 or later.|
|Hardware|The computer where you install the connector requires a 1.6 GHz CPU with 2 GB ram and 10 GB of free disk space  minimum hardware.|
|Additional software|A full installation of Microsoft .NET Framework 4 and [!INCLUDE[wps_2](../Token/wps_2_md.md)] 2.0 must be installed on the computer that hosts the connector.|
|Network|The computer where you install the connector must be in a domain that has a trust relationship to the domain that hosts your Exchange Server.<br /><br />The computer requires configurations to enable it to access the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service through firewalls and proxy servers over Ports 80 and 443. Domains used by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] include manage.microsoft.com, &#42;manage.microsoft.com, and &#42;.manage.microsoft.com.|

### <a name="BKMK_ServiceConnectorReqs"></a>Requirements for the Service to Service Connector
The Service to Service Connector supports only cloud-based Exchange and has no requirements for on-premises infrastructure.

However, to use this connector, the following must be true:

-   You have an Office 365 subscription that has an Exchange Server 2013 tenant. So long as the tenant is Exchange Server 2013, the connector supports Exchange Server 2010 in that same environment.

-   The user account that you use to install the On-Premises Connector must be a tenant administrator for [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] and be an administrator in the Exchange tenant with a license to use Exchange Server 2013.

## See Also
[What to know before setting up Microsoft Intune](../Topic/What-to-know-before-setting-up-Microsoft-Intune.md)
[How to buy Intune](http://technet.microsoft.com/library/dn646949.aspx)

