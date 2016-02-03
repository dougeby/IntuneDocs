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

||||
|-|-|-|
|**Purpose**|**Domain**|**Ports**|
|Microsoft Intune and related services|&#42;.manage.microsoft.com|80 and 443|
||&#42;manage.microsoft.com|80 and 443|
||manage.microsoft.com|80 and 443|
||&#42;.microsoftonline-p.com|80 and 443|
||&#42;.microsoftonline-p.net|80 and 443|
||&#42;.portal.office.com|80 and 443|
||&#42;.spynet2.microsoft.com|443|
||c.microsoft.com|80 and 443|
||c1.microsoft.com|80 and 443|
||blob.core.windows.net|80 and 443|
||ajax.aspnetcdn.com|80 and 443|
||&#42;.googleapis.com<br /><br />This domain is required for JQuery support when you use the company portal website.|80 and 443|
||wustat.microsoft.com|80 and 443|
|Microsoft Update Services|&#42;.update.microsoft.com|80 and 443|
||download.microsoft.com|80 and 443|
||update.microsoft.com|80 and 443|
||&#42;.download.windowsupdate.com|80 and 443|
||download.windowsupdate.com|80 and 443|
||&#42;.windowsupdate.com|80 and 443|
||windowsupdate.microsoft.com|80 and 443|
||ntservicepack.microsoft.com|80 and 443|
|DNS lookup requests|manage.microsoft.com.nsatc.net|80|
|Samsung KNOX device communication through the firewall|To enable Samsung KNOX devices to contact KNOX servers through the firewall, follow the instructions on the [Samsung KNOX FAQ](https://www.samsungknox.com/en/faq/our-corporate-devices-are-behind-firewall-how-do-i-enable-knox-devices-contact-samsung-servers).|To enable Samsung KNOX devices to contact KNOX servers through the firewall, follow the instructions on the [Samsung KNOX FAQ](https://www.samsungknox.com/en/faq/our-corporate-devices-are-behind-firewall-how-do-i-enable-knox-devices-contact-samsung-servers).|
|Documentation, Help, and support|&#42;.livemeeting.com|80 and 443|
||&#42;.microsoftonline.com|80 and 443|
||&#42;.social.technet.microsoft.com|80|
||blogs.technet.com|80|
||go.microsoft.com|80|
||onlinehelp.microsoft.com|80|
||www.microsoft.com|80|

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
|On-Premises Connector|If your instance of Exchange Server is on-premises, you must download, install, and [Configure Microsoft Intune on-premises connector for on-premises or hosted Exchange](../Topic/Mobile_device_management_with_Exchange_ActiveSync_and_Microsoft_Intune.md#bkmk_EX_OP) on a computer in your infrastructure. This connector can also connect to Exchange in the cloud.<br /><br />If your instance of Exchange Server is hosted in a cloud-based service, you can install and configure the On-Premises Connector, or you can [Configure Intune service to service connector for hosted Exchange](../Topic/Mobile_device_management_with_Exchange_ActiveSync_and_Microsoft_Intune.md#bkmk_S_S) which does not require an on-premises server to host the connector.<br /><br />Before you can use either connector to connect [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to your Exchange Server, you must [set up Active Directory synchronization](http://technet.microsoft.com/library/dn646983.aspx#BKMK_SyncUsersFromAD) so that your local users and security groups are synchronized with your instance of Azure AD.|
|Proxy server|If you manage clients that access the Internet through a proxy server, see [Requirements for proxy servers](../Topic/Network_infrastructure_requirements_for_Microsoft_Intune.md#BKMK_ProxyReqs).<br /><br />You can also use a proxy server that caches content to reduce network bandwidth. For more information, see [Reduce network bandwidth use](../Topic/What_to_know_before_setting_up_Microsoft_Intune.md#BKMK_ReduceBandwidth) in the [What to know before setting up Microsoft Intune](../Topic/What_to_know_before_setting_up_Microsoft_Intune.md) topic.|

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
[What to know before setting up Microsoft Intune](../Topic/What_to_know_before_setting_up_Microsoft_Intune.md)
[How to buy Intune](http://technet.microsoft.com/library/dn646949.aspx)

