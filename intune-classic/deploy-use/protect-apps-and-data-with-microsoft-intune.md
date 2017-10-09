---
# required metadata

title: Protect apps and data 
description: This topic describes the various Intune features and capabilities that are available to you to help protect your company apps and data.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5c46e188-87eb-4ce2-b184-24809e8bf783ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Protect apps and data with Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune protects company data through multiple technology layers. At the identity layer, conditional access protects access to services by only allowing access from managed and compliant devices. At the client application layer, mobile application management (MAM) protects data loss by preventing data from moving to nonprotected apps or storage locations—and by wiping data when a device is lost or stolen. We recommend using these two layers of protection together to help secure data while keeping your mobile workforce productive.

An important first step to protecting company data is to implement conditional access. You do this by making sure that devices that are used to access that data are using security protections like strong passwords and encryption, and are not jailbroken. Intune lets you set conditions that the devices have to comply with before they're allowed to access your company email and data.

[Conditional access](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) is determined by two types of policies that you can set in Intune:
- You use [compliance policies](introduction-to-device-compliance-policies-in-microsoft-intune.md) to determine the compliance of a device. They evaluate settings and conditions like:
  - PINs and passwords: You can create rules to require passwords to unlock a device, for the complexity requirements of the password, and for other password settings.
  - Encryption: You can restrict access to devices that are encrypted.
  - When a device is not jailbroken or rooted: Intune can detect if an enrolled device is jailbroken. You can set the policy to block access on such devices.
- You configure [conditional access policies](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) for a particular service, like Exchange Online or SharePoint Online. For each service, you can define which groups of users these policies should apply to. For example, you can make sure that everyone in the finance department can only access company email from enrolled and compliant devices.

Securing access to company resources is just the first step to protecting company data. You still need the ability to protect data after it's been accessed on the device. The data can now be copied, moved, saved to a different location, or shared. Intune solves this problem by providing you with the ability to restrict data movement by creating a set of rules like:
- Blocking copy and paste, or preventing data transfer outside of the work context.
- Preventing backup to personal cloud storage and preventing "Save as".
- Securing app access by requiring a PIN/passcode or corporate credentials.
- Having all web links open within the Intune Managed Browser.

These set of rules are referred to as [mobile application management (MAM) policies](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md). You can apply MAM policies to apps that are running on devices that might or might not be managed by you.  

You can protect your company data by using MAM policies for devices that are **enrolled in Intune**, devices that are **enrolled and managed by another third-party mobile device management (MDM) solution**, or devices that are **not enrolled in any MDM solution**, like employee-owned devices.

To associate an app with a MAM policy, the app must incorporate the Microsoft Intune App Software Development Kit (SDK), or you can use the App Wrapping Tool.

Apps like Microsoft Office apps have the Intune App SDK built in. You can see the full list of supported apps in the [Microsoft Intune mobile application gallery](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) on the Microsoft Intune application partners page. Choose the app to see the supported scenarios and platforms, and whether the app supports multi-identity.

You can also [enable your custom-built line-of-business apps](/intune/apps-prepare-mobile-application-management) to use with MAM policies.

In addition to restricting data movement, if a device gets lost or stolen or the user is no longer working with your company, you can [selectively wipe company data](wipe-managed-company-app-data-with-microsoft-intune.md), which leaves only personal data behind.
