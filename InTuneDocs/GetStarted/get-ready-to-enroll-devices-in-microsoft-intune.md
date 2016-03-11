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
To let employees use company resources on mobile devices (including Android, iOS, and Windows Phone) you must enable device enrollment, the process that brings devices into management. To do this you must first set [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] as your mobile device authority and enable enrollment for the device's operating system. Computers running Windows 10 and Windows 8.1 can also be managed as mobile devices or you can manage them [using Intune client software](manage-windows-pcs-with-microsoft-intune.md).

## Enable mobile device enrollment
To enable mobile device management (MDM) enrollment you must set the *mobile device management authority*. The MDM authority defines the  management service with permission to manage a set of devices. Options for MDM authority include [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], Configuration Manager with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], or Office 365 MDM solutions. Office 365 and Intune can be used in tandem to manage mobile devices. If System Center Configuration Manager is set as the management authority, no other service can be used for mobile device management. To get started, [set your Intune as the MDM authority](set-mobile-device-management-authority-and-configure-microsoft-intune.md).

## Set up device management
After you set the MDM authority, you enable enrollment for the operating systems your organization wants to support. Certain mobile device operating systems (for example Windows and iOS) require a trust relationship between devices and [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] to allow management.

Select from the following device platform options to learn more:

> [!div class="op_single_selector"]
- [Set up Android management with Microsoft Intune](set-up-android-management-with-microsoft-intune.md)
- [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Set up Windows Phone management with Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md)
- [Set up Windows device management with Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md)

## Enroll corporate-owned devices
Organizations can use Intune to manage large numbers of mobile devices with a single user account called a [device enrollment manager account](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). After creating a device enrollment manager account, that account can be used to enroll more than the standard five devices allowed by default to normal users. After creating a device enrollment manager account, you will be ready to enroll company owned devices on behalf of your end users.

Corporate-owned device (COD) management of iOS devices with Microsoft Intune is an alternative to enrollment with the Company Portal app. Intune supports the enrollment of corporate-owned iOS devices using the Apple Device Enrollment Program (DEP) or the [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) tool running on a Mac computer.

You can enroll corporate-enrolled iOS devices in three ways:

-   **Device Enrollment Program (DEP)** – Deploys an enrollment profile that enrolls the device “over the air” and can include setup assistant options for the device. Devices enrolled through DEP cannot be un-enrolled by users.

-   **Setup Assistant Enrollment** – Factory resets the device and prepares it for setup by the device’s new user. This method supports DEP or Apple Configurator enrollments.

-   **Direct Enrollment** – Creates an Apple Configurator-compliant file for use during device preparation. The enrolled device isn’t factory reset. This method cannot be used for DEP enrollment. This method only works if user affiliation is set to "No user affinity."

> [!NOTE]
> Devices enrolled with these methods require the Intune Company Portal app to enable certain Intune capabilities such as [Conditional Access](manage-access-to-email-and-sharepoint-with-microsoft-intune.md) and [Mobile Application Management](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md). Additional steps may be necessary to properly configure the Company Portal app. [Learn more](https://blogs.technet.microsoft.com/intunesupport/2015/12/28/update-to-company-portal-brings-benefits-to-corporate-owned-ios-devices/)

Select from the following corporate device enrollment options to learn more:

> [!div class="op_single_selector"]
- [Apple device enrollment program (DEP) for iOS](iOS-device-enrollment-program.md)
- [Apple Configurator Setup Assistant for iOS](iOS-setup-assistant-enrollment.md)
- [Apple Configurator direct Enrollment for iOS](iOS-direct-enrollment.md)
- [Specify company-owned devices using IMEI numbers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)
