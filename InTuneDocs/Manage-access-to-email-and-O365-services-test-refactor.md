---
title: Manage access to email and O365 services test refactor
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: secure-email-article
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712
author: karthikaraman
---
# Manage access to email and O365 services test refactor
You can restrict access to your company email and O365 services like SharePoint and Skype for Business.
Intune's conditional access capability allows you to make sure that only devices that are compliant with the rules that you set are allowed access to your company email and resources.
To implement conditional access, you configure two policy types in Intune:
## What is conditional access?
Conditional access in Intune means that you can require that devices meet a certain set of conditions in order to be able to access your company data and resources.
- Compliance policies are optional policies you can deploy to users and devices and evaluate settings like:

  - Passcode
  - Encryption
  - Whether the device is jailbroken or rooted
  - Whether email on the device is managed by an Intune policy

  If no compliance policy is deployed to a device, then any applicable conditional access policies will treat the device as compliant.


- Conditional access policies are configured for a particular service, and define rules such as which Azure Active Directory security user groups or Intune user groups will be targeted and how devices that cannot enroll with Intune will be managed.

Unlike other Intune policies, you do not deploy conditional access policies. Instead, you configure these once, and they apply to all targeted users.


When devices do not meet the conditions you configure, the user is guided though the process of enrolling the device and fixing the issue that prevents the device from being compliant.
## How does it work?
A typical flow of conditional access might as follows:

![](./media/ConditionalAccess4.png)

See this 4 minute video that describes how this works using email as an example:
<iframe width="560" height="315" src="https://www.youtube.com/embed/lYx3YIezccg" frameborder="0" allowfullscreen></iframe>
## Conditional access for mobile devices
Generally the following mobile platforms are supported for conditional access:
- Windows Phone 8.1 and later
- iOS 7.1 and later
- Android 4.0 and later, Samsung Knox Standard 4.0 and later

Depending on the resource or service the device is trying to access, requirements
may vary. The specific requirements are listed for each resource in their respective topics:
- Manage access to Exchange On-premises
- Manage access to Exchange Online
- Manage access to SharePoint Online
- Manage access to Skype for Business

## Conditional access for PCs
You can setup conditional access for PCs that run Office desktop applications and meet the following requirements:

- The PC must be running Windows 7.0 or Windows 8.1.
- The PC must either be domain joined or compliant.

  In order to be compliant, the PC must be enrolled in Intune and comply with the policies.
  For domain joined PCs, you must set it up to automatically register the device with Azure Active Directory.
- Office 365 modern authentication must be enabled, and have all the latest Office updates.

  Modern authentication brings Active Directory Authentication Library (ADAL) based sign-in to Office 2013 Windows clients and enables better security like multi-factor authentication, and certificate-based authentication.
- Setup ADFS claims rules to block non-modern authentication protocols. Step by step instructions are detailed in scenario 3 - block all access to O365 except browser based applications.
## Next steps
Manage device compliance policy

  Manage access to email

  Manage access to SharePoint

  Manage access to Skype for Business
