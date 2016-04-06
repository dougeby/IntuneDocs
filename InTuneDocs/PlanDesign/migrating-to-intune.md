---
# required metadata

title: Migrating to Microsoft Intune | Microsoft Intune
description:
keywords:
author: robmazz
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4fe6d6c6-b482-4c61-9f6a-c1cbdc912325

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Migrating to Microsoft Intune

More and more organizations with existing enterprise mobility management solutions are considering migrating to Microsoft Intune. Intune’s rapidly expanding mobile device management (MDM) and mobile application management (MAM) feature set offers many organizations improvements over their existing enterprise mobility management solutions. Intune also includes tight integration with Azure Active Directory Premium, Azure Rights Management Service as part of the Microsoft Enterprise Mobility Suite.

This document provides high-level guidance for you to consider when migrating your devices and users to Intune from an existing enterprise mobility management solution. It outlines the basic planning and migration considerations, best practices, and provides links to configuration guidance that you can use to get started with a migration to Intune.

If you purchase licenses for Microsoft Intune, you can use the "FastTrack Center Benefit," a service where Microsoft specialists work with you to get your environment ready for Intune. See the Microsoft Intune Service Benefit Description for more details.

This document focuses on the main stages of migrating to Intune from an existing enterprise mobility management solution:

- Before you begin
- Setting up Intune
- Configuring Intune
- Piloting Intune
- Migrating to Intune

## Before you begin

When migrating to Intune from another enterprise mobility management solution, there are several important consideration areas you should review before the migration:

- **Comparing features and capabilities:** Since you already have an existing enterprise mobility management solution, you’re familiar with its capabilities and limitations. However, you may not be familiar with Intune’s architecture or device/application management features. Thoroughly understanding how Intune’s mobile management features align or significantly differ from your current solution is essential to migration success. Make sure you also understand the complementary relationship with other Microsoft cloud services, such as Azure Active Directory Premium and Azure Rights Management. To help you map the features and capabilities of your current MDM solution to Intune, see the features reference worksheet at the end of this document. Additionally, you might find our design considerations guide helpful in comparing mobile device management options and configurations.
 
- **Migrating users and devices quickly:** Migrating users and devices to Intune quickly is important to prevent losses in productivity and keeping user satisfaction high. To help things move quickly, having a well-designed pilot deployment and making sure that you have configured and deployed compliance and configuration policies correctly is crucial. Depending on your organization, you may need to balance this migration with other service migration projects in your organization. Be sure to understand how these other projects affects your overall Intune migration timeline.

- **Maintaining business productivity:** Most users cannot afford to be disconnected from corporate resources or critical line-of-business (LOB) applications for extended periods. It’s very important that you maintain user productivity throughout the entire migration process by understanding exactly how Intune handles resource and application management.  Additionally, timely and detailed communication about the migration with your users is critical to a successful migration.

- **Maintaining data security:** Securing corporate resources before, during, and after the migration to Intune is critical. Make sure you understand how Intune uses policies that help you to configure security and functional settings for enrolled mobile devices, including hardware, password, and allowed/blocked apps settings.

- **Maintaining compliance requirements:** Most organizations need to maintain and enforce some level of compliance standards, from either internal governance directives or external regulatory requirements. As part of your migration, make sure you understand how Intune helps protect your data security, privacy, and compliance practices. Also, Intune enables you to present your own compliance resources to your users, like a custom terms of use or a link to your privacy policies. As part of your migration planning, you should plan to coordinate with your internal legal department to develop terms or guidelines that you’ll configure in Intune. 

- **Planning for user identity management:** You may already manage user identities and access to corporate resources using Active Directory and Active Directory Federation Services (AD FS) in your on-premises infrastructure. If you already use these services to synchronize and manage user accounts with Microsoft cloud services such as Office 365, you’ll be able to leverage your existing identity infrastructure if you use the same tenant name (*.onmicrosoft.com) across all Microsoft cloud services. 

- **Leveraging other Microsoft cloud services:** If you’re using integrated cloud services or SaaS applications with your existing enterprise mobility management solution, you need to understand how the Intune migration may impact these services. Intune shares a common foundation with other Microsoft cloud services and you can use the same accounts to subscribe to multiple cloud services that use the Microsoft Azure AD infrastructure.

- **Communication with users:** What you tell your users is incredibly important when migrating to Intune from your existing product.  Unlike some software migrations, this has a direct impact on the user’s mobile device and requires them to take certain steps to ensure a trouble-free experience.

- **Intune or Intune + System Center Configuration Manager?:** This document only covers a migration to a standalone Intune (cloud-only) deployment from an existing enterprise mobility management solution. If you have an existing on-premises System Center Configuration Manager (ConfigMgr) infrastructure, a hybrid Intune deployment may be a better migration and deployment option. There may be additional considerations with your migration that aren’t covered in this guidance.
