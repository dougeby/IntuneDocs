---
# required metadata

title: Manage Intune licenses | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service:
ms.technology:
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Manage Intune licenses
A user must have a license to your Intune subscription before they can sign in to use the service or enroll their devices into management. When users have a license, they are a member of the [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] user group. This group includes all users who have a license to use the subscription. **Each user license supports enrolling up to five devices**.

## How Intune licenses are assigned
When user accounts are synchronized from your on-premsies Active Directory or manually added to your cloud services subscription via the account portal, they are not automatically assigned an Intune license. Instead, at a later time, an Intune tenant administrator must edit the user account to assign a license to the user from the account portal.

When your subscription shares Azure AD with other cloud services associated with your subscription, you also have access to users that were added to those services. These users do not have a license to [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] until you assign a license to each of them.

> [!TIP]
> If the option to assign or revoke a license to [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] is disabled, your subscription might include volume licensing options, such as the options available when using [Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx). For information on how to assign or revoke licenses, see the documentation for your licensing options. 

## Assign an Intune user license

You use the **[!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)]** to manually add cloud-based users and assign licenses to both cloud-based user accounts and accounts synchronized from your on-premises Active Directory to Azure AD.

1.  Sign in to the Intune account portal using your tenant administrator credentials.

2.  Select the user account that you want to assign and Intune user license to and enable the **Microsoft Intune** checkbox on the user account properties. .

3.  The user account will now be added to the Microsoft Intune user group which grants the user permissions to use the service and enroll their devices into management.

### Next steps
Congratulations! You have just completed step 4 of the *Start with a paid subscription to Microsoft Intune* guide.
>[!div class="step-by-step"]

>[&larr; **Sync users to Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Organize users and devices** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  
