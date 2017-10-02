---
# required metadata

title: Block apps with no modern authentication on Intune
description:
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Block apps that do not use modern authentication (ADAL)

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

App-based conditional access with app protection policies rely on applications using [modern authentication](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) which is an implementation of OAuth2. Most current Office mobile and desktop applications use modern authentication, however there are third-party apps and older Office apps that user other authentication methods like basic authentication and forms based authentication.

To block access to these apps we recommend the following:

* Set up ADFS claims rules to block non-modern authentication protocols. Detailed instructions are provided in scenario 3 - [block all access to O365 except browser-based applications](https://technet.microsoft.com/library/dn592182.aspx).
* For **SharePoint Online**, disable non-modern authentication in the SharePoint Online service using the PowerShell commandlet [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx) to set the legacy authentication protocols property to false:

```
 Set-SPOTenant -LegacyAuthProtocolsEnabled $false

```


>[!IMPORTANT]
>App-based CA must not be used with Azure Active Directory (Azure AD) certificate based authentication. You can only have one of these configured at a time.

### See also
[App-based conditional access with Intune](app-based-conditional-access-intune.md)
