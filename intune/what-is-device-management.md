---
# required metadata

title: Device management in Microsoft 365
description: Microsoft 365 Enterprise includes Microsoft Intune. See how Intune provides mobile device management and mobile application management for your organization, including common scenarios, and using Intune to deploy Microsoft 365 in your environment. 
author: MandiOhlinger 
ms.author: mandia 
manager: dougeby 
ms.date: 09/21/2018 
ms.topic: article 
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.service: 
ms.technology: 
ms.custom: microsoft-intune 
ms.assetid: 0649d310-43a7-4b01-85d2-da255d03e1da
audience: ITPro

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune

---

# What is device management? 

A key task of any Administrator is to protect and secure an organization's resources and data. This task is device management. Users have many devices from which they open and share personal files, visit websites, and install apps and games. These same users are also employees and students, and want to use their devices to access work and school resources, such as email and OneNote. *Device management* enables organizations to protect and secure their resources and data. 

Using a device management provider, organization's can make sure that only authorized individuals and devices get access to proprietary information. Similarly, device users can feel at ease accessing work data from their phone, because they know that their device meets their organization's security requirements. As an organization, you might ask - **What should we use to protect our resources?**

This is where [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) comes in. Intune offers mobile device management (MDM) and mobile application management (MAM). Some key tasks of any MDM or MAM solution are to:

- Support a diverse mobile environment&mdash;manage iOS, Android, Windows, and macOS devices securely
- Make sure devices and apps are compliant with your organization's security requirements
- Create policies that help keep your organization data safe on company-owned and personal devices
- Use a single, unified mobile solution to enforce these policies, and help manage devices, apps, users, and groups.

Intune is included with Microsoft 365, and integrates with Azure Active Directory (Azure AD). Azure AD helps control who has access, and what they have access to.

## Hello Intune!
Many organizations, such as Microsoft, use Intune to secure proprietary data that users access from their company-owned and personal mobile devices. Intune includes features such as device and app configuration policies, software update policies, and installation statuses (as well as charts, tables, and reports) to help you secure and monitor data access.

It's common for people to have multiple devices that use different platforms. For example, an employee might use Surface Pro for work, and an Android mobile device in their personal life. And, it's common for a person to access organizational resources, such as Microsoft Outlook and SharePoint, from these multiple devices.

With Intune, you can manage multiple devices per person, and the different platforms that run on each device, including iOS, macOS, Android, and Windows. Intune separates policies and settings by device platform, so it's easy to manage and view devices of a specific platform.

**[Common scenarios](https://docs.microsoft.com/intune/common-scenarios)** is a great resource to see how Intune answers common questions when working with mobile devices. You'll find scenarios about:  
- Protecting email with on-premises Exchange
- Accessing Office 365 safely and securely
- Using personal devices to access organizational resources

## Integration with secure-and-protect services
A key task of any device management solution is to provide security and protection. Intune does a great job of integrating with other services to achieve this task. For example:

- **Microsoft 365** is a key component to simplifying common IT tasks. Using the Microsoft 365 admin center, you can create users, manage groups, and get access to other services, such as Intune, Azure Active Directory, and more. For example, you can create an iOS devices group in Microsoft 365. Then, use Intune to push policies to the iOS devices group that focus on iOS features, such as access to the app store, using AirDrop, backing up to iCloud, using Apple’s web filter, and more.

- **Windows Defender** includes many security features to help protect Windows 10 devices. For example, using Intune and Windows Defender together, you can: 

    - Enable [Windows Defender SmartScreen](https://docs.microsoft.com/intune/endpoint-protection-windows-10) to look for suspicious activity in files and apps on mobile devices. 
    - Use [Windows Defender Advanced Threat Protection (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) to help prevent security breaches on mobile devices, and help limit the impact of a security breach by blocking a user from corporate resources.

- **Conditional access** is a feature of Azure Active Directory, and integrates nicely with Intune. Using [conditional access](https://docs.microsoft.com/intune/conditional-access), you can make sure only compliant devices are allowed access to email, SharePoint, and other apps. 

## Choose the device management solution that's right for you

There are a couple of ways to approach device management. First, you can manage all aspects of devices by using all the features built into Intune. This is called **Mobile device management (MDM)**. In this approach, users "enroll" their devices, and use certificates to communicate with Intune. As an IT admin, you can push apps on devices, restrict devices to a specific operating system, block personal devices, and more. If a device is ever lost or stolen, you can also remove all data from the device. 

In the second approach, you manage apps on devices. This is called **Mobile application management (MAM)**. In this approach, users can use their personal devices to access organizational resources. When opening an app, such as email or SharePoint, users are prompted for additional authentication. If a device is ever lost or stolen, you can remove all organization data from the device. 

You can also use a combination of [MDM and MAM](https://docs.microsoft.com/intune/byod-technology-decisions) together.

When you set up Intune, you also choose to work solely in the Azure portal to manage devices, or use Intune and Microsoft 365 together to manage devices. See how Microsoft IT chose a modern device management approach, and lessons learned in the [Migrating mobile device management to Intune in the Azure portal](https://www.microsoft.com/itshowcase/Article/Content/1042/Migrating-mobile-device-management-to-Intune-in-the-Azure-portal) Microsoft IT case study. 

## Simplify IT tasks using the Device Management dashboard

The [Device Management dashboard](https://devicemanagement.portal.azure.com/) is a one-stop shop to manage and complete tasks for your mobile devices. This dashboard includes the services used for device management, including Intune and Azure Active Directory, and to also manage client apps. 

On the Device Management dashboard, you can:

- [Enroll devices](https://docs.microsoft.com/intune/device-enrollment)
- [Set device compliance](https://docs.microsoft.com/intune/device-compliance-get-started)
- [Manage devices](https://docs.microsoft.com/intune/device-management)
- [Manage apps](https://docs.microsoft.com/intune/app-management)  
- [iOS eBooks](https://docs.microsoft.com/intune/vpp-ebooks-ios)  
- [Install Exchange on-premises connector](https://docs.microsoft.com/intune/exchange-connector-install)  
- [Manage roles](https://docs.microsoft.com/intune/role-based-access-control)  
- Manage software updates
  - [Manage Windows 10 updates](https://docs.microsoft.com/intune/windows-update-for-business-configure)  
  - [Manage iOS updates](https://docs.microsoft.com/intune/software-updates-ios)  
- [Azure active directory](https://docs.microsoft.com/azure/active-directory)  
- [Manage users](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)
- [Manage groups and members](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups)
- [Troubleshoot](https://docs.microsoft.com/intune/help-desk-operators)

## Next step
When you're ready to get started with an MDM or MAM solution, walk through the different steps to set up Intune, enroll devices, and start creating policies, see [Mobile device management for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure). 
