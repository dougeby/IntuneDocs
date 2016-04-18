---
# required metadata

title: Migrating to Intune - Configure Intune | Microsoft Intune
description:
keywords:
author: robmazz
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5909acd9-1598-4a25-843a-3bdd0c398eb4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Migrating to Intune - Configure Intune

>[!NOTE]
>This topic is part of a larger migration guide. If you'd like to start at the beginning of the guide, check out the [main topic](migrating-to-intune.md). To get a downloadable copy of this entire guide, visit the [TechNet Gallery](https://gallery.technet.microsoft.com/Migrating-to-Intune-ea439387).

Intune offers a very comprehensive set of mobile device and mobile application management features and capabilities. In this step, you’ll need to determine what configuration and compliance policies need to be configured to match the policies of your current enterprise mobility management solution. You’ll also need to fully understand the management process for these policies in the Intune architecture and how they manage and protect corporate resources.

## Device settings

Intune allows you to **configure a wide range of settings** that you can deploy to managed devices in your organization. These policies can be configured for each device platform type and can manage the most up-to-date device settings available.

## Email
[Email profiles](/Intune/DeployUse/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) in Intune allow you to create and deploy profiles that can automatically configure devices with appropriate email server information so that users can connect to their email mailbox. This helps users connect to the correct email server and prevents the need for users to have to try to remember email server names. Provisioning email profiles via Intune also allows you to remove email from devices as part of a selective wipe process. Intune can configure the native email for iOS, Samsung KNOX Android devices, and Windows Phone 8.0 or later.  Intune also supports the Outlook app for both iOS and Android devices as a MAM-enabled application.

## Wireless

To simplify connections to wireless networks, you can manage these connections using Intune [wireless profiles](/Intune/DeployUser/wi-fi-connections-in-microsoft-intune) that outline the specific settings devices need to configure in order to connect to the wireless network. This may include automatically configuring a custom network name, network Service Set Identifier (SSID), security settings, network proxy, and whether or not the device should automatically connect to the wireless network when the device is in range.

## Virtual private network

Secure remote access to corporate resources often includes using a defined VPN connection type from the mobile device that manages user account credentials to authenticate the VPN connection. You may have a vendor-specific VPN application for your mobile devices, or it may be supported by your existing enterprise mobility management solution. To simplify connections to VPNs after the migration, you can manage these connections using Intune [VPN profiles](/intune/deploy-use/vpn-connections-in-microsoft-intune). Depending on integration support, managing VPN connections with Intune may or may not be an option with certain VPN platforms.

## Certificates

Most enterprise mobility management solutions natively support digital certificates, either self-signed or issued from a third party Certificate Authorities (CAs), to authenticate mobile devices to networks connections or specific network resources. To simplify managing digital certificates after the migration, you can manage certificates using Intune [certificate profiles](/intune/deploy-use/secure-resource-access-with-certificate-profiles). Intune provides a uniform, centralized method for managing certificates, including how they are created, issued, and renewed.

## Conditional access

[Conditional access in Intune](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) controls whether or not users (or user groups) can access corporate resources such as SharePoint Online, Exchange Online, and Exchange on-premises.  If a device isn’t enrolled in Intune and compliant with your compliance policies, the user won’t have access to these resources from that device.  Additionally, if you’re blocking Exchange ActiveSync (EAS) connectivity at the network layer for externally connecting devices (such as mobile devices on a wireless carrier’s network), you’ll need to allow EAS access for Intune’s conditional access policies to work correctly. Make sure you’ve reviewed the considerations in the controlling access to corporate resources section before enabling conditional access policies.

## Application delivery & software

Intune offers a variety of methods for managing applications, including **publishing applications** and deploying both in-house developed applications and store apps.

## Mobile application management

Intune MAM policies allow you modify the functionality of native MAM-enabled applications to help provide data protection and security.  For example, you can **restrict cut, copy, and paste** for MAM-enabled apps. When deploying these native MAM-enabled apps you can define policies for these apps during the deployment.

## App wrapping

The Microsoft Intune App Wrapping Tool for **iOS** and [Android](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) allows you to modify and restrict the behavior of your in-house developed apps without modifying the code of the app itself. When your in-house iOS and Android apps are “wrapped”, you can provide data protection controls such as restrict cut, copy, and paste. 

>[!IMPORTANT]
>When these apps have been built using the SDK for your current enterprise mobility management solution or wrapped using your existing solution’s wrapper, Intune will not support that functionality.  You’ll need to recompile these apps with the [Intune App SDK](https://msdn.microsoft.com/library/mt627769.aspx) or the use the [Intune App Wrapper Tool](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) as appropriate. 

## Terms and conditions

Intune allows you to configure customized terms and conditions that your users must accept prior to enrolling a device in Intune.  This feature includes versioning control and allows you to generate reports to view which users have accepted the terms and conditions, what version they accepted, and when they accepted the terms.  We recommend investigating if you can use your existing terms and conditions in Intune early in your planning phase as engaging different legal resources may extend your migration timeline.
