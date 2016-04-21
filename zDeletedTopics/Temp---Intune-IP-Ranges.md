---
title: Temp - Intune IP Ranges
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 594ee47b-8583-400c-a2ef-5b41715528aa
author: robstackmsft
---
# Temp - Intune IP Ranges

The follwing table lists all domains and IP addresses that might be used by [!INCLUDE[wit_firstref](/Token/wit_firstref.xml)]. Depending on your configuration, you might need to allow one or more of these addresses access through your company firewall.

The following table lists the domains and services that the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client accesses.

|**Purpose**|**Domain**|**Ports**|**IP addresses**|
|-|-|-|-|
|Microsoft Intune and related services|&#42;.manage.microsoft.com|80 and 443|
||&#42;manage.microsoft.com|80 and 443|
||manage.microsoft.com|80 and 443|134.170.168.254<br>134.170.51.126
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







## See Also
[Introduction to Microsoft Intune](../Topic/Introduction-to-Microsoft-Intune.md)

