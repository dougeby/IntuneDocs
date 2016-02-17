---
title: Step 2: Configure a custom domain name
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid:
author: Staciebarker
---

# Step 2: Configure a custom domain name
By default, [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] uses the domain name that you select when you subscribe to the service, which looks like **&lt;domain&gt;.onmicrosoft.com**. When your organization owns a custom domain, you can configure your instance of [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] to use that domain instead of the domain name provided with your subscription.

Before you create new user accounts or synchronize accounts from your on-premises Active Directory, we strongly recommend that you decide whether to use only the .onmicrosoft.com domain or to add one or more of your custom domain names. If you don't configure a custom domain name and suffix, each user account you import receives the onmicrosoft.com suffix for its user principal name (UPN). Configuring a custom domain before adding users can help simplify the management of user identities for your subscription by enabling users to sign in with the credentials they use to access other domain resources.

Because the tasks to configure [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] to use your organizations custom domain name are the same as for other Azure AD tenants, use the information and procedures found in [Add your domain](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

For more information about using your custom domain with a cloud-based service from Microsoft, see [Internet domain management](http://technet.microsoft.com/library/hh969248.aspx).

When you subscribe to a cloud-based service from Microsoft, your instance of that service becomes a tenant of Microsoft Azure Active Directory (Azure AD), which provides identity and directory services for your cloud-based service.

For more information about your Azure AD tenant, see [What is an Azure AD tenant?](http://technet.microsoft.com/library/jj573650.aspx).

**Prev** Step 1

**Next** Step 3
