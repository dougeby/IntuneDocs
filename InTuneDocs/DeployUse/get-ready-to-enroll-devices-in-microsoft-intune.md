---
# required metadata

title: Get ready to enroll devices in Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Get ready to enroll devices in Microsoft Intune
To let employees enroll mobile devices (including Android, iOS, and Windows Phone, and Windows PCs) with Intune you must enable device enrollment. To allow enrollment you must set a mobile device management authority, configure the Intune Company Portal, assign licenses, and enable enrollment for the device platform.

## <a name="BKMK_Set_MDM_Authority"></a>Set mobile device management authority
The MDM authority defines the  management service with permission to manage a set of devices. Options for MDM authority include Intune by itself and Configuration Manager with Intune. If you set Configuration Manager as the management authority, no other service can be used for mobile device management.

>[!IMPORTANT]
> Consider carefully whether you want to manage mobile devices using Intune-only (online service) or System Center Configuration Manager with Intune (on-premises software solution in conjunction with online service). After you set the mobile device management authority, it cannot be changed.



1.  In the [Microsoft Intune administration console](http://manage.microsoft.com) click **Admin** &gt; **Mobile Device Management**.

2.  In the **Tasks** list, click **Set Mobile Device Management Authority**. The **Set MDM Authority** dialog box opens.

    ![Set MDM authority dialog box](../media/intune-mdm-authority.png)

3.  Intune requests confirmation that you want Intune as your MDM authority. Check the box and then click **Yes** to use Microsoft Intune to manage mobile devices.

## Configure the Intune Company Portal and assign licenses
The Intune Company Portal helps users access company resources such as apps, find helpdesk information, and enroll and un-enrolled devices. Before enrolling devices you should [configure the Company Portal](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-7). You must also [assign user licenses](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-4) to allow access to Intune.

## Set up device management
After setting up the MDM authority, you need to set up device management for the operating systems your organization wants to support. The steps required to set up device management vary by operating system. For example, Android OS does not require you to do anything in the Intune administration console. On the other hand, Windows and iOS require a trust relationship between devices and Intune to allow management.

> [!div class="op_single_selector"]
- [Set up Android management with Microsoft Intune](set-up-android-management-with-microsoft-intune.md)
- [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Set up Windows Phone management with Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md)
- [Set up Windows device management with Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md)

You can also:
 - Use the [device enrollment manager account](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) to enroll many devices
 - [Specify company-owned devices using IMEI numbers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) to help enroll devices and target policy
