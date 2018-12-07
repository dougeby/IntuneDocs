---
# required metadata

title: Android & Android Enterprise email settings in Microsoft Intune - Azure | Microsoft Docs
description: Create a device configuration email profiles that use Exchange servers, and retrieve attributes from Azure Active Directory. Enable SSL or SMIME, authenticate users with certificates or username/password, and synchronize email and schedules on Android and Android work profile devices using Microsoft Intune.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: seodec18

---

# Android and Android Enterprise device settings to configure email, authentication, and synchronization in Intune

This article lists and describes the different email settings you can control on Android and Android Enterprise devices. As part of your mobile device management (MDM) solution, use these settings to configure an email server, use SSL to encrypt emails, and more.

As an Intune administrator, you can create and assign email settings to the following Android devices:

- Android Samsung Knox Standard
- Android Enterprise

## Before you begin

[Create a device configuration profile](email-settings-configure.md).

## Android (Samsung Knox)

- **Email server**: Enter the host name of your Exchange server.
- **Account name**: Enter the display name for the email account. This name is shown to users on their devices.
- **Username attribute from AAD**: This name is the attribute Intune gets from Azure Active Directory (AAD). Intune dynamically generates the username that's used by this profile. Your options:
  - **User Principal Name**: Gets the name, such as `user1` or `user1@contoso.com`
  - **User name**: Gets only the name, such as `user1`
  - **sAM Account Name**: Requires the domain, such as `domain\user1`. sAM account name can only be used with Android devices. Android Enterprise isn't supported.

    Also enter:  
    - **User domain name source**: Choose **AAD** (Azure Active Directory) or **Custom**.

      When choosing to get the attributes from **AAD**, enter:
      - **User domain name attribute from AAD**: Choose to get the **Full domain name** or the **NetBIOS name** attribute of the user

      When choosing to use **Custom** attributes, enter:
      - **Custom domain name to use**: Enter a value that Intune uses for the domain name, such as `contoso.com` or `contoso`

- **Email address attribute from AAD**: Choose how the email address for the user is generated. Select **User principal name** (`user1@contoso.com` or `user1`) to use the full principal name as the email address, or **Primary SMTP address** (`user1@contoso.com`) to use the primary SMTP address to sign in to Exchange.

- **Authentication method**: Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.
  - If you select **Certificate**, select a client SCEP or PKCS certificate profile that you previously created to authenticate the Exchange connection.

### Security settings

- **SSL**: Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.
- **S/MIME**: Send outgoing email using S/MIME encryption.
  - If you select **Certificate**, select a client SCEP or PKCS certificate profile that you previously created to authenticate the Exchange connection.

### Synchronization settings

- **Amount of email to synchronize**: Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.
- **Sync schedule**: Select the schedule for devices to synchronize data from the Exchange server. You can also select **As Messages arrive**, which synchronizes data when it arrives, or **Manual**, where the user of the device must initiate the synchronization.

### Content sync settings

- **Content type to sync**: Select the content types that you want to synchronize to devices from:
  - **Contacts**
  - **Calendar**
  - **Tasks**

## Android Enterprise

- **Email app**: Select either **Gmail** or **Nine Work**
- **Email server**: The host name of your Exchange server.
- **Username attribute from AAD**: This name is the attribute in Active Directory (AD) or Azure AD, that is used to generate the username for this email profile. Select **Primary SMTP Address**, such as user1@contoso.com or **User Principal Name**, such as user1 or user1@contoso.com.
- **Email address attribute from AAD**: How the email address for the user on each device is generated. Select **User Principal Name** to use the full principal name as the email address or **User name**.
- **Authentication method**: Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.
  - If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created to authenticate the Exchange connection.
- **SSL**: Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.
- **Amount of email to synchronize**: Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.
- **Content type to sync** (Nine Work only): Select the content types that you want to synchronize to devices from:
  - **Contacts**
  - **Calendar**
  - **Tasks**

## Next steps
[Configure email settings in Intune](email-settings-configure.md)
