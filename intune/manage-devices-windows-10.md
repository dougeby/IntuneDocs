---
# required metadata

title: Windows 10 device management in Intune
titleSuffix: "Intune on Azure"
description: Learn how to see the devices you manage with Intune, and perform remote actions on them."
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/13/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: cc0e66f8-4624-4406-bc85-d249af0483d6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: [ALIAS]
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Manage Windows 10 devices

Intune management of Windows 10 PC's and Windows 10 Mobile devices allows you to optimize Windows features for the enterprise or school.

## Planning

Personal devices v. company owned devices
Azure Active Directory (AD) Premium

## Set up Intune
The following steps help you configure Intune for Windows 10 device management:

1. [Sign in to Intune](account-sign-up.md) - Sign in to your trial subscription or create a new Intune subscription.
2. [Configure domain name](custom-domain-name-configure.md) - Set DNS registration to connect your company's domain name with Intune. This gives users a familiar domain when connecting to Intune and using resources.
3. [Add users](users-add.md) - Manually add users or connect Active Directory to sync users with Intune.
4. [Assign licenses](licenses-assign.md) - Give users permission to use Intune. Each user or userless device requires an Intune license to access the service.
5. [Add groups](groups-add.md) - Use user and device groups to simplify management tasks. Groups are used to assign apps, settings, and other resources.
6. [Add apps](apps-add.md) - Apps can be assigned to groups and automatically or optionally installed.
  - [Add Windows store apps](store-apps-windows.md)
  - [Add Windows line-of-business apps](lob-apps-windows.md)
  - [Assign apps](apps-deploy.md)
7. [Configure devices](device-profiles.md) - Set up profiles that manage device settings. Device profiles can preconfigure settings for email, VPN, Wi-Fi, and device features. They can also restrict devices to help protect both devices and data. All of these settings are optional and can be configured and assigned after device enrollment. 
  - [Configure device profiles](device-profile-create.md) (optional) - The device profile containing settings that is assigned to devices. Required if you deploy device configurations or want to use conditional access.
  - [Configure certificates](certificates-configure.md) (optional) - An alternative to having users sign
  - [Configure device restriction settings](device-restrictions-windows-10.md) (optional)
  - [Configure email profile](email-settings-windows-10.md) (optional)
  - [Configure VPN settings](vpn-settings-windows-10.md) (optional)
  - [Configure Wi-Fi settings](wi-fi-settings-import-windows-8-1.md) (optional)
  - [Configure Endpoint Protection](endpoint-protection-windows-10) (optional)
  - [Configure Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) (optional)
  - [Use Windows Hello for Business](windows-hello.md) (optional)
8. [Configure device compliance](compliance-policy-create-windows.md)
9. [Set MDM authority](mdm-authority-set.md)
10. [Enable Windows enrollment](windows-enroll.md)
