---
# required metadata

title: Sync Active Directory and add users to Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service:
ms.technology:
ms.assetid: ""

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Sync Active Directory and add users to Intune
You can configure directory synchronization to import user accounts from your on-premises Active Directory to Microsoft Azure Active Directory (Azure AD). Having your on-premises Active Directory service connected with all of your Azure Active Directory-based services makes managing user identity much simpler. You can also configure single sign-on features to make the authentication experience for your users familiar and easy.

Making things even easier, when you use multiple services with the same [Azure AD tenant](http://technet.microsoft.com/library/jj573650.aspx), the user accounts that you have previously synchronized are available to all cloud-based services that share the same Azure AD tenant subscription.

## Synchronize on-premises users with Azure AD
The only tool that you need to synchronize your user accounts with Azure AD is the [Azure AD Connect wizard](https://www.microsoft.com/download/details.aspx?id=47594). The Azure AD Connect wizard provides a simplified and guided experience for connecting your on-premises identity infrastructure to the cloud.  Choose your topology and needs (single or multiple directories, password sync or federation), and the wizard will deploy and configure all components required to get your connection up and running. Including: sync services, Active Directory Federation Services (AD FS), and the Azure AD PowerShell module.

> [!TIP]
> Azure AD Connect encompasses functionality that was previously released as Dirsync and Azure AD Sync. You can learn more about directory integration at [Directory integration](http://technet.microsoft.com/library/jj573653.aspx). To learn about the benefits of synchronizing user accounts from your local directory to Azure AD, see [Similarities between Active Directory and Azure AD](http://technet.microsoft.com/library/dn518177.aspx).

## Grant administrator permissions
After you've added users to your Intune subscription, we recommend that you grant a few user accounts [administrative credentials](administrative-accounts-websites-perms.md). The console that you use to assign administrative credentials depends on the type of administrator you want to assign:

-   **Tenant administrator**: Use the **[!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]** to assign this type of administrator to manage your subscription, including billing, cloud storage, and managing the users who can use [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

-   **Service administrator**: Use the **[!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]** to assign this type of administrator for day-to-day tasks including management of mobile devices or computers, deploying policy or software, and running reports.


### Next steps
Congratulations! You have just completed step 3 of the *Start with a paid subscription to Microsoft Intune* guide.

>[!div class="step-by-step"]

>[&larr; **Domain settings**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Manage Intune licenses** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  
