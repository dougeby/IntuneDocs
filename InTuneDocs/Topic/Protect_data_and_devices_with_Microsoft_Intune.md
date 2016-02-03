---
title: Protect data and devices with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
author: Lindavr
---
# Protect data and devices with Microsoft Intune
[![](../Image/Nav_Icons/WIT_Tile_W_Overview.png)](https://technet.microsoft.com/library/dn646960.aspx/?WT.mc_id=IntuneOverview20150801)[![](../Image/Nav_Icons/WIT_Tile_W_GetStarted.png)](https://technet.microsoft.com/library/dn646953.aspx/?WT.mc_id=IntuneGS20150801)[![](../Image/Nav_Icons/WIT_Tile_W_EnrollDevices.png)](https://technet.microsoft.com/library/dn646962.aspx/?WT.mc_id=IntuneEnroll20150801)[![](../Image/Nav_Icons/WIT_Tile_W_ManageDevices.png)](https://technet.microsoft.com/library/mt313202.aspx/?WT.mc_id=IntuneConfig20150801)[![](../Image/Nav_Icons/WIT_Tile_W_ManageApps.png)](https://technet.microsoft.com/library/dn646965.aspx/?WT.mc_id=IntuneDeploy20150801)![](../Image/Nav_Icons/WIT_Tile_W_ProtectResourcesHighlight.png)[![](../Image/Nav_Icons/WIT_Tile_W_RetireData.png)](https://technet.microsoft.com/library/mt313204.aspx/?WT.mc_id=IntuneRetire20150801)[![](../Image/Nav_Icons/WIT_Tile_W_TechnicalReference.png)](https://technet.microsoft.com/library/mt282239.aspx/?WT.mc_id=IntuneTR20150801)[![](../Image/Nav_Icons/WIT_Tile_W_Troubleshooting.png)](https://technet.microsoft.com/library/mt345521.aspx)
![](../Image/Nav_Icons/WIT_Banner_ProtectResources.png)

After you have provisioned and configured your devices, you'll want to make sure that they are *protected against data loss* and other threats. Here are common user scenarios that might present a danger to your network and data and how you can protect against them.

## Protect  data in email and SharePoint
Email is what employees want to get first on their device.  Because email often contains critical company data, you'll want to make sure that the device is secure. For example, if the device is not secured by a passcode, and it is stolen, the thief can read all company email on the device.

[Manage access to email and protect corporate data on SharePoint Online ](https://technet.microsoft.com/library/dn818907.aspx) using Intune's capabilities to set access polices  like requiring a  *passcode* or *data encryption*.   You can also deny access if the device has been *jailbroken or rooted*.

Microsoft offers the Enterprise Mobility Suite (EMS), a comprehensive solution for identity, mobile device management, app management, and data protection. EMS provides a layered security model which allows your IT department to manage access to email, data, and corporate applications from almost any device. The [Architecture guidance for protecting company email and documents](../Topic/Architecture_guidance_for_protecting_company_email_and_documents.md) topic discusses the solution overall, and [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] capabilities in detail. The [Learn how to deploy a solution for protecting company email and documents](../Topic/Learn_how_to_deploy_a_solution_for_protecting_company_email_and_documents.md) topic has step by step instructions on how to deploy the solution.

## Additional layer of protection with multi-factor authentication
[Multi-factor authentication (MFA)](https://technet.microsoft.com/library/dn889751.aspx) is a more secure way of authenticating the users of Windows and Windows Phone devices on the network.  With MFA, users need to confirm their identity beyond username and password, through a phone call, or text message.

## Control Microsoft Passport settings on devices with Microsoft Intune
[!INCLUDE[wit_nextref](/Token/wit_nextref.xml)] lets you integrate with [Microsoft Passport for Work](Control_Microsoft_Passport_settings_on_devices_with_Microsoft_Intune.md) which is an alternative sign-in method that uses Active Directory, or an Azure Active Directory account to replace a password, smart card, or virtual smart card.

## See Also
[Documentation for Microsoft Intune](../Topic/Documentation_for_Microsoft_Intune.md)

