---
# required metadata

title: Supported devices - Microsoft Intune | Microsoft Docs
description: Lists supported device platforms and browsers for Intune device management
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/07/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: angrobe
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Supported devices and browsers

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

This article is for system administrators responsible for device management in the enterprise. For help installing Intune on your phone, see [using managed devices to get work done](https://docs.microsoft.com/intune/enduser/company-portal-frequently-asked-questions).

Before you start setting up Microsoft Intune, review the following requirements:

- [Supported devices and computers](#intune-supported-devices)
- [List of supported web browsers use Intune](#intune-supported-web-browsers)

You should also familiarize yourself with [Intune network bandwidth usage](network-bandwidth-use.md).

## Intune supported devices

You can manage the following devices using Intune mobile device management:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Intune cannot be used to manage Windows Server operating systems.

Intune device management provides [these capabilities](mobile-device-management-capabilities-in-microsoft-intune.md).

### Windows PC software client

An [Intune software client](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune) can be deployed and installed on Windows PCs as an alternate enrollment method. You can use the Intune software client to manage Windows 7 and later PCs with the exception of Windows 10 Home edition. Managing PCs with the client software provides [these capabilities](windows-pc-management-capabilities-in-microsoft-intune.md).

### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.

## Intune supported web browsers

Different administrative tasks require that you use one of the following administrative websites.

- [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune administrator console](https://admin.manage.microsoft.com/)

|Intune feature |Supported browsers|
|---------|---------|
|**Intune Admin console**     |  Internet Explorer 10 or later<br /><br />Google Chrome (versions prior to version 42)<br /><br />Mozilla Firefox with Silverlight enabled<br />**Note:** Mozilla will remove support for Silverlight effective March 2017. [Learn more](https://go.microsoft.com/fwlink/?linkid=836872). |
|**Office 365 Admin Portal**     |All browsers, including mobile browsers and managed browsers  |
|**Company Portal website**     |**On mobile devices:** use the default web browser for each supported platform   <br /><br />**On Windows PCs:** Internet Explorer 10 or later, or Microsoft Edge<br /><br />**On Mac OS X 10.9 or later:** Apple Safari    |

> [!Note]
> Microsoft Edge and mobile browsers are not supported for the admin console because they do not support [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx). The Intune console is moving from the Silverlight experience over a period of time; eventually, all of Intune's mobile device and application management features will be [made available in the new Microsoft Azure portal](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).


Only users with service administrator permissions or tenant administrators with the global administrator role can sign in to this portal. To access the administration console, your account must have a license to use Intune and a sign-in status of **Allowed**.

>[!div class="step-by-step"]

>[**Networking** &rarr;](network-bandwidth-use.md)  
