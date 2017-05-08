---
# required metadata

title: Compare Windows PC management options | Microsoft Docs
description: Enrollment of corporate-owned iOS devices by using the Apple Device Enrollment Program (DEP) or Apple Configurator
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/11/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 068a73bb-e6b3-44a6-8f6e-4cf7d455bbf3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: owenyen
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Compare managing Windows PC as computers or mobile devices

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Organizations can use Microsoft Intune to manage Windows PCs either as mobile devices via mobile device management (MDM) or as computers via the Intune software client.  Microsoft recommends customers use MDM whenever possible to take advantage of the growing modern management paradigm.  To help customers better understand the differences between these options, however, the following comparison contrasts the differences between the two management options.  

> [!NOTE]
> This comparison attempts to present how each approach addresses similar scenarios, the scenarios are rarely parallel. There are differences even if the scenario is addressed by both mechanisms.

|**Capability / Scenario** |**Windows as Computer**<br>Intune software client | **Windows as Mobile Device**<br>MDM|
|--------------|-------------------------------|-------------------------------|
|**Operating systems** |Windows 10, Windows 8+, Windows 7, Windows Vista | WIndows 10+, Windows 8.1 |
|**Intune Portal support** |Silverlight console only (https://manage.microsoft.com)|Azure portal (https://portal.azure.com) or Silverlight console (https://manage.microsoft.com)|
|**Software update management**| Windows Updates<br>[Keep Windows PCs up to date with software updates in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)|Windows Update for Business<br> [How to configure Windows Update for Business settings with Microsoft Intune](https://docs.microsoft.com/intune-azure/configure-devices/how-to-configure-windows-update-for-business) |
|**Windows Firewall policy**|Available <br>[Help protect Windows PCs using Windows Firewall policies in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune) |Not available|
|**Anti-malware protection**|Endpoint Protection<br>[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)|Windows Defender<br>[Windows Defender settings](https://docs.microsoft.com/intune-azure/configure-devices/custom-for-windows-10#windows-defender-settings)|
|**Remote assistance** |TeamViewer<br>[Request and provide remote assistance for Windows PCs](https://docs.microsoft.com/intune/deploy-use/request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune)|Not available |
|**Software license management**|Available <br>[Manage license agreements for Windows PC software in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)|Windows Store for Business<br>[How to manage apps you purchased from the Windows Store for Business with Microsoft Intune](https://docs.microsoft.com/intune-azure/manage-apps/wsfb-apps)|
|**App deployment** | Not available for Windows Store for Business<br>.exe and multi-file .msi only<br>[Add apps for Windows PCs that run the Intune software client](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)|Available for Windows store apps, not available for Windows apps (single file .msi only)<br>[How to add Windows store apps to Microsoft Intune](https://docs.microsoft.com/intune-azure/manage-apps/windows-store-app)|
|**App management**|Not available|Available <br>[What are app protection policies?](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-protection-policy)|
|**Inventory**|Available [View hardware and software inventory for Windows PCs](https://docs.microsoft.com/intune/deploy-use/view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune)|Not available|
|**Conditional access**|Not available|Available <br>[What is conditional access?](https://docs.microsoft.com/intune-azure/conditional-access/what-is-conditional-access)|
|**Bulk enrollment**|Not available|Available <br>[Bulk enrollment for Windows devices](https://docs.microsoft.com/intune-azure/enroll-devices/bulk-enroll-windows)|
|**Device profiles**|Not available|Available <br>[What are Microsoft Intune device profiles?](https://docs.microsoft.com/intune-azure/configure-devices/what-are-device-profiles)|
