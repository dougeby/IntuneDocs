---
title: Manage Intune licenses
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid:
author: Staciebarker
---
# 4. Manage Intune licenses
A user must have a license to your Intune subscription before they can sign in to use the service. When users have a license, they are a member of the [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] user group. This group includes all users who have a license to use the subscription. **Each user license supports enrolling up to five devices**.

-   **When you use the [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)] to add users** to your subscription, either manually or by bulk import from a CSV file, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] assigns an available license to each user account. If you do not have an available license, then no license is assigned. With both methods, you have the option to not assign licenses to the new user accounts at the time you add them to your subscription.

-   **When you import users from your on-premises Active Directory**, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] does not assign a license to each user account. Instead, at a later time, you must edit the user account to assign a license to the user.

-   **When your subscription shares Azure AD with other Azure AD tenants**, you have access to users that were added to those services. These users do not have a license to [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] until you assign a license to each of them.

If the option to assign or revoke a license to [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] is disabled, your subscription might include volume licensing options, such as the options available when using [Enterprise Mobility Suite](http://www.microsoft.com/server-cloud/products/enterprise-mobility-suite/default.aspx). For information on how to assign or revoke licenses, see the documentation for your licensing options.

## Next steps
Congratulations! You have just completed step 4 of the *Get started with a paid subscription to Microsoft Intune* guide.
>[!div class="step-by-step"]
>[Next](.\get-started-with-a-paid-subscription-to-microsoft-intune-step-5.md)  **Create groups to organize users and devices**
>
>[Previous](.\get-started-with-a-paid-subscription-to-microsoft-intune-step-2.md)  **Sync Active Directory and add users to Intune**
