---
# required metadata

title: Configure Email settings for iOS devices in Microsoft Intune - Azure | Microsoft Docs
description: See a list of all the email settings you can configure and add to iOS devices in Microsoft Intune, including using Exchange servers, and getting attributes from Azure Active Directory. You can also enable SSL, authenticate users with certificates or username/password, and synchronize email on iOS devices using device configuration profiles in Microsoft Intune.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
---

# Add e-mail settings for iOS devices in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In Microsoft Intune, you can create and configure email to connect to an email server, choose how users authenticate, use S/MIME for encryption, and more.

This article lists and describes all the email settings available for devices running iOS. You can create a device configuration profile to push or deploy these email settings to your iOS devices.

## Before you begin

[Create a device configuration profile](email-settings-configure.md).

> [!NOTE]
> These settings are available for all enrollment types. For more information on the enrollment types, see [iOS enrollment](ios-enroll.md).

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

- **Email address attribute from AAD**: Choose how the email address for the user is generated. Select **User principal name** (`user1@contoso.com` or `user1`) to use the full principal name as the email address. Select **Primary SMTP address** (`user1@contoso.com`) to use the primary SMTP address to sign in to Exchange.
- **Authentication method**: Select either **Username and Password** or **Certificates** as the authentication method used by the email profile. Azure multi-factor authentication isn't supported.
  - If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created that is used to authenticate the Exchange connection.
- **SSL**: **Enable** uses Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.
- **OAuth**: **Enable** uses Open Authorization (OAuth) communication when sending emails, receiving emails, and communicating with Exchange. If your OAuth server uses certificate authentication, choose **Certificate** as the **Authentication method**, and include the certificate with the profile. Otherwise, choose **Username and password** as the **Authentication method**. When using OAuth, be sure to:

  - Confirm your email solution supports OAuth before targeting this profile to your users. Office 365 Exchange online support OAuth. On-premises Exchange and other partner or third-party solutions may not support OAuth. On-premises Exchange can be configured for Modern Authentication (see the [Announcing Hybrid Modern Authentication for Exchange On-Premises](https://blogs.technet.microsoft.com/exchange/2017/12/06/announcing-hybrid-modern-authentication-for-exchange-on-premises/) blog post).

    If the email profile uses Oauth, and the email service doesn't support it, then the **Re-Enter password** option appears broken. For example, nothing happens when the user selects **Re-Enter password** in Apple's device settings.

  - When OAuth is enabled, end users have a different “Modern Authentication” email sign-in experience that supports multi-factor authentication (MFA). 

  - Some organizations disable the end user’s ability to do [self-service application access](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-self-service-access). In this scenario, the Modern Authentication sign-in may fail until an Administrator creates the “iOS Accounts” enterprise app, and grant users access to the app in Azure AD.

    The default action is to add an application using the [Application Access Panel](https://docs.microsoft.com/azure/active-directory/user-help/active-directory-saas-access-panel-introduction) **Add App** feature **without business approval**. For more information, see [assign users to applications](https://docs.microsoft.com/azure/active-directory/manage-apps/ways-users-get-assigned-to-applications).

  > [!NOTE]
  > When you enable OAuth, the following happens:  
  > 1. Devices that are already targeted are issued a new profile.
  > 2. End users are prompted to enter their credentials again.

- **S/MIME**: **Enable S/MIME** to allow users to sign and/or encrypt email in the iOS native mail application. 

  When you use S/MIME with an email message, you confirm the authenticity of the sender, and the integrity and confidentiality of the message.

  - **S/MIME signing enabled**: Choose **Enable** to allow users to digitally sign outgoing email for the account you entered. Signing helps users who receive messages be certain that the message came from the specific sender, and not from someone pretending to be the sender. **Disable** doesn't allow users to digitally sign the message.
    - **Allow user to change setting**: Choose **Enable** to allow users to change S/MIME signing behavior. **Disable** prevents users from changing the S/MIME signing setting you configured. Available in iOS 12 and newer.

  - **S/MIME Signing Cert**: Select an existing PKCS or SCEP certificate profile that's used for signing email messages.
    - **Allow user to change setting**: Choose **Enable** to allow users to change the signing certificate. **Disable** prevents users from changing the signing certificate, and forces users to use the certificate you configured. Available in iOS 12 and newer.

  - **Encrypt by default**: **Enable** encrypts all messages as the default behavior. **Disable** doesn't encrypt all messages as the default behavior.
    - **Allow user to change setting**: Choose **Enable** to allow users to change the default encryption behavior. **Disable** prevents users from changing the encryption default behavior, and forces users to use the setting you configured. Available in iOS 12 and newer.

  - **Force per-message encryption**: Per-message encryption allows users to choose which emails are encrypted before being sent. Choose **Enable** to show the per-message encryption option when creating a new email. Users can then choose to opt in or opt out of per-message encryption. **Disable** prevents the per-message encryption option from showing.

    If the **Encrypt by default** setting is enabled, enabling per-message encryption allows users to opt out of encryption per message. If the **Encrypt by default** setting is disabled, enabling per-message encryption allows users to opt in to encryption per message.

  - **S/MIME Encryption Cert**: Select an existing PKCS or SCEP certificate profile that's used for encrypting email messages.
    - **Allow user to change setting**: Choose **Enable** to allow users to change the encryption certificate. **Disable** prevents users from changing the encryption certificate, and forces users to use the certificate you configured. Available in iOS 12 and newer.
- **Amount of email to synchronize**: Choose the number of days of email that you want to synchronize. Or select **Unlimited** to synchronize all available email.
- **Allow messages to be moved to other email accounts**: **Enable** allows users to move email messages between different accounts the users configured on their devices.
- **Allow email to be sent from third-party applications**: **Enable** allows users to select this profile as the default account for sending email. It allows third-party applications to open email in the native email app, such as attaching files to email.
- **Synchronize recently used email addresses**: **Enable** allows users to synchronize the list of email addresses that have been recently used on the device with the server.

## Next steps

The profile is created, but it's not doing anything yet. Next, [assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).

Configure email settings on [Android](email-settings-android.md), [Android Enterprise](email-settings-android-enterprise.md), [Windows 10](email-settings-windows-10.md), and [Windows Phone 8.1](email-settings-windows-phone-8-1.md) devices.
