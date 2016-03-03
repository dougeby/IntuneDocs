---
title: Sync Active Directory and add users to Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid: ""
author: Staciebarker
---

# Sync Active Directory and add users to Intune
You can configure directory synchronization to import user accounts from your on-premises Active Directory to Microsoft Azure Active Directory. Additionally, when you activate directory synchronization in your Intune tenant, you are turning on this feature across  all the Microsoft cloud services that you are subscribed to. When you use multiple services with the same Azure AD, the user accounts that you synchronize are available to each cloud-based service that shares your Azure AD. Having your on-premises Active Directory service connected with all of your Azure Active Directory-based services makes managing user identity much simpler. You can also configure single sign-on features to make the authentication experience for your users familiar and easy.

The [Azure AD Connect wizard](https://www.microsoft.com/download/details.aspx?id=47594) is the single tool and guided experience for connecting your on-premises identity infrastructure to the cloud.  Choose your topology and needs (single or multiple directories, password sync or federation), and the wizard will deploy and configure all components required to get your connection up and running, including sync services, Active Directory Federation Services (AD FS), and the Azure AD PowerShell module.
Azure AD Connect encompasses functionality that was previously released as Dirsync and Azure AD Sync.
Learn more about directory integration at [Directory integration](http://technet.microsoft.com/library/jj573653.aspx).

After you've added users to your Intune subscription, we recommend that you grant a few user accounts administrative credentials. The console that you use to assign administrative credentials depends on the type of administrator you want to assign:

-   **Tenant administrator**: Use the **[!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]** to assign this type of administrator to manage your subscription, including billing, cloud storage, and managing the users who can use [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

-   **Service administrator**: Use the **[!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]** to assign this type of administrator for day-to-day tasks including management of mobile devices or computers, deploying policy or software, and running reports.

To learn more about administrator accounts, see [Intune administrator accounts and special permissions](/Intune/Understand/what-to-know-before-setting-up-microsoft-intune.html#BKMK_AdminAccounts).

To learn about the benefits of synchronizing user accounts from your local directory to Azure AD, see
            [Similarities between Active Directory and Azure AD](http://technet.microsoft.com/library/dn518177.aspx).

## Next steps
Congratulations! You have just completed step 3 of the *Get started with a paid subscription to Microsoft Intune* guide.

>[!div class="step-by-step"]
>[Next](.\get-started-with-a-paid-subscription-to-microsoft-intune-step-4.md)  **Manage Intune licenses**
>
>[Previous](.\get-started-with-a-paid-subscription-to-microsoft-intune-step-2.md)  **Configure a custom domain name**
