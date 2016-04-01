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
# Manage Intune licenses
A user must have a license to your Intune subscription before they can sign in to use the service or enroll their devices into management. When users have a license, they are a member of the [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] user group. This group includes all users who have a license to use the subscription. **Each user license supports enrolling up to five devices**.

When user accounts are synchronized from your on-premsies Active Directory or manually added to your cloud services subscription via the account portal, they are not automatically assigned an Intune license. Instead, at a later time, an Intune tenant administrator must edit the user account to assign a license to the user from the account portal.

When your subscription shares Azure AD with other cloud services associated with your subscription, you also have access to users that were added to those services. These users do not have a license to [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] until you assign a license to each of them.

> [!TIP]
> If the option to assign or revoke a license to [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] is disabled, your subscription might include volume licensing options, such as the options available when using [Enterprise Mobility Suite](http://www.microsoft.com/server-cloud/products/enterprise-mobility-suite/default.aspx). For information on how to assign or revoke licenses, see the documentation for your licensing options.

## Assign Intune user licenses

You use the **[!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)]** to manually add cloud-based users and assign licenses to both cloud-based user accounts and accounts synchronized from your on-premises Active Directory to Azure AD.

To assign an Intune user license, simply log into the Intune account portal as a tenant administrator, select the user account(s) that you want to assign a license to, and enable the **Microsoft Intune** checkbox on the user account properties. This will add the user account to the Microsoft Intune user group and assign an available user license which will grant the user permissions to use the service and enroll their devices into management.

## Next steps
Congratulations! You have just completed step 4 of the *Get started with a paid subscription to Microsoft Intune* guide.
>[!div class="step-by-step"]
>[Next](.\get-started-with-a-paid-subscription-to-microsoft-intune-step-5.md)  **Create groups to organize users and devices**
>
>[Previous](.\get-started-with-a-paid-subscription-to-microsoft-intune-step-2.md)  **Sync Active Directory and add users to Intune**
