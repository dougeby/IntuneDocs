---
# required metadata

title: Migrating to Intune - Setup Intune | Microsoft Intune
description:
keywords:
author: robmazz
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 96b73b86-e496-4d95-aaf9-7d694725be63

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Migrating to Intune - Setup Intune

## Review infrastructure requirements and architecture

Understanding the Intune service requirements and differences between your existing enterprise mobility solution and Intune is crucial to a successful migration. For example, Intune is tightly integrated with other Microsoft services and products that may provide additional benefits to other areas of your organization. A careful analysis of how these other services currently interact with your existing enterprise mobility solution may illuminate how Intune will manage these relationships.

## Controlling access to corporate resources

How you currently manage access to corporate resources in your existing enterprise mobility management solution may impact both your Intune pilot deployment and migration to Intune. “Conditional access” is an Intune feature for managing device access to corporate resources, such as email and cloud services, until the device has met certain compliance or configuration criteria.  Most enterprise mobility management solutions offer a similar capability, but many require an email gateway or additional access servers in your perimeter network.  If your existing solution is currently configured to manage your mobile devices in this capacity, several important questions must be answered before piloting or migrating devices to Intune:

1. **Can the conditional access policies in my existing enterprise mobility management solution coexist with Intune conditional access policies?** Typically, devices cannot be enrolled in two different enterprise mobility management solutions at the same time. The same restriction usually applies to configuring different sets of conditional access policies to a single email server or cloud service as well. For these reasons, we typically recommend that you do not have Intune and your existing enterprise mobility management solution both manage conditional access for the same group of devices and users at the same time. However, there may be cases and scenarios where conditional access coexistence is supported between Intune and your existing enterprise mobility management solution – specifically mobile application management without enrollment scenarios. We strongly recommend that you extensively test compatibility and coexistence scenarios for conditional access policies in a lab environment for your pilot and migration. The results of this testing will apply to the next question.

2. **When will I enable Intune’s conditional access policies?** This is an important security decision that impacts access to corporate resources and affects the overall user experience.  Depending on the results of your conditional access policy coexistence testing and evaluation, you may or may not have a gap in device coverage for these policies. In cases where coexistence isn’t possible for conditional access policies, you’ll need to determine whether or not to immediately require conditional access for devices migrating to Intune. Since these users will lose conditional access provided by the existing enterprise mobility management solution (it will need to be disabled so Intune can manage conditional access), they’ll need to enroll in Intune immediately to maintain managed access to corporate resources. This can be a tall order when dealing with large numbers of devices and users all at once. Depending on the number of devices and users you are able to simultaneously support, you may need to plan for a grace period where users and devices aren’t covered by conditional access by either solution.

## Sign up for (or sign into) Microsoft Intune

Before you can migrate to Intune, you’ll first need an Intune tenant. An Intune tenant uses a unique domain that your organization will use across all Microsoft Cloud Services and will be in the format of <your domain>.onmicrosoft.com.  If your company is already using Microsoft Online service such as Microsoft Office 365, we strongly recommend that you use the same user ID to sign up for Intune so that your user identities are shared automatically.  Intune is free to try for 30 days for up to 100 users, and is available as a standalone service or part of the Enterprise Mobility Suite. Sign up for either of these Intune options here. 

After completing the process of creating a new Intune tenant or adding Intune to your existing onmicrosoft.com tenant, you’ll be automatically signed in to the Microsoft Intune account portal with the global administrator account.

### Prepare Intune

To get started, you’ll need to configure a few basic Intune service settings: 

- In the Office 365 Management Portal: Add the users you want to test manage with Intune. If you added Intune to an existing tenant where Active Directory Federation Services (AD FS) and a synchronization technology are already in place, you’ll simply need to enable licenses for your Intune pilot users. 

	If this is not the case, for most medium-level and enterprise-level organizations, connecting your existing directory services to Intune via Azure Active Directory is the best and most convenient way to manage user identity with Intune. This is especially true if you already use other Microsoft cloud services, such as Office 365 or Exchange Online. Synchronizing your existing user accounts using Microsoft's AD Connect is a quick and easy way to connect your on-premises Active Directory to Azure Active Directory and configure a single sign-on authentication experience for your users.  Azure AD Connect encompasses functionality that was previously released as DirSync and Azure AD Sync.

	To migrate users to Intune they shouldn’t have their devices currently managed by your existing enterprise mobility solution. If they are, unenroll their devices and user accounts in accordance with the guidance from your existing mobile device management solution provider.  You’ll also need to assign Intune licenses to your pilot users in the Office 365 Management Portal.

	>[!IMPORTANT]
	>If you’ve configured conditional access to corporate resources in your existing solution for these pilot users and devices, the considerations covered in the controlling access to corporate resources section will apply.

- In the Intune Admin Console: Select the Start Managing Mobile Devices button to select your Mobile Device Management Authority, and enable mobile devices for each platform you plan to support in your organization.

 - Enable Android devices
 - Enable iOS and Mac devices
 - Enable Windows Phone devices
 - Enable Windows devices

>[!NOTE] 
>For Windows Phone and Windows devices, it isn’t necessary to specify the DNS entries listed in the TechNet topics for piloting Windows Phone and Windows devices if your current DNS CNAME entries already point to your existing enterprise mobility management solution provider. Changing the DNS entries may impact your current production users and devices.  To piloting Intune with Windows Phone or Windows devices, you can work around this by:
>
>- **Windows Phone:** During the enrollment process, users are prompted for the management server name if you do not create the CNAME record for “enterpriseenrollment.company_domain.com”.  Simply enter “manage.microsoft.com” for this value to complete the enrollment.
>- **Windows 8.1:** Create a registry key on your Windows 8.1 device for the Intune enrollment server address if you do not wish to configure the “enterpriseregistration.company_domain.com” DNS entry.

After you’ve completed these steps and configured the necessary platform requirements, you’re ready to start enrolling devices in Intune if you’d like test service connectivity and the basic enrollment process. Users can enroll and manage their devices with the Company Portal app using their credentials or you can enroll devices with the Device Enrollment Manager. It’s important to remember that you haven’t configured any Intune configuration or compliance polices yet, so these devices are enrolled but are not targeted for policies, applications, or other corporate resources.
