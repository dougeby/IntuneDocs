---
# required metadata

title: Intune email settings for Android devicestitleSuffix: "Intune on Azure"
description: Learn about the Intune settings you can use to configure email connections on Android devices."
keywords:
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
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
ms.custom: intune-azure

---

# Email profile settings for Android devices in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]



- **Email server** - The host name of your Exchange server.
- **Account name** - The display name for the email account as it will appear to users on their devices.
- **Username attribute from AAD** - This is the attribute in Active Directory (AD) or Azure AD, that will be used to generate the username for this email profile. Select **Primary SMTP Address**, such as user1@contoso.com or **User Principal Name**, such as user1 or user1@contoso.com.
- **Email address attribute from AAD** - How the email address for the user on each device is generated. Select **Primary SMTP Address** to use the primary SMTP address to log into Exchange or use **User Principal Name** to use the full principal name as the email address.
- **Authentication method** - Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.
	- If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created that will be used to authenticate the Exchange connection.

## Security settings

- **SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.
- **S/MIME** - Send outgoing email using S/MIME encryption.
	- If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created that will be used to authenticate the Exchange connection.

## Synchronization settings

- **Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.
- **Sync schedule** - Select the schedule by which devices will synchronize data from the Exchange server. You can also select **As Messages arrive**, which synchronizes data as soon as it arrives, or **Manual**, where the user of the device must initiate the synchronization.

## Content sync settings

- **Content type to sync** - Select the content types that you want to synchronize to devices from:
	- **Contacts**
	- **Calendar**
	- **Tasks**
