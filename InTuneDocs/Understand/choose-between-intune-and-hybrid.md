---
title: Choose between Intune standalone and SCCM
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:
author: robstackmsft
---
# Choose between Intune standalone and Intune integrated with Configuration manager

|You might choose [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] standalone if:|You might choose [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] + Configuration Manager if:|
|----------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
|You want to manage mobile devices<br /><br />You want to manage computers that are not joined to a domain<br /><br />You have fewer than 50,000 devices to manage<br /><br />You have no (or limited) on-premises IT infrastructure<br /><br />[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] does not require on-premises IT infrastructure, however it can use the capabilities of Exchange ActiveSync or Active Directory Domain Services if you have those installed.<br /><br />You have a mobile or highly distributed workforce. Cloud-based device management lets you manage mobile devices and computers anywhere in the world.|You want to manage computers joined to a domain.<br /><br />You want to manage servers.<br /><br />You want to manage computers with the Configuration Manager client, Mac computers, Linux and UNIX server, and mobile devices enrolled with Intune from the same console.<br /><br />You have more than 50,000 devices to manage.<br /><br />You have on-premises IT infrastructure in place, or plan to deploy such infrastructure. In this configuration, the device and resource management experience is fully unified.<br /><br />User names and passwords are synchronized, providing users with a single account that they use to access company resources, whether from a domain-joined computer or from a mobile device.|

## Detailed comparison of capabilities
The following tables compare the device and app management capabilities available to you when you use [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] alone, Configuration Manager alone, or a solution that uses both products.

To learn more about using Configuration Manager with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], see [Manage Mobile Devices with Configuration Manager and Microsoft Intune](http://msdn.microsoft.com/en-us/library/2c6bd0e5-d436-41c8-bf38-30152d76be10).

### Device support

|Platform|[!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]|System Center 2012 Configuration Manager SP2|System Center 2012 Configuration Manager SP2 and [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]|
|------------|---------------------------------------------------------|------------------------------------------------|--------------------------------------------------------------------------------------------------------|
|Microsoft Windows|Yes|Yes|Yes|
|Microsoft Windows Server|No|Yes|Yes|
|Windows Phone|Yes|No|Yes|
|Windows RT|Yes|No|Yes|
|iOS|Yes|No|Yes|
|Android and Samsung KNOX|Yes|No|Yes|
|Mac OS X|Yes|Yes|Yes|
|Unix/Linux servers|No|Yes|Yes|

### Product capabilities
> [!TIP]
> Where indicated with (R2), the listed capability requires Microsoft System Center 2012 R2 Configuration Manager or later.

|Scenario|[!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]|System Center 2012 Configuration Manager SP2|System Center 2012 Configuration Manager SP2 and [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]|
|------------|---------------------------------------------------------|------------------------------------------------|--------------------------------------------------------------------------------------------------------|
|**Compliance Settings**||||
|Deploy and customize Windows PC device configuration settings (e.g., WMI, registry)|No|Yes|Yes|
|Deploy and customize Mac OS X configuration settings|Yes|Yes|Yes|
|Deploy configuration settings to mobile devices.|Yes|Yes|Yes|
|Deploy custom mobile device settings (such as OMA-URI and Apple Configurator)|Yes|Yes|Yes|
|**Deployment**||||
|Deploy apps to devices and Windows PCs|Yes|Yes|Yes|
|Deploy Windows operating systems|No|Yes|Yes|
|**Security and Privacy**||||
|Manage Windows software updates|Yes|Yes|Yes|
|Monitor malware on Windows PCs with Endpoint Protection|Yes|Yes|Yes|
|**Administration and Reporting**||||
|Monitor and report on how often software is being used with software metering|No|Yes|Yes|
|Hardware and software inventory|Yes|Yes|Yes|
|Extend hardware and software inventory for Windows PCs|No|Yes|Yes|
|Use role-based administration and reporting to control who has access to product capabilites|No|Yes|Yes|
|Run reports for Windows PCs and enrolled mobile devices from the same console|No|No|Yes|
|Customize existing reports, and write your own reports using SQL Server Reporting Services|No|Yes|Yes|
|**Data Protection for mobile devices**||||
|Deploy security settings to mobile devices|Yes|Yes|Yes|
|Remote wipe|Yes|Yes|Yes|
|Remote lock|Yes|Yes|Yes|
|Passcode reset|Yes|Yes|Yes|
|**Company resource access**||||
|Email profiles|Yes|Yes (R2)|Yes (R2)|
|Wi-Fi profiles|Yes|Yes (R2)|Yes (R2)|
|VPN profiles|Yes|Yes (R2)|Yes (R2)|
|Certificate profiles|Yes|Yes (R2)|Yes (R2)|
|Manage access to Exchange email and SharePoint with conditional access|Yes|Yes|Yes|
|Mobile application management|Yes|Yes|Yes|
|App compliance policies (compliant and noncompliant apps)|Yes|Yes|Yes|
|Kiosk mode|Yes|Yes|Yes|
|Managed Internet browser policy|Yes|Yes|Yes|
|**Automation**||||
|Use PowerShell to automate operations|No|Yes|Yes|
