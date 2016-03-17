---
title: Get ready to enroll devices in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40
author: NathBarn
---
# Get ready to enroll devices in Microsoft Intune
To let employees access company resources on mobile devices (including Android, iOS, and Windows Phone) with Intune you must enable device enrollment. Apart from managing mobile devices that use iOS, Android, or Widows, Intune also enables you to manage computers running Windows 10 and Windows 8.1 as mobile devices; alternately, you can manage them [using Intune client software](manage-windows-pcs-with-microsoft-intune.md).

## <a name="BKMK_Set_MDM_Authority"></a>Set mobile device management authority
The MDM authority defines the  management service with permission to manage a set of devices. Options for MDM authority include [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] and Configuration Manager with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. If you set Configuration Manager as the management authority, no other service can be used for mobile device management.

>[!IMPORTANT]
> Consider carefully whether you want to manage mobile devices using Intune-only (online service) or System Center Configuration Manager with Intune (on-premises software solution in conjunction with online service). After you set the mobile device management authority, it cannot be changed. If you're unsure of your options, see [Ways to do enterprise mobility](../Topic/Ways%20to%20do%20enterprise%20mobility.md).



1.  In the [Microsoft Intune administration console](http://manage.microsoft.com) click **Admin** &gt; **Mobile Device Management**.

2.  In the **Tasks** list, click **Set Mobile Device Management Authority**. The **Set MDM Authority** dialog box opens.

    ![](../Media/Intune-MDM-Authority.png)

3.  Intune requests confirmation that you want Intune as your MDM authority. Check the box and then click **Yes** to use Microsoft Intune to manage mobile devices.

## Configure the Intune Company Portal
The Intune Company Portal helps users access company resources such as apps, find helpdesk information, and enroll and un-enrolled devices. Before enrolling devices you should [configure the Company Portal app](set-mobile-device-management-authority-and-configure-microsoft-intune.md).

## Set up device management
After setting up the MDM authority, you need to set up device management for the operating systems your organization wants to support. The steps required to set up device management vary by operating system. For example, Android OS does not require you to do anything in the Intune administration console. On the other hand, Windows and iOS require a trust relationship between devices and [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] to allow management.

- [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Set up Windows Phone management with Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md)
- [Set up Windows device management with Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md)

You can also:
 - Use the [device enrollment manager account](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) to enroll many devices allowed
 - [Specify company-owned devices using IMEI numbers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) to help enroll devices and target policy
