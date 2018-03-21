---
# required metadata

title: Microsoft Intune email settings for devices running Android and Android for Work
titleSuffix:
description: Learn about the Microsoft Intune settings you can use to configure email settings on devices running Android and Android for Work.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
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

# Email profile settings in Microsoft Intune for devices running Android and Android for Work

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

This article shows you the email profile settings you can configure for your devices running Android.

As an Intune administrator, you can create and assign email settings to the following Android devices:
- [Android Samsung Knox Standard](#android-samsung-knox-standard-email-settings)
- [Android for Work](#android-for-work-email-settings)

## Android Samsung Knox Standard email settings
- **Email server** - The host name of your Exchange server.
- **Account name** - The display name for the email account as it appears to users on their devices.
- **Username attribute from AAD** - This name is the attribute in Active Directory (AD) or Azure AD used to generate the username for this email profile. Select **Primary SMTP Address**, such as user1@contoso.com or **User Principal Name**, such as user1 or user1@contoso.com.
- **Email address attribute from AAD** - How the email address for the user on each device is generated. Select **Primary SMTP Address** to use the primary SMTP address to log in to Exchange or use **User Principal Name** to use the full principal name as the email address.
- **Authentication method** - Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.
	- If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created to authenticate the Exchange connection.

### Security settings

- **SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.
- **S/MIME** - Send outgoing email using S/MIME encryption.
	- If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created to authenticate the Exchange connection.

### Synchronization settings

- **Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.
- **Sync schedule** - Select the schedule by which devices synchronize data from the Exchange server. You can also select **As Messages arrive**, which synchronizes data when it arrives, or **Manual**, where the user of the device must initiate the synchronization.

### Content sync settings

- **Content type to sync** - Select the content types that you want to synchronize to devices from:
	- **Contacts**
	- **Calendar**
	- **Tasks**

## Android for Work email settings

- **Email app** - Select either **Gmail** or **Nine Work**
- **Email server** - The host name of your Exchange server.
- **Username attribute from AAD** - This name is the attribute in Active Directory (AD) or Azure AD, that is used to generate the username for this email profile. Select **Primary SMTP Address**, such as user1@contoso.com or **User Principal Name**, such as user1 or user1@contoso.com.
- **Email address attribute from AAD** - How the email address for the user on each device is generated. Select **User Principal Name** to use the full principal name as the email address or **User name**.
- **Authentication method** - Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.
	- If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created to authenticate the Exchange connection.
- **SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.
- **Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.
- **Content type to sync** (Nine Work only) - Select the content types that you want to synchronize to devices from:
	- **Contacts**
	- **Calendar**
	- **Tasks**
