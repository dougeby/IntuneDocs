---
# required metadata

title: Drive end-user adoption with conditional access
description: This article provides insights on how to use conditional access to drive Intune enrollment.
keywords:
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 06/12/2017
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
#ms.custom:

---

# Drive end-user adoption with conditional access

Enabling conditional access features with Intune, such as blocking email for unenrolled devices, can help drive enrollment and compliance but they are not required for a migration to be successful. Your migration adoption goals and security requirements should dictate the success.

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

-   Users of previous solution could potentially access resources using unmanaged devices until conditional access is enabled for those users.


This is one approach among many. You may choose a simpler process that defers all conditional access until after every phase has been instructed to enroll, or a stricter process that enforces conditional access from the very beginning and requires full compliance for all access.

-   Learn more about [conditional access](conditional-access.md).

## Task list for conditional access

### Task 1: Decide how you are going to implement conditional access

[Common ways to use conditional access](conditional-access-intune-common-ways-use.md).

### Task 2: Set up Intune conditional access

Choose one of the following options:

-   [Configure conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

-   [Install on-premises Exchange connector with Intune](exchange-connector-install.md)

-   [Set up app-based conditional access policies for Exchange Online](app-based-conditional-access-intune-create.md)

-   [Set up app-based conditional access policies for SharePoint Online](app-based-conditional-access-intune-create.md)

-   [Block apps that do not use modern authentication (ADAL)](app-modern-authentication-block.md)

## Next steps

Learn about the [typical migration cycle](migration-guide-cycle.md).
