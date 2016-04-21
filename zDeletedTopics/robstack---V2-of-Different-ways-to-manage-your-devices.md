---
title: robstack - V2 of Different ways to manage your devices
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e4fc05d3-4b57-4853-9908-85f90e520ac0
author: robstackmsft
---
# robstack - V2 of Different ways to manage your devices
Microsoft provides several options for managing your mobile devices. Use the information in this topic to help you decide which works best for your business needs.

## <a name="BKMK_MDMOfferings"></a>Decide between Intune and MDM for Office 365

|Consideration|MDM for Office 365|[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)]|
|-----------------|----------------------|---------------------------------------------------------|
|Cost|Included with many [Office 365 commercial subscriptions](http://products.office.com/business/enterprise-productivity-tools).|Requires a [paid subscription for Microsoft Intune](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/Purchasing.aspx) or can be purchased with the [Enterprise Mobility Suite](http://www.microsoft.com/en-us/server-cloud/products/enterprise-mobility-suite/Purchasing.aspx).|
|How you manage devices|Manage devices using the [Office 365 admin center](https://support.office.com/article/About-the-Office-365-admin-center-58537702-d421-4d02-8141-e128e3703547).|If you use [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] by itself, you manage devices using the [Intune admin console](https://technet.microsoft.com/library/dn646966.aspx).<br /><br />If you integrate Intune with System Center 2012 Configuration Manager, you use the Configuration Manager console to manage devices on-premises and in the cloud.|
|Devices you can manage|Cloud-based management for:<br /><br />-   iOS<br />-   Android<br />-   Windows Phone|Cloud-based management for:<br /><br />-   iOS<br />-   Android<br />-   Windows Phone<br />-   Windows PCs|
|Key capabilities|-   Ensure that Office 365 corporate email and documents can be accessed only on phones and tablets that are managed by your company and that are compliant with your IT policies.<br />-   Set and manage security policies, like device level pin lock and jailbreak detection, to help prevent unauthorized users from accessing corporate email and data on a device when it is lost or stolen.<br />-   Remove Office 365 company data from an employee’s device while leaving their personal data in place.<br /><br />For the latest information about Office 365 MDM capabilities, see [capabilities of Built-in Mobile Device Management for Office 365](https://technet.microsoft.com/library/ms.o365.cc.devicepolicysupporteddevice.aspx).|MDM for Office 365 capabilities, plus:<br /><br />-   Help users securely access corporate resource with certificates, Wi-Fi, VPN, and email profiles.<br />-   Enroll and manage collections of corporate-owned devices, simplifying policy and app deployment.<br />-   Deploy your internal line-of-business apps and apps in stores to users.<br />-   Enable your users to securely access corporate information using the Office mobile and line-of business apps they know, while ensuring security of data by restricting actions like *copy*, *cut*, *paste*, and *save as*, to only those apps managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].<br />-   Enable secure web browsing using the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] Managed Browser app.<br />-   Manage PC's from the cloud with no infrastructure required using [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], or connect [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to [!INCLUDE[cm5short](../Token/cm5short_md.md)] to manage all of your devices including PCs, Macs, Linux and UNIX servers, and mobile devices from a single management console.|
If you've decided that Intune is the best solution for you, then continue to step 2, where you'll decide which configuration is right for you. If you've decided to use Office 365 MDM, continue to [Office 365 commercial subscriptions](http://products.office.com/business/enterprise-productivity-tools)

## <a name="BKMK_HybridOfferings"></a>Choose between Intune standalone and Intune with Configuration Manager

|You might choose [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] stand-alone if:|You might choose [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] + Configuration Manager if:|
|----------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
|-   You want to manage mobile devices<br />-   You want to manage computers that are not joined to a domain<br />-   You have fewer than 50,000 devices to manage<br />-   You have no (or limited) on-premises IT infrastructure **Note:**     [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] does not require on-premises IT infrastructure, however it can use the capabilities of Exchange ActiveSync or Active Directory Domain Services if you have those installed.<br />-   You have a mobile or highly distributed workforce. Cloud-based device management lets you manage mobile devices and computers anywhere in the world.|-   You want to manage computers joined to a domain.<br />-   You want to manage servers.<br />-   You want to manage computers with the Configuration Manager client, Mac computers, Linux and UNIX server, and mobile devices enrolled with Intune from the same console.<br />-   You have more than 50,000 devices to manage.<br />-   You have on-premises IT infrastructure in place, or plan to deploy such infrastructure. In this configuration, the device and resource management experience is fully unified.<br />-   User names and passwords are synchronized, providing users with a single account that they use to access company resources, whether from a domain-joined computer or from a mobile device.|
**Detailed comparison of capabilities**

The following tables compare the device and app management capabilities available to you when you use [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] alone, Configuration Manager alone, or a solution that uses both products.

To learn more about using Configuration Manager with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], see [Manage Mobile Devices with Configuration Manager and Microsoft Intune](http://msdn.microsoft.com/en-us/library/2c6bd0e5-d436-41c8-bf38-30152d76be10).

### Device support

|Scenario|[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)]|System Center 2012 Configuration Manager SP2|System Center 2012 Configuration Manager SP2 and [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]|
|------------|---------------------------------------------------------|------------------------------------------------|--------------------------------------------------------------------------------------------------------|
|Microsoft Windows|Yes|Yes|Yes|
|Microsoft Windows Server|No|Yes|Yes|
|Windows Phone|Yes|No|Yes|
|Windows RT|Yes|No|Yes|
|iOS|Yes|No|Yes|
|Android and Samsung KNOX|Yes|No|Yes|
|Mac OS X|No|Yes|Yes|
|Unix/Linux servers|No|Yes|Yes|

### Comparison of capabilities
> [!TIP]
> Where indicated with (R2), the listed capability requires Microsoft System Center 2012 R2 Configuration Manager or later.

|Scenario|[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)]|System Center 2012 Configuration Manager SP2|System Center 2012 Configuration Manager SP2 and [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]|
|------------|---------------------------------------------------------|------------------------------------------------|--------------------------------------------------------------------------------------------------------|
|**Compliance Settings**||||
|Extensible Windows PC device configuration settings (e.g., WMI, registry)|No|Yes|Yes|
|Extensible Mac OS X configuration settings|No|Yes|Yes|
|Mobile device configuration settings|Yes|Yes|Yes|
|Custom mobile device settings (such as OMA-URI and Apple Configurator)|Yes|Yes|Yes|
|**Deployment**||||
|App deployment|Yes|Yes|Yes|
|Windows operating system deployment|No|Yes|Yes|
|**Security and Privacy**||||
|Software updates|Yes|Yes|Yes|
|Endpoint Protection|Yes|Yes|Yes|
|**Administration and Reporting**||||
|Software metering|No|Yes|Yes|
|Hardware and software inventory|Yes|Yes|Yes|
|Custom hardware and software inventory|No|Yes|Yes|
|Role-based administration and reporting|No|Yes|Yes|
|Unified reporting for cloud and corporate-connected devices|No|No|Yes|
|Cloud-based reporting|Yes|No|No|
|Custom reports|No|Yes|Yes|
|**Data Protection for mobile devices**||||
|Security settings|Yes|Yes|Yes|
|Remote wipe|Yes|Yes|Yes|
|Remote lock|Yes|Yes|Yes|
|Passcode reset|Yes|Yes|Yes|
|**Company resource access**||||
|Email profiles|Yes|Yes (R2)|Yes (R2)|
|Wi-Fi profiles|Yes|Yes (R2)|Yes (R2)|
|VPN profiles|Yes|Yes (R2)|Yes (R2)|
|Certificate profiles|Yes|Yes (R2)|Yes (R2)|
|Conditional access|Yes|Yes|Yes|
|Mobile application management|Yes|Yes|Yes|
|App compliance policies (compliant and noncompliant apps)|Yes|Yes|Yes|
|Kiosk mode|Yes|Yes|Yes|
|Managed Internet browser policy|Yes|Yes|Yes|
|**Automation**||||
|Use PowerShell to automate operations|No|Yes|Yes|

## See Also
[Introduction to Microsoft Intune](../Topic/Introduction-to-Microsoft-Intune.md)

