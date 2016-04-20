---
title: Protect apps and data | Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:
author: karthikaraman
---
# Protect apps and data with Microsoft Intune


**This section describes Intune capabilities like conditional access and mobile app management (MAM) policies that can help protect your company data.**

An important step to protecting company data is making sure that devices used to access that data are using security protections like strong password, encryption, and are not jailbroken. Microsoft Intune gives you the ability to set conditions that the devices have to comply with, before they are allowed to access your company email and data. This is known as **conditional access**.

[Conditional access](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) is determined by two types of policies you can set in Intune:
- [Compliance policies](introduction-to-device-compliance-policies-in-microsoft-intune.md) determine the compliance of a device. They evaluate settings and conditions like:
  - PIN and passwords: You can create rules to require passwords before unlocking a device, the complexity requirements of the password, and other password settings.
  - Encryption: You can restrict access to devices that are encrypted.
  - Device is not jailbroken or rooted: Intune can detect if an enrolled device is jailbroken, and you can set the policy to block access on such devices.
- [Conditional access policies](create-a-device-compliance-policy-in-microsoft-intune.md) are     configured for a particular service like Exchange Online or SharePoint Online. For each service, you can define which groups of users these policies should apply to. For example, you can make sure that everyone in the finance department can only access company email from enrolled and compliant devices.

Securing access to company resources is just the first step to protecting company data. You still need the ability to protect the data once it has been accessed on the device. The data now can be copied, moved, saved to a different location, or shared. Intune solves this problem by providing you with the ability to restrict data movement by creating a set of rules like:
- Block copy and paste, or prevent data transfer outside of the work context.
- Prevent backup to personal cloud storage, prevent Save as.
- Secure app access by requiring PIN/passcode or corporate credentials.
- Have all web links open within the Intune Managed Browser.

These set of rules are referred to as [mobile app management (MAM) policies](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).  MAM policies can be applied to apps running on devices that may or may not be managed by you.  You can protect your company data using MAM policies for devices that are enrolled in Intune, devices that are enrolled and managed by another third party MDM, or a device that may not be managed by you, like the employee owned devices.

To associate an app with a MAM policy, the app must incorporate the Microsoft Intune App Software Development Kit (SDK), or use the App wrapping tool.

Apps like Microsoft Office apps have the App SDK built-in. The full list of supported apps can be found on the [Microsoft Intune mobile application gallery](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) page. Choose the app to see the supported scenarios, platforms and whether or not the app supports multi-identity.

You can also [enable](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) your custom built line of business apps to use with MAM policies.

In addition to restricting data movement, if a device gets lost or stolen, or if the user is no longer working with your company, you can [selectively wipe company data](wipe-managed-company-app-data-with-microsoft-intune.md), leaving only personal data behind.
