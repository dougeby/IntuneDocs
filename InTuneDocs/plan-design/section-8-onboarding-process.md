---
# required metadata

title: Intune onboarding process | Microsoft Docs
description: This article helps you with all details that need to be considered when on-boarding Intune cloud-only solution into your environment.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffbu, cgerth
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Intune implementation

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

During the onboarding phase, you’ll implement Intune into your production environment. The implementation process will consist of setting up and configuring Intune and external dependencies (if required), based on your [use case requirements](section-3-determine-use-case-requirements.md) that were reviewed in previous sections of this guide.

The following section provides an overview of the Intune implementation process that includes requirements and high-level tasks.

>[!TIP]
> Check [Additional resources](additional-resources.md) for more information about the Intune implementation process.

## Intune requirements

The main Intune standalone requirements are provided below:

-   EMS/Intune subscription

-   Office 365 subscription (for Office apps and MAM policy managed apps)

-   Apple APNs Certificate (to enable iOS device platform management)

-   Azure AD Connect (for directory synchronization)

-   Intune On-Premises Connector for Exchange (for CA for Exchange On-Premises, if needed)

-   Intune Certificate Connector (for SCEP certificate deployment, if needed)

>[!TIP]
> You can find more information about Intune standalone requirements [here](https://docs.microsoft.com/intune/get-started/what-to-know-before-you-start-microsoft-intune).

## Intune implementation process

### Overview of implementation tasks

Here's an overview of each task when implementing Intune.

#### Task 1: Add Intune subscription

As identified in the previous requirements section, an EMS or Intune subscription is required. If your organization does not have an EMS or Intune subscription, please contact Microsoft or your Microsoft Account Team regarding your interest in purchasing Enterprise Mobility + Security (EMS) or Intune.

-   Learn more about [how to buy Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-pricing).

#### Task 2: Add Office 365 subscription

This step is optional. As identified in the previous requirements section, an Office 365 subscription is required if you plan to use Exchange Online and manage Office mobile apps with MAM policy. If your organization does not have an Office 365 subscription, please contact Microsoft or your Microsoft account team regarding your interest in purchasing Office 365.

-   Learn more about [how to buy Office 365](https://products.office.com/business/compare-office-365-for-business-plans).

#### Task 3: Add users groups in Azure AD

You may need to add users or security groups in AD or AAD based on your Intune deployment use case scenarios and requirements. You should review your current users and security groups in Active Directory or Azure Active Directory and determine if they fully meet your needs. New users and security groups are most commonly added in Active Directory and synchronized into Azure Active Directory via Azure AD Directory Connect.

-   Learn more about [how to add users/groups in Intune](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3).

#### Task 4: Assign Intune and Office 365 user licenses

All users that will be targeted for EMS/Intune and Office 365 rollout will need to have a license assigned to them. EMS/Intune and Office 365 license assignment can be done in the Office 365 Admin Center Portal.

-   Learn more about [how to assign Intune licenses](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4).

#### Task 5: Set Mobile Device Management Authority to Intune

Before you can begin to setup, configure, manage and enroll devices using Intune, you must set the Device Management Authority to Intune. Setting the Device Management Authority task is completed in the Intune Admin Portal, Admin workspace.

-   Learn more about [how to set the Device Management Authority](https://docs.microsoft.com/intune/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).

#### Task 6: Enable device platforms

By default, in the Intune admin console, most device platforms are enabled, except for Apple devices (iOS and Mac). Before iOS devices can be enrolled and managed in Intune, the device platform must be enabled. Enabling the iOS device platform consists of a three-step process: create and download the APNs certificate and upload the APNs certificate into Intune.

-   Learn more about [how the iOS and Mac device management setup works.](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)

#### Task 7: Add and deploy terms and conditions policies

Microsoft Intune supports adding and deploying terms and conditions policies. Adding and deploying terms and conditions policies are completed in the Intune Admin Portal, Policy workspace. Add terms and conditions policies as appropriate and deploy to targeted groups based on your Intune deployment use cases and requirements.

-   Learn more about [how to add and deploy terms and condition policies](https://docs.microsoft.com/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune).

#### Task 8: Add and deploy configuration policies

Microsoft Intune supports adding and deploying two types of Configuration policies, General and Custom. Adding and deploying Configuration policies are completed in the Intune Admin Portal, Policy workspace. Add the Configuration policies as appropriate and deploy to targeted groups based on your Intune deployment use cases and requirements.

-   Learn more about [how to add and deploy configuration policies](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

#### Task 9: Add and deploy resource profiles

Microsoft Intune supports Email, Wi-Fi and VPN profiles. Adding and deploying profiles are completed in the Intune Admin Portal, Policy workspace. Add Email/Wi-Fi/VPN profiles as appropriate and deploy to targeted groups based on your Intune deployment use cases and requirements.

-   Learn more about [enable access to company resources with Intune](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

#### Task 10: Add and deploy apps

Microsoft Intune supports the deployment of Web, LOB and Public Store Apps. In addition, managing apps that have integrated the Intune SDK by associated them with MAM policies is supported. Adding and deploying apps are completed in the Intune Admin Portal, App workspace. Adding MAM policies are completed in the Intune Admin Portal, Policy workspace. Add apps as appropriate and deploy to targeted groups based on your Intune deployment use cases and requirements.

-   Learn more about [add and deploy applications](https://docs.microsoft.com/en-us/intune/deploy-use/deploy-apps).

#### Task 11: Add and deploy compliance policies

Microsoft Intune supports Compliance policies. Adding and deploying Compliance policies are completed in the Intune Admin Portal, Policy workspace. Add Compliance policies as appropriate and deploy to targeted groups based on your Intune deployment use cases and requirements.

-   Learn more about [compliance policies](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

#### Task 12: Enable Conditional Access Policies

Microsoft Intune supports Conditional Access for Exchange Online and On-premises, SharePoint Online, Skype for Business Online and Dynamics CRM Online. You enable Conditional Access policies in the Intune Admin Portal, Policy workspace. Enable and configure Conditional Access as appropriate based on your [Intune deployment use cases and requirements](section-3-determine-use-case-requirements.md).

-   Learn more about [conditional access](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

#### Task 13: Enroll devices

Intune supports iOS, Mac OS, Android, Windows desktop and Windows mobile device platforms. Enroll mobile device platforms as appropriate, based on your Intune deployment use cases and requirements.

-   Learn more about [how to enroll devices](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune).

>[!TIP]
> Check out this [Microsoft Virtual Academy Intune session module](https://mva.microsoft.com/training-courses/deploying-microsoft-enterprise-mobility-suite-16408?l=PPWNoZxvD_1404778676) for more information on the Intune implementation process.

## Next Section

The next section provides guidance on [testing and validating your Intune deployment](section-9-test-and-validation.md).
