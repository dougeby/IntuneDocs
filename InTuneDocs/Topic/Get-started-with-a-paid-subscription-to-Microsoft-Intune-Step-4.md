---
title: Get started with a paid subscription to Microsoft Intune - Step 4
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
author: Staciebarker
---
# <a name="BKMK_AssignWitLicenses"></a>Step 4: Manage Intune licenses
A user must have a license to your Intune subscription before they can sign in to use the service. When users have a license, they are a member of the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] user group. This group includes all users who have a license to use the subscription. **Each user license supports enrolling up to five devices**.

-   **When you use the [!INCLUDE[wit_icp_2](../Token/wit_icp_2_md.md)] to add users** to your subscription, either manually or by bulk import from a CSV file, [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] assigns an available license to each user account. If you do not have an available license, then no license is assigned. With both methods, you have the option to not assign licenses to the new user accounts at the time you add them to your subscription.

-   **When you import users from your on-premises Active Directory**, [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] does not assign a license to each user account. Instead, at a later time, you must edit the user account to assign a license to the user.

-   **When your subscription shares Azure AD with other Azure AD tenants**, you have access to users that were added to those services. These users do not have a license to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] until you assign a license to each of them.

If the option to assign or revoke a license to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] is disabled, your subscription might include volume licensing options, such as the options available when using [Enterprise Mobility Suite](http://www.microsoft.com/server-cloud/products/enterprise-mobility-suite/default.aspx). For information on how to assign or revoke licenses, see the documentation for your licensing options.

**Prev** Step 3
**Next** Step 5
