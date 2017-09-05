---
# required metadata

title: Supported devices - Microsoft Intune
description: Lists supported device platforms and browsers for Intune device management
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/23/2017
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

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

This article is for system administrators responsible for device management in the enterprise. For help installing Intune on your phone, see [using managed devices to get work done](/intune-user-help/company-portal-frequently-asked-questions).

Before you start setting up Microsoft Intune, review the following requirements:

- [Supported devices and computers](#intune-supported-devices)
- [List of supported web browsers use Intune](#intune-supported-web-browsers)

You should also familiarize yourself with [Intune network bandwidth usage](network-bandwidth-use.md) ([Classic console](/intune-classic/get-started/network-bandwidth-use)) .

## Intune supported devices

You can manage the following devices using Intune mobile device management:

[!INCLUDE[mdm-supported-devices](./includes/mdm-supported-devices.md)]

Intune cannot be used to manage Windows Server operating systems.

### Windows PC software client

An [Intune software client](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) can be deployed and installed on Windows PCs as an alternate enrollment method. This functionality is only available using the Intune classic console. You can use the Intune software client to manage Windows 7 and later PCs with the exception of Windows 10 Home edition.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## Intune supported web browsers

Different administrative tasks require that you use one of the following administrative websites.

- [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Intune portal](https://portal.azure.com/)

The following browsers are supported for these portals:
- Microsoft Edge (latest version)
- Microsoft Internet Explorer 11
- Safari (latest version, Mac only)
- Chrome (latest version)
- Firefox (latest version)

### Intune classic portal

Intune classic-only features, such as Intune PC software client and integration with Mobile Threat Defense partners, are only available in the Intune classic portal (https://manage.microsoft.com). The Intune classic portal requires Silverlight browser support.

The following Silverlight browsers support the classic Intune console:
- Internet Explorer 10 or later
- Google Chrome (versions prior to version 42)
- Mozilla Firefox with Silverlight enabled [Learn more](https://go.microsoft.com/fwlink/?linkid=836872)

> [!Note]
> Microsoft Edge and mobile browsers are not supported for the Intune classic console because they do not support [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx).

Only users with service administrator permissions or tenant administrators with the global administrator role can sign in to this portal. To access the administration console, your account must have a license to use Intune and a sign-in status of **Allowed**.
