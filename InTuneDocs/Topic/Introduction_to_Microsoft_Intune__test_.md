---
title: Introduction to Microsoft Intune &lt;test&gt;
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 5e2d548b-3858-453b-a31b-3e570d7b6fc8
author: Dougeby
robots: noindex,nofollow
---
# Introduction to Microsoft Intune &lt;test&gt;
![](../Image/Nav_Icons/WIT_Tile_W_OverviewHighlight.png)[![](../Image/Nav_Icons/WIT_Tile_W_GetStarted.png)](https://technet.microsoft.com/en-US/library/mt483702(TechNet.10).aspx)[![](../Image/Nav_Icons/WIT_Tile_W_EnrollDevices.png)](https://technet.microsoft.com/library/dn646962.aspx/?WT.mc_id=IntuneEnroll20150801)[![](../Image/Nav_Icons/WIT_Tile_W_ManageDevices.png)](https://technet.microsoft.com/library/mt313202.aspx/?WT.mc_id=IntuneConfig20150801)[![](../Image/Nav_Icons/WIT_Tile_W_ManageApps.png)](https://technet.microsoft.com/library/dn646965.aspx/?WT.mc_id=IntuneDeploy20150801)[![](../Image/Nav_Icons/WIT_Tile_W_ProtectResources.png)](https://technet.microsoft.com/library/mt313203.aspx/?WT.mc_id=IntuneProtect20150801)[![](../Image/Nav_Icons/WIT_Tile_W_RetireData.png)](https://technet.microsoft.com/library/mt313204.aspx/?WT.mc_id=IntuneRetire20150801)[![](../Image/Nav_Icons/WIT_Tile_W_TechnicalReference.png)](https://technet.microsoft.com/library/mt282239.aspx/?WT.mc_id=IntuneTR20150801)
![](../Image/Nav_Icons/WIT_Tile_Bar_Overview.png)

[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] is a cloud-based service that lets you manage mobile devices, PCs, and apps so your users can be productive while you protect your company's information.

Mobile device management (MDM) and computer management are the cornerstone of  the modern IT department. Today workers, staff and students are more mobile and engaged than ever. Your success depends upon delivering information where it's needed while ensuring that information is protected. You need to deploy apps, protect devices, ensure updates are in place, and provision email faster than ever while defending company information.

## Different ways to manage your devices with Microsoft Intune
You have several options for using Intune. This short video shows you how Intune fits into your existing network to help you manage devices and apps.

[![](../Image/IT_MDM_MAMOverview2.png)](https://youtu.be/kLi3uZ_pK-g)

Learn more about what Intune provides as:

-   **A standalone solution for device management**. As a cloud-based service, you manage devices and protect company data without the overhead of network infrastructure costs.

    Intune can manage iOS, Android, and Windows Phone devices, as well as Windows RT and Windows 8.1 and Windows 10 devices as mobile devices. If you're looking at [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] for a mobile device management (MDM) solution, review [Intune's MDM capabilities and features](https://technet.microsoft.com/library/dn600287.aspx).

    You can install the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client software on computers to enable management. Once a computer is managed you can deploy apps and software updates, manage Endpoint Protection and Windows Firewalls, provide remote assistance, and much more. See [a full list of computer management capabilities](http://technet.microsoft.com/library/dn646975.aspx).

    You can also use Intune to [deploy and manage apps](https://technet.microsoft.com/library/dn646965.aspx). App management helps you protect data from being shared outside of your business by restricting actions such as copy, cut, paste, and save-as between Intune-managed apps and personal apps. This data protection is built directly into many Microsoft mobile apps but you can [extend data protection to your existing line-of-business apps with the Intune App Wrapping Tool](https://technet.microsoft.com/library/dn878026.aspx). You can also establish secure content viewing with the [Intune Managed Browser](https://technet.microsoft.com/library/dn878029.aspx). To further protect corporate information, you can [selectively wipe managed apps and related data](https://technet.microsoft.com/library/mt313204.aspx) on devices that are unenrolled, no longer compliant, or lost, stolen, or retired from use.

-   **A cloud extension of Microsoft System Center 2012 Configuration Manager**. If you already use Configuration Manager to manage on-premises devices and are looking for a way to manage many of today's mobile devices, you can [use Intune as an extension of System Center 2012 Configuration Manager](https://technet.microsoft.com/library/dn957912.aspx#BKMK_HybridOfferings). Two key benefits of this option are a unified management experience for both on-premises and mobile device management, and scale. This hybrid implementation of Intune gives you the capacity to manage more than 50,000 devices.

-   **Part of your Microsoft Office 365 subscription**. If you have a commercial subscription to Office 365, you can use the Intune [mobile device management capabilities built into Office 365](https://technet.microsoft.com/library/dn957912.aspx#MDMOfferings). While this option is not as extensive as Intune standalone or Intune and Configuration Manager, you can still manage iOS, Android, and Windows Phone devices, create security policies, limit access to Office 365  email and documents on managed devices, and use selective wipe to remove Office 365 from managed devices.

-   **Part of the Microsoft Enterprise Mobility Suite**. Mobility is here to stay, and so is the cloud. Intune is a core component of the [Microsoft Enterprise Mobility Suite (EMS)](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx%20), a set of cloud-based services that provide threat detection, identity management  on top of the data protection and device management that Intune standalone delivers.

## Requirements for setting up Intune
Although Intune is a service, and thus relieves you of many infrastructure costs, you may still have some [network setup requirements](https://technet.microsoft.com/library/dn646950.aspx). For example, your firewall might, by default, block some of the network ports required by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].  Additionally, if you want to synchronize data from Exchange Server, there are also certain firewall exceptions you might have to make.

Other preparations to make as you [get ready to deploy Intune](https://technet.microsoft.com/library/dn646966.aspx) include:

-   setting up a company portal so users can enroll their mobile devices to be managed by Intune

-   understanding expected bandwidth usage

-   deciding whether to use the default **onmicrosoft.com** domain name or a domain name you own

## See Also
[Documentation for Microsoft Intune](../Topic/Documentation_for_Microsoft_Intune.md)

