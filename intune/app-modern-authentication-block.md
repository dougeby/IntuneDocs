---
# required metadata

title: Block apps with no modern authentication on Intune
titleSuffix: Microsoft Intune
description: Learn about blocking apps that do not use modern authentication (ADAL) using Microsoft Intune.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/03/2019
ms.prod:
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: conceptual
ms.technology:
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Block apps that do not use modern authentication (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

App-based conditional access with app protection policies rely on applications using [modern authentication](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), which is an implementation of OAuth2. Most current Office mobile and desktop applications use modern authentication. However, there are third-party apps and older Office apps that user other authentication methods, like basic authentication, and forms-based authentication.

## Block apps

To block access to apps that do not use modern authentication, we recommend the following methods:

- Use Intune app protection policies to implement condition access. For more information, see [App-based conditional access with Intune](app-based-conditional-access-intune.md).

For more information about Azure AD Conditional Access, see the following:
- [What is conditional access in Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
- [How app-based conditional access works](app-based-conditional-access-intune.md#how-app-based-conditional-access-works)
- [Set up SharePoint Online and Exchange Online for Azure Active Directory conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/conditional-access-for-exo-and-spo)
- 

## Next steps

- [App-based conditional access with Intune](app-based-conditional-access-intune.md)
