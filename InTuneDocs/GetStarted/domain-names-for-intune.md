

---
title: Domain names for Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: 
ms.assetid: 
author: Staciebarker
---
# Domain names for Microsoft Intune

Before you set up [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)], review this topic and other requirements listed in [What to know before you start Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).

When your organization signs up for a cloud-based service from Microsoft like [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)], you’re given an initial domain name that looks like the following: **contoso.onmicrosoft.com**. In this example, **contoso** is the domain name that you chose when you signed up, and **onmicrosoft.com** is the suffix assigned to accounts you add to your subscription. After you complete the sign-up process, you cannot change that domain name. However, as a global administrator, you can add your own custom domain names for your organization to use with the service, or you can remove domains that you’ve added previously.

By default, when you use the onmicrosoft domain, each user you import receives the **onmicrosoft.com** suffix for their user principal name (UPN).

To use a domain name that you own rather than the one that you were given at sign-up, you can add the domain name to Azure AD. After you add the domain, and it has been verified that you own it, you can create accounts and groups that include the domain name by changing DNS resource records at your DNS hosting provider. To simplify management of user accounts when you plan to use a custom domain, [configure a custom domain name](get-started-with-a-paid-subscription-to-microsoft-intune-step-2.md) to your subscription before you begin to synchronize users from your local Active Directory.

Configuring domain names and DNS resource records for [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] is the same as for other Azure AD tenants. See [Add and verify a custom domain name in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-add-verify-general/) for instructions.

After you review the information about domains and DNS resource records, return to this topic to continue learning about [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

### See also
[What to know before you start Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)