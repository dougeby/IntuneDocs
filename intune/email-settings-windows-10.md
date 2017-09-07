---
# required metadata

title: Intune email settings for Windows 10 devicestitleSuffix: "Azure portal"
description: Learn about the Intune settings you can use to configure email connections on Windows 10 devices."
keywords:
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2ffafbd0-4b5d-4c86-a46b-611f9b7a58e5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Email profile settings for Windows 10 devices in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]



- **Email server** - The host name of your Exchange server.
- **Account name** - The display name for the email account as it will appear to users on their devices.
- **Username attribute from AAD** - This is the attribute in Active Directory (AD) or Azure AD, that will be used to generate the username for this email profile. Select **Primary SMTP Address**, such as **user1@contoso.com** or **User Principal Name**, such as **user1** or **user1@contoso.com**.
- **Email address attribute from AAD** - How the email address for the user on each device is generated. Select **Primary SMTP Address** to use the primary SMTP address to log into Exchange or use **User Principal Name** to use the full principal name as the email address.


## Security settings

- **SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.



## Synchronization settings

- **Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.
- **Sync schedule** - Select the schedule by which devices will synchronize data from the Exchange server. You can also select **As Messages arrive**, which synchronizes data as soon as it arrives, or **Manual**, where the user of the device must initiate the synchronization.

## Content sync settings

- **Content type to sync** - Select the content types that you want to synchronize to devices from:
	- **Contacts**
	- **Calendar**
	- **Tasks**
