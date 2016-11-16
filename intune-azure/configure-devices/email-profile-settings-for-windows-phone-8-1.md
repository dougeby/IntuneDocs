---
# required metadata

title: Intune email settings for Windows Phone 8.1 devices | Microsoft Docs
description: Description.
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 352d6bd9-ec8c-439e-be3a-ad3daf307df2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Email profile settings for Windows Phone 8.1 devices

[!INCLUDE[azure_preview](../includes/azure_preview.md)]



- **Email server** - The host name of your Exchange server.
- **Account name** - The display name for the email account as it will appear to users on their devices.
- **Username attribute from AAD** - This is the attribute in Active Directory (AD) or Azure AD, that will be used to generate the username for this email profile. Select **Primary SMTP Address**, such as user1@contoso.com or **User Principal Name**, such as user1 or user1@contoso.com.
- Email address attribute from AAD


- **Security**
	- **SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.



- **Synchronization**
	- Amount of email to synchronize
	- Sync schedule



- **Content type to sync**
	- Email
	- Contacts
	- Calender
	- Tasks
