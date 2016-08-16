---
# required metadata

title: Choose how to manage devices | Microsoft Intune
description: Learn about the various ways you can enroll and manage devices.
keywords:
author: robstackmsft
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: angrobe
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Choose how to manage devices
Intune lets you manage a range of devices by *enrolling* them into the service. Users can then use a *company portal* to perform a range of operations such as enrolling their device, browsing and installing apps, making sure their device is compliant with company policies, and contacting their IT support.

## Ways to manage mobile devices
Intune can manage the following device platforms:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

> [!NOTE]
> If you previously enrolled devices running an earlier version of iOS than the supported version, the devices will remain enrolled. Check documentation to confirm the feature supports that version of iOS.

Intune can manage users' devices, popularly known as "bring your own device" (BYOD). It can also manage company-owned devices including scenarios where the company provides a list of devices users may choose from, known as "choose your own device" (CYOD).

### Enrolling devices into management
For mobile device operating systems including iOS, Android and Windows Phone, you must always enroll devices. How you enroll devices depends on your organization's needs:

|Enrollment type|BYOD|CYOD|Shared device with manager account|Shared device without a user account|
|-------------------|--------|--------|--------------------------------------|----------------------------------------|
|**Description**|Personal device enrolled using Microsoft Intune|Corporate-owned device for single user|Corporate-owned device managed using a manager account shared by many users|Corporate-owned user-less device used by many users.|
|**Device’s user**|Owner|Assigned user|No user-specific account|No specific user|
|**Who enrolls?**|Owner|Administrator|Device Manager|Anyone|
|**Who un-enrolls?**|Owner or administrator|Platform |Administrator or user|Administrator or user|
|**Who can reset?**|Owner or administrator|Administrator|Administrator|Administrator|

For additional guidance, see [choose how to enroll mobile devices](/intune/get-started/choose-how-to-enroll-devices1.md).

> [!NOTE]
> See [Mobile device management capabilities](mobile-device-management-capabilities-in-microsoft-intune.md) for a full list of the capabilities that enrolling devices gives you.

## Ways to manage Windows PCs
Intune can manage Windows Vista and later Windows PCs using the Intune computer client. However, for Windows PCs, you can choose between enrolling them or installing the Intune PC client software which offers a few capabilities not available when you enroll devices. In most scenarios, you will enroll your Windows device with Intune which provides a greater set of capabilities than the computer client.

Consider using the Intune computer client when you want to:

- Use any of the Microsoft Intune computer client enabled capabilities to manage your Windows PCs
- Manage a Windows PC that runs an operating system that is not supported for enrollment

> [!NOTE]
> See [Windows PC management capabilities](windows-pc-management-capabilities-in-microsoft-intune.md) for a full list of the capabilities that installing the Intune computer client on supported Windows PCs gives you.

## Exchange ActiveSync management
You can also manage devices by using Exchange ActiveSync. This requires you to install the On-Premises Connector or use the built-in Service to Service Connector to connect to your Exchange Server.

To learn about the hardware and software requirements to install the On-Premises Connector, see [Requirements for the On-Premises Connector](/intune/deploy-use/intune-on-premises-exchange-connector#requirements-for-the-on-premises-connector).

To learn about using the On-Premises Connector or Service to Service Connector with Exchange, see [Mobile device management with Exchange ActiveSync and Microsoft Intune](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).



## Next steps
Now you've discovered some of the capabilities you can use when you enroll your devices with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Next, you'll need to [enroll your devices](/intune/deploy-use/enroll-devices-in-microsoft-intune). After you have enrolled your devices, you can take advantage of all of the capabilities you've read about in this topic. <!--lindavr: There's a logical flaw in our "get to know/get started" content. You can take the path in this topic or you can take the path in the What to know before your get started topic. And they don't cover the same ground. -->
