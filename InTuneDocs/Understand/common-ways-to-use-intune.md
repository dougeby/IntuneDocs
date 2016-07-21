---
# required metadata

title: Common ways to use Intune | Microsoft Intune
description: Lists six of the most common tasks that users want Intune to do for them
keywords:
author: jeffgilb
manager: arob98
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1f37d4ff-b5a7-4a89-8884-a6184908b09c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Common ways to use Intune

Before diving into implementation tasks it is important to align your company’s enterprise mobility stakeholders around the business goals.  This is important whether you are brand new to enterprise mobility or migrating from another product.  The needs around enterprise mobility are dynamically evolving and Microsoft approaches to addressing these needs can sometimes be different from other solutions in the market.  The best way to align around business goals is to express what you want to accomplish in terms of the scenarios you want to enable for your employees, partners and IT.  Below are short introductions to the 6 most common scenarios that rely on Intune, accompanied with links to more information on how to plan and deploy each of them.

>[!NOTE]
>Do you want to know how Microsoft IT uses Intune to enable Microsoft employees to access corporate resources on their mobile devices while also keeping corporate data protected? [Read this technical case study](https://www.microsoft.com/itshowcase/Article/Content/588) to see in detail how Microsoft IT uses Intune and other services to manage identity, devices, and apps, and data.  

## Securing your on-premises email and data so it can be safely accessed by mobile devices
Most enterprise mobility strategies begin with a plan to enable secure access to email for employees with mobile devices out on the internet. Many organizations still have on-premises data and application servers, like Microsoft Exchange, hosted on their corporate network. Intune and the Enterprise Mobility Suite (EMS) provide a uniquely integrated conditional access solution for Exchange Server that ensures no mobile apps will be able to access email until the device is enrolled with Intune, all without deploying another gateway machine to the edge of your corporate network!

Beyond email, Intune supports enabling access to mobile apps that require secure access to on-premises data, like a line of business app server.  This is typically done using Intune-managed certificates for access control combined with a standard VPN gateway or proxy in the perimeter such as Microsoft Azure AD Application Proxy.  In these cases, the only way to access the corporate data is to enroll the device into management.  Once enrolled, the management system ensures that devices accessing corporate data are compliant with your policies.  Additionally, Intune’s App Wrapping Tool can be used to help contain the accessed data within your line of business app, so it can’t pass corporate data to consumer apps or services.

<!-- Learn more about how to plan and deploy Intune to help secure on-premises email and data. -->

## Securing your Office 365 email and data so it can be safely accessed by mobile devices
Protecting corporate data in Office 365 (email, documents, instant messages, contacts) could not be easier for you or more seamless for your users. Intune and the Enterprise Mobility Suite provide a uniquely integrated conditional access solution that ensures no users, apps, or devices can access Office 365 data unless they meet your company’s compliance requirements (performed multi-factor authentication, enrolled with Intune, using managed app, supported OS version, device pin, low user risk profile, etc.). The Office mobile apps in their respective app stores are ready to go with data containment policies you can configure via Intune, enabling you to prevent data from being shared with apps (e.g. native email app) and storage locations (e.g. Dropbox) that aren’t managed by IT.  All this functionality is built into Office 365 and EMS.  You do not have to deploy additional infrastructure to get this value.

A common Office 365 deployment practice is to require devices to enroll into management if they need to be fully provisioned with corporate apps/certs/Wi-Fi/VPN configurations, which is often the case for corporate-owned devices.  However, if the user simply needs to access corporate email and documents, which is often the case for personally owned devices, then the user is required to use the Office mobile apps (which you have applied data containment policies to) and skip enrolling the device altogether!  Either way, the Office 365 data will be secured by policies you’ve defined.

<!-- Learn more about how to plan and deploy Intune to help secure Office 365 email and data. -->

## Offer a “bring your own device” (BYOD) program to all employees
BYOD continues to grow in popularity among organizations as a means to reduce hardware expenditures or increase mobile productivity choices for employees. Just about everyone has a personal phone these days so why put another one in their pocket? The main challenge has always been to convince employees to enroll their personal device into management, as they are fearful of what their IT department will be able to see and do with their device.  

When device enrollment is not a viable option, Intune offers an alternative BYOD approach of simply managing the apps that contain corporate data.  Intune protects the corporate data even if the app in question accesses both corporate and personal data, as is the case for Office mobile apps.  As an administrator, you can require users to access Office 365 from the Office mobile apps and configure the apps with policies that keep the data protected (encrypted, pin protected, etc.).  These policies prevent data loss to unmanaged apps and storage locations – inside or outside of those apps.  For example, the policies will prevent a user from copying text from a corporate email profile into a consumer email profile even if both profiles are configured within Outlook Mobile.  Similar configurations can be deployed for other services and applications required by your BYOD users.

<!-- Learn more about how to plan and deploy Intune to support BYOD.-->

## Issue corporate-owned phones to your information workers
Most information workers are mobile these days, making productivity on mobile devices an imperative to be competitive.  These employees need seamless access to all corporate apps and data, at any time, wherever they are.  You need to ensure corporate data is secure and administrative costs are low.  

Intune offers bulk provisioning and management solutions that are integrated with the major corporate device management platforms on the market today, including the Apple Device Enrollment Program and the Samsung KNOX mobile security platform.  Centralized authoring of device configurations with Intune makes provisioning of corporate devices something that can be highly automated.  

Picture this: hand an employee an unopened iPhone box. The employee powers it on and is walked through a corporate-branded setup flow where they must authenticate themselves. The iPhone is seamlessly configured with security policies (encrypt hard drive, device pin, etc.),  email/Wi-Fi/VPN/certificate profiles, and a baseline set of apps. Then, the employee launches the Intune Company Portal app to access optional corporate apps available to them.

<!-- Learn more about how to plan and deploy Intune to support corporate owned devices. -->

## Issue limited-use shared tablets to your task workers
Task workers are increasingly making use of mobile technologies.  For example, shared tablets are now commonplace for retail store employees.  Whether used to process a sale or instantly check inventory, tablets help create great customer interactions.  Simplicity of the user experience is critical in this case.  For this reason, tablets are usually handed to employees in a limited-use mode, such that a single line-of-business app is the only thing the employee can interact with.  Intune enables you to bulk provision, secure, and centrally manage these shared tablets that can be configured to run in this limited-use mode.

<!-- Learn more about how to plan and deploy Intune to support shared tablets. -->

## Enable your employees to securely access Office 365 from an unmanaged public kiosk
Sometimes your employees need to use devices, apps, or browsers that you can’t manage, such as the public computers at trade shows and hotel lobbies. Should you allow your employees to access corporate email from them? With Intune and the enterprise mobility suite, <!--you have choices. The--> the answer can simply be “no” by limiting email access to devices that are managed by your organization.  <!-- Alternatively, you can choose to allow limited access to these untrusted computers by requiring multi-factor authentication and only allowing browser access (Outlook Web Access) in a mode where files cannot be downloaded (e.g. email attachments).-->  This will ensure your strongly authenticated employee will not accidentally leave corporate data on the untrusted computer.

<!-- Learn more about how to plan and deploy Intune to support kiosks. -->
