---
# required metadata

title: Email settings for iOS devices in Microsoft Intune: Azure | Microsoft Docs
description: Create a device configuration email profile that that uses Exchange servers, and retrieves attributes from Azure Active Directory. You can also enable SSL, authenticate users with certificates or username/password, and synchronize email on iOS devices using Microsoft Intune.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/20/2018
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

# Email profile settings for iOS devices - Intune

Use the email profile settings to configure your devices running iOS.

## Email settings

- **Email server**: Enter the host name of your Exchange server.
- **Account name**: Enter the display name for the email account. This name is shown to users on their devices.
- **Username attribute from AAD**: This name is the attribute Intune gets from Azure Active Directory (AAD). Intune dynamically generates the username that's used by this profile. Your options:
  - **User Principal Name**: Gets the name, such as `user1` or `user1@contoso.com`
  - **Primary SMTP address**: Gets the name in email address format, such as `user1@contoso.com`
  - **sAM Account Name**: Requires the domain, such as `domain\user1`.

    Also enter:  
    - **User domain name source**: Choose **AAD** (Azure Active Directory) or **Custom**.

      When choosing to get the attributes from **AAD**, enter:
      - **User domain name attribute from AAD**: Choose to get the **Full domain name** or the **NetBIOS name** attribute of the user

      When choosing to use **Custom** attributes, enter:
      - **Custom domain name to use**: Enter a value that Intune uses for the domain name, such as `contoso.com` or `contoso`

- **Email address attribute from AAD**: Choose how the email address for the user is generated. Select **User principal name** (`user1@contoso.com` or `user1`) to use the full principal name as the email address, or **Primary SMTP address** (`user1@contoso.com`) to use the primary SMTP address to sign in to Exchange.
- **Authentication method**: Select either **Username and Password** or **Certificates** as the authentication method used by the email profile (**Note**: Azure Multi-factor authentication is not supported).
  - If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created that is used to authenticate the Exchange connection.
- **SSL**: Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.
- **S/MIME**: Send outgoing email using S/MIME signing.
  - If you selected **Certificate**, select a PKCS certificate profile you previously created to authenticate the Exchange connection.
- **Amount of email to synchronize**: Choose the number of days of email that you want to synchronize. Or select **Unlimited** to synchronize all available email.
- **Allow messages to be moved to other email accounts**: Allows users to move email messages between different accounts they have configured on their device.
- **Allow email to be sent from third-party applications**: Allow the user to select this profile as the default account for sending email, and allow third-party applications to open email in the native email app, for example, to attach files to email.
- **Synchronize recently used email addresses**: Allows users to synchronize the list of email addresses that have been recently used on the device with the server.

## Next steps
[Configure email settings in Intune](email-settings-configure.md)