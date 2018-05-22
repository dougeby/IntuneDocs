---
# required metadata

title: Set up app based conditional access policy with Intune
description: Learn how to create an app-based conditional access policy with Intune.
keywords:
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 05/17/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Set up app-based conditional access policies with Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

This article describes on how to set up app-based conditional access policies for apps that are part of the list of approved apps. The list of approved apps consists of apps that were tested by Microsoft.

> [!IMPORTANT]
> This article walks through the steps to add an app-based conditional access policy. Note that you can use the same steps when adding apps such as SharePoint Online, Microsoft Teams, and Microsoft Exchange Online from the list of approved apps.

## Create app-based conditional access policies in Azure AD workload

IT admins can create app-based conditional access policies from the Azure AD workload. This gives convenience so you don't need to switch between the Azure and the Intune workloads.

> [!IMPORTANT]
> You need to have an Azure AD Premium license to create Azure AD conditional access policies from the Intune Azure portal.

### To create an app-based conditional access policy

> [!IMPORTANT]
> You need to have [Intune app protection policies](app-protection-policies.md) applied to your apps before using app-based conditional access policies.

1. In the **Intune Dashboard**, choose **Conditional access**.

2. In the **Policies** pane, choose **New policy** to create your new app-based conditional access policy.

4. Once you enter a policy name and configure the settings available in the **Assignments** section, then choose **Grant** under the **Access controls** section.

5. Choose **Require approved client app**, choose **Select**, then choose **Create** to save the new policy.

## Next steps
[Block apps that do not have modern authentication](app-modern-authentication-block.md)

### See also

[Protect app data with app protection policies](app-protection-policies.md)
[Conditional Access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
