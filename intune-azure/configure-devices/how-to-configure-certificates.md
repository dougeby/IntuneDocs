---
# required metadata

title: How to configure certificates with Microsoft Intune | Microsoft Docs
description: Description.
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# How to configure certificates with Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

When you give users access to corporate resources through VPN, Wi-Fi, or email profiles, you can secure the access by using a certificate that is installed on each user device. The high-level workflow is as follows:

1. Ensure you have the right certificate infrastructure in place.
2. Install a root certificate or an intermediate Certification Authority (CA) certificate on each device so that the device recognizes the legitimacy of your CA. To do this, create and deploy a **trusted certificate profile**. When you deploy this profile, the devices that you manage with Intune will request and receive the root certificate. You have to create a separate profile for each platform. Trusted certificate profiles are available for these platforms:
	- iOS 8.0 and later
	- Mac OS X 10.9 and later
	- Android 4.0 and later
	<!--Android for Work --->
	- Windows 8.1 and later
	- Windows Phone 8.1 and later
3. Create certificate profiles so that devices request a certificate to be used for authentication of VPN, Wi-Fi, and email access. You can create and deploy a **PKCS** or a **SCEP** certificate profile for devices running these platforms:
	- iOS 8.0 and later
	- Android 4.0 and later
	- Android for Work
	- Windows 10 (desktop and mobile) and later

	You can only use a SCEP certificate profile with these platforms:
	- Mac OS X 10.9 and later
	- Windows Phone 8.1 and later

You must create a separate profile for each platform. When you create the profile, associate it with the trusted root certificate profile that you've already created.

### Notes

- If you don't have an Enterprise Certification Authority, you must create one.
- If you decide, based on your device platforms, to use the Simplified Certificate Enrollment Protocol (SCEP) profile, you'll also need to configure a Network Device Enrollment Service (NDES) server.
- Whether you plan to use SCEP or .PFX profiles, you must download and configure the Microsoft Intune Certificate Connector.

## Before you start


### If you will use SCEP certificates

Complete the necessary prerequisites in [Certificate infrastructure for SCEP](/intune-azure/configure-devices/configure-certificate-infrastructure-for-scep).

### If you will use PFX certificates

Complete the necessary prerequisites in [Certificate infrastructure for PFX](/intune-azure/configure-devices/configure-certificate-infrastructure-for-pfx).

## Create a trusted certificate profile



## Create a PKCS certificate profile



## Create a SCEP certificate profile