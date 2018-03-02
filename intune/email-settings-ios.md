---
# required metadata

title: Microsoft Intune email settings for iOS devices
titleSuffix:
description: Learn the Microsoft Intune settings you can use to configure email settings on devices running iOS.
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Email profile settings for devices running iOS in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

This article shows you the email profile settings you can configure for your devices running iOS.

## Email settings

- **Email server** - The host name of your Exchange server.
- **Account name** - The display name for the email account as it appears to users on their devices.
- **Username attribute from AAD** - This is the attribute in Active Directory (AD) or Azure AD, that is used to generate the username for this email profile. Select **Primary SMTP Address**, such as **user1@contoso.com** or **User Principal Name**, such as **user1** or **user1@contoso.com**.
- **Email address attribute from AAD** - How the email address for the user on each device is generated. Select **Primary SMTP Address** to use the primary SMTP address to log into Exchange or use **User Principal Name** to use the full principal name as the email address.
- **Authentication method** - Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.
	- If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created that is used to authenticate the Exchange connection.
- **SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.
- **S/MIME** - Send outgoing email using S/MIME signing.
	- If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created that is used to authenticate the Exchange connection.
- **Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.
- **Allow messages to be moved to other email accounts** - This allows users to move email messages between different accounts they have configured on their device.
- **Allow email to be sent from third-party applications** - Allow the user to select this profile as the default account for sending email, and allow third-party applications to open email in the native email app, for example, to attach files to email.
- **Synchronize recently used email addresses** - This feature allows users to synchronize the list of email addresses that have been recently used on the device with the server.
