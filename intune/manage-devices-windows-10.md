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

# Manage company-owned Windows 10 devices

Intune lets you simplify Windows 10 PC management for business or school. With modern management you can give users access to the resources they need while ensuring the devices are up-to-date and protected.

This topic helps you understand how to manage Windows 10 PCs with Intune.  

For example, your company uses shared Windows 10 PCs for employees' desktop devices. It's your responsibility to keep those devices updated and ensure they're protected with services like Windows Defender and BitLocker. You also need to provide users with apps and configure Wi-Fi and VPN settings. You can use bulk enrollment to Azure Active Directory (AD) join devices and enroll in Intune management. When users log on to PCs, they are made a standard user of the device with their assigned apps settings ready for use. Once enrolled, you can use Intune to ensure devices remain compliant with company policies and to deploy apps and settings to devices.


## Planning
The following questions can help you understand how you'll manage your company-owned Windows 10 devices:
- **Does your company have Azure AD Premium?** - Required for automatic enrollment and bulk enrollment.
- **What edition and version of Windows 10 are your devices running?** -
Certain Windows 10 management capabilities have minimum requirements:
  - **Automatic enrollment or bulk enrollment** - Windows 10 Pro or Enterprise required
  - **Windows as a service** - Windows 10 Pro or Enterprise with Anniversary edition required
  - **Multi-user support** - Windows 10 Creators version
- **Does your IT department have administrative roles you need to implement with Intune?** - Role-based access control lets you define the admins' role and scope for administrative purposes.
- **What device resources do you want to automatically provide to users?**<br>Resources can include email, VPN, and Wi-Fi settings, as well as apps.
- **What device restrictions do you want to enforce on devices?**<br>Device restrictions let you control settings and features including Windows Defender, browser, hardware, and personalization, and Microsoft store settings.

## Set up Windows 10 management
The following steps help you configure Intune for Windows 10 device management:

1. [Sign in to Intune](account-sign-up.md) - Sign in to your trial subscription or create a new Intune subscription.
2. [Configure domain name](custom-domain-name-configure.md) - Set DNS registration to connect your company's domain name with Intune. This gives users a familiar domain when connecting to Intune and using resources.
3. [Add users](users-add.md) - Manually add users or connect Active Directory to sync users with Intune.
4. [Add groups](groups-add.md) - Use user and device groups to simplify management tasks. Groups are used to assign apps, settings, and other resources.
5. [Add apps](apps-add.md) - Apps can be assigned to groups and automatically or optionally installed.
  - [Add Windows store apps](store-apps-windows.md)
  - [Add Windows line-of-business apps](lob-apps-windows.md)
  - [Assign apps](apps-deploy.md)
6. [Configure devices](device-profiles.md) - Set up profiles that manage device settings. Device profiles can preconfigure settings for email, VPN, Wi-Fi, and device features. They can also restrict devices to help protect both devices and data. All of these settings are optional and can be configured and assigned after device enrollment.
  - [Configure device profiles](device-profile-create.md) - The device profile containing settings that is assigned to devices. Required if you deploy device configurations or want to use conditional access.
  - [Configure certificates](certificates-configure.md)  - An alternative to having users sign in
  - [Configure device restriction settings](device-restrictions-windows-10.md)
  - [Configure email profile](email-settings-windows-10.md)
  - [Configure VPN settings](vpn-settings-windows-10.md)
  - [Configure Wi-Fi settings](wi-fi-settings-import-windows-8-1.md)
  - [Configure Endpoint Protection](endpoint-protection-windows-10.md)
  - [Configure Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)
  - [Use Windows Hello for Business](windows-hello.md)
7. [Configure device compliance](compliance-policy-create-windows.md) - Send an alert or block access when devices are out of compliance.
8. [Role-based access control (RBAC)](role-based-access-control.md) - Assign roles and scope to control who can perform various Intune tasks within your organization.
9. [Set MDM authority](mdm-authority-set.md) - Enables Intune device management for enrolled devices.
10. [Enable Windows enrollment](windows-enroll.md) - Enables Windows device enrollment so devices enter into management when users add their work or school account
