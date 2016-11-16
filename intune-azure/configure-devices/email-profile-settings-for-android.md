---
# required metadata

title: Intune email settings for Android devices | Microsoft Docs
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
ms.assetid: 4d3458cc-fcaa-4648-b13f-bf1f0616c1c5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Email profile settings for Android devices

[!INCLUDE[azure_preview](../includes/azure_preview.md)]



- **Email server** - The host name of your Exchange server.
- **Account name** - The display name for the email account as it will appear to users on their devices.
- **Username attribute from AAD** - This is the attribute in Active Directory (AD) or Azure AD, that will be used to generate the username for this email profile. Select **Primary SMTP Address**, such as user1@contoso.com or **User Principal Name**, such as user1 or user1@contoso.com. 
- Email address attribute from AAD - 
- Authentication method - 

- **Security**
	- **SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server. For devices that run Samsung KNOX Standard 4.0 or later, you must export your Exchange Server SSL certificate, and deploy it as an Android Trusted Certificate Profile in Intune. Intune does not support accessing this certificate if it is installed on the Exchange server by other means.
	- Require S/MIME - 



- **Synchronization**
	- Amount of email to synchronize - 
	- Sync schedule - 


- **Content type to sync**
	- Email - 
	- Contacts - 
	- Calender - 
	- Tasks
