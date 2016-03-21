---
title: What's new - January 2016 | Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid: 
author: Lindavr
---
# What's new in Microsoft Intune

## January 2016

### Take advantage of Windows 10 features
* **Conditional access with Health Attestation Service**
Intune administrators can now view the status of Windows 10 Device Health Attestation in the Intune Admin console. Device health attestation lets the administrator ensure that client computers have trustworthy BIOS, TPM, and boot software configurations. To support device health attestation, client devices must be running Windows 10 with TPM 2 enabled. Device health attestation displays the number of devices enabled for each of the following:
	* Early-launch antimalware
	* BitLocker
	* Secure Boot
	* Code Integrity

	Read [Manage device compliance policies for Microsoft Intune](manage-device-compliance-policies-for-microsoft-intune.md) for more details on the device health setting, collected data points, and the health attestation report. The [HAS service details](https://msdn.microsoft.com/en-us/library/dn934876.aspx) explains the service in depth.

* **Windows 10 Passport for Work Policy and certificate management**
With Intune, you can [integrate with Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md), which is an alternative sign-in method for Windows 10 that uses Active Directory or an Azure Active Directory account to replace a password, smart card, or virtual smart card. Passport lets you use a user gesture to log in instead of a password. A user gesture might be a simple PIN, biometric authentication such as Windows Hello, or an external device such as a fingerprint reader.

* **VPN for specific apps**
You can select apps that automatically connect to your corporate network over VPN. Create the list of apps when you set up the VPN profile, as described in Help users connect to their work using VPN profiles with Microsoft Intune.

* **Windows 10 Full Wipe support**
You can now issue a remote full wipe of Windows 10 desktop devices enrolled in Intune through the Intune admin console. Windows 10 full wipe does a factory reset of the device.


### Apple Volume Purchase Program (VPP) update
Intune can now help you [manage apps you purchased through the Apple Volume Purchase Program (VPP) for Business](manage-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md). This includes synchronizing license information between Apple and Intune, and tracking how many copies of each app you have deployed.

### Use IMEI numbers to identify corporate-owned devices
You can now [import international mobile equipment identity (IMEI) numbers](specifiy-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) for mobile device platforms that have an IMEI number to help identify corporate-owned mobile devices. Once enrolled in Intune, devices with imported IMEI numbers are tagged as Corporate, which can be used for applying policies that are different than those applied to personally owned devices.

### More apps are now compatible with Intune MAM policies
Additional apps from Microsoft partners are now compatible with Intune mobile application management (MAM) policies (for devices managed by Intune):
* Box for EMM (from Box Inc) – iOS only
* Adobe Reader (from Adobe) – Android only
* Foxit PDF Reader (from Foxit Corporation) – iOS and Android

For a complete list see [Microsoft apps you can use with Microsoft Intune mobile application management policies](microsoft-apps-you-can-use-with-microsoft-intune-mobile-application-management-policies.md). For a list of compatible partner apps, see the [Microsoft Intune application partners](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) page.

## What’s coming
Keep informed about upcoming developments for Intune with the [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### IE9 support ending in January
Starting in February, 2016, Internet Explorer 9 will no longer be supported as an official browser for accessing the Microsoft Intune company portal website, Intune account portal, and Intune administration console. You will need to migrate to Internet Explorer 10 or later.

### Protect your company data using enterprise data protection (EDP)
When managing Windows 10 devices, Intune will be able to create and deploy configuration policies for Windows 10 enterprise data protection (EDP). EDP can help you restrict and/or alert you to company data sharing. Intune EDP policies will manage the list of apps protected by EDP, enterprise network locations, protection level, and encryption settings. To opt-in to receive preview builds of Windows, consider joining the [Windows Insider Program](https://insider.windows.com/).

> [!NOTE]
> Enterprise data protection is currently being tested with a number of enterprise customers, and will become available to Windows Insiders soon.

### See also
* [Start using Microsoft Intune](start-using-microsoft-intune.md)
* [Microsoft Intune TechNet Library](http://go.microsoft.com/fwlink/?LinkID=247636)
* [Microsoft Intune Product Information](http://go.microsoft.com/fwlink/?LinkID=249135)
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
