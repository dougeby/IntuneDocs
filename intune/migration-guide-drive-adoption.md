---
# required metadata

title: Drive end-user adoption with conditional access 
description: The purpose of this article is to provide insights on how to leverage conditional access to drive Intune enrollment.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Phase 2: Drive end-user adoption with conditional access

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Enabling conditional access features with Intune, such as blocking email for un-enrolled devices, can help drive enrollment and compliance but they are not required for a migration to be successful. Your migration adoption goals and security requirements should dictate the success.

## Migration campaign with conditional access

Here is a typical approach to enhancing a migration campaign with conditional access:

1.  Set conditional access rules to be enforced for all users but specifically exclude the users who need to migrate from the old MDM provider. You can create an Azure AD user group with all conditional access excluded users.

2.  As users migrate, remove them from the conditional access exclusion group.

3.  After migration completes, configure all conditional access policies to block by default unless Intune allows access.

### Advantages

-   Provides access control for new user accounts or user account who were not managed by the previous solution.

-   Provides grace period for users of previous solution to migration.

-   Minimizes loss of productivity

### Disadvantages

-   Users of previous solution could potentially access resources using un-managed devices until conditional access is enabled for those users.

> [!TIP]
> This is one approach among many. You may choose a simpler process that defers all conditional access until after every phase has been instructed to enroll, or a stricter process that enforces conditional access from the very beginning and requires full compliance for all access.

-   Learn more about [conditional access](https://docs.microsoft.com/intune/conditional-access).

## Task list for conditional access

### Task 1: Get ready for Intune conditional access

-   Learn [how to configure conditional access](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

### Task 2: Set up Intune conditional access

Choose one of the following conditional access policy types to learn more:

-   [Exchange Online & new Exchange Online dedicated](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)

-   [Exchange on-premises & legacy Exchange Online dedicated](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)

-   [SharePoint Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)

-   [Skype for Business Online](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)

-   [Dynamics CRM Online](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)

-   [Example e-mail access scenarios](/intune-classic/deploy-use/restrict-email-access-example-scenarios)

## Next steps

[Phase 2: Typical Migration Cycle](migration-guide-cycle.md)
