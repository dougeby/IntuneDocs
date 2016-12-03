---
# required metadata

title: Supported mobile devices and browsers | Microsoft Intune
description: Lists supported devices and the browsers that can run Intune
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/01/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: aeeccfa4-0f14-447e-a3df-c8435c8a4bb2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Supported devices and browsers for Intune

As an Intune administrator, you can manage a range of devices from a browser. Enrolling devices provides [these capabilities](/Intune/get-started/choose-how-to-manage-devices). This topic provides:

- [Lists of supported device platforms](#intune-supported-devices)
- [List of browsers use Intune](#intune-supported-web-browsers)

## Intune supported devices

You can manage the following devices using Intune mobile device management:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Intune cannot be used to manage Windows Server.

### Windows PC software client

Instead, the [Intune software client](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune) can manage Windows PCs running Windows 7 and later, except Windows 10 Home. Managing PCs with the client software provides [these capabilities](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

### Exchange ActiveSync management

You can also manage devices from the Intune console with [Exchange ActiveSync](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune). This third option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.

## Intune supported web browsers

Different administrative tasks require you to use one of the following administrative websites.

- [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune administrator console](https://admin.manage.microsoft.com/)

|Intune feature |Supported browsers|
|---------|---------|
|Intune Admin console     |  Internet Explorer 10 or later<br /><br />Google Chrome (versions prior to version 42)<br /><br />Mozilla Firefox with Silverlight enabled<br />**Note:** Mozilla will remove support for Silverlight effective March 2017. [Learn more](https://go.microsoft.com/fwlink/?linkid=836872). |
|Office 365 Admin Portal     |All browsers, including mobile browsers and managed browsers  |
|Company Portal website     |**On mobile devices:** use the default web browser for each supported platform   <br /><br />**On Windows PCs:** Internet Explorer 10 or later, or Microsoft Edge<br /><br />**On Mac OS X 10.9 or later:** Apple Safari    |

> [!Note]
> Microsoft Edge and mobile browsers are not supported for the admin console because they do not support [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx). The Intune console is moving from the Silverlight experience over a period of time; eventually, all of Intune's mobile device and application management features will be [made available in the new Microsoft Azure portal](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).


Only users with service administrator permissions or tenant administrators with the global administrator role can sign in to this portal. To access the administration console, your account must have a license to use Intune and a sign-in status of **Allowed**.
