---
# required metadata

title: Compare Windows PC management options
description: Enrollment of corporate-owned iOS devices by using the Apple Device Enrollment Program (DEP) or Apple Configurator
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/27/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 068a73bb-e6b3-44a6-8f6e-4cf7d455bbf3

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: owenyen
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Compare managing Windows PCs as computers or mobile devices

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Organizations can use Microsoft Intune to manage Windows PCs either as mobile devices with mobile device management (MDM) or as computers with the Intune software client.  Microsoft recommends that customers use the MDM management solution whenever possible. To help you better understand the differences between these options, however, the following chart compares the two management options.

|**Capability / Scenario** |**Windows as Computer**<br>Intune software client | **Windows as Mobile Device**<br>MDM |
|--------------|-------------------------------|-------------------------------|
|**Operating systems** |Windows 10, Windows 8+, Windows 7, Windows Vista | Windows 10+ |
|**Intune Portal support** |[Silverlight console](https://manage.microsoft.com)|[Azure portal](https://portal.azure.com) |
|**Conditional access**|Not available|Available <br>[What is conditional access?](https://docs.microsoft.com/intune-azure/conditional-access/what-is-conditional-access)|
|**Bulk enrollment**|Not available|Available <br>[Bulk enrollment for Windows devices](https://docs.microsoft.com/intune-azure/enroll-devices/bulk-enroll-windows)|
|**Device profiles**|Not available|Available <br>[What are Microsoft Intune device profiles?](https://docs.microsoft.com/intune-azure/configure-devices/what-are-device-profiles)|
|**Agentless enrollment**|Not available |Available<br>[Enroll Windows devices](https://docs.microsoft.com/intune-azure/enroll-devices/enroll-windows-devices)|
|**Software update management**| Windows Updates and Microsoft app updates<br>[Keep Windows PCs up to date with software updates](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)|Microsoft Store for Business for both Windows 10 and Microsoft apps updates<br> [Configure Windows Update for Business settings](https://docs.microsoft.com/intune-azure/configure-devices/how-to-configure-windows-update-for-business) |
|**Software license management**|Available <br>[Manage license agreements for Windows PC software](https://docs.microsoft.com/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)|Microsoft Store for Business (.appx apps only)<br>[Manage apps purchased from the Microsoft Store for Business](https://docs.microsoft.com/intune-azure/manage-apps/wsfb-apps)|
|**Inventory**|Available <br>[View hardware and software inventory for Windows PCs](https://docs.microsoft.com/intune/deploy-use/view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune)|Available <br>[How to monitor app information](https://docs.microsoft.com/intune/apps-monitor)<br>[What is device management](https://docs.microsoft.com/intune/device-management)|
|**Windows Firewall policy**|Available <br>[Help protect Windows PCs using Windows Firewall policies](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune) |Not available|
|**Anti-malware protection**|Endpoint Protection<br>[Help secure Windows PCs with Endpoint Protection](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)|Windows Defender<br>[Windows Defender settings](https://docs.microsoft.com/intune-azure/configure-devices/custom-for-windows-10#windows-defender-settings)|
|**Remote assistance** |TeamViewer<br>[Request and provide remote assistance for Windows PCs](https://docs.microsoft.com/intune/deploy-use/request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune)|Not available |
|**App deployment** | Not available for Microsoft Store for Business,<br>.exe, .appx, and multi-file .msi only<br>[Add apps for Windows PCs that run the Intune software client](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)|Available for Microsoft Store apps and line-of-business apps<br>[How to add Windows store apps](https://docs.microsoft.com/intune/store-apps-windows)<br>[How to add Windows line-of-business (LOB) apps](https://docs.microsoft.com/intune/lob-apps-windows)|
|**App protection**|Not available|Available <br>[What are app protection policies?](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-protection-policy)|
|**Health attestation**|Not available|Available|


### Advantages of MDM Windows PC management
Windows PC management with modern mobile device management has the following advantages:
- **Scalability** - MDM management scales with Intune cloud management. The Intune software client is limited to 7000 PCs.
- **Simplicity** - Uses modern management capabilities included in the operating system without relying on a downloaded software client
- **Consistency** - Your Windows PCs are managed like all other mobile devices in your organization
<!-- - **Cloud optimization** - -->
