---
# required metadata

title: Block apps with no modern authentication | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 098b652c-01e0-45d1-a731-620b0d3dc7c1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Block apps that do not use modern authentication (ADAL)
Conditional access for apps with MAM policies (MAM CA) relies on applications using [modern authentication](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) which is an implementation of OAuth2. Most current Office mobile and desktop applications use modern authentication, however there are third-party apps and older Office apps that user other authentication methods like basic authentication and forms based authentication.

To block access to these apps we recommend the following:

* Setup ADFS claims rules to block non-modern authentication protocols. Detailed instructions are provided in scenario 3 - [block all access to O365 except browser-based applications](https://technet.microsoft.com/library/dn592182.aspx).

### See also
[Allow only apps supported by Intune to access O365 services](allow-policy-managed-apps-access-to-o365.md)
