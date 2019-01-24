---
# required metadata

title: Outlook settings for iOS and Android devices in Microsoft Intune
description: Create a configuration policy to set Microsoft Outlook settings running on iOS and Android devices.
keywords:
author: Erikre
ms.author: erikre
ms.reviewer: smithre4
manager: dougeby
ms.date: 01/24/2019
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
ms.custom: intune-azure

---

# Microsoft Outlook configuration settings 

Use a configuration policy to set Microsoft Outlook settings running on iOS and Android devices. 

To create an app configuration policy for managed iOS devices, see [Add app configuration policies for managed iOS devices](app-configuration-policies-use-ios.md). To create an app configuration policy for managed Android devices, see [Add app configuration policies for managed Android devices](app-configuration-policies-use-android.md). 

## Configuration settings

When adding a configuration policy in Intune, you can specify settings to configure Microsoft Outlook on iOS and Android. In the **Configuration settings** pane you can specify the email account configuration and configure app specific settings. In addition, you can configure these settings and/or use name/value pairs.

For Outlook account setup information and procedural steps for iOS and Android devices in Microsoft Intune, see [Account setup in Outlook for iOS and Android using Basic authentication](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/account-setup). For additional information about Outlook configuration settings, see [Deploying Outlook for iOS and Android app configuration settings](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).

### Basic authentication for email account configuration
Outlook for iOS and Android offers Exchange administrators the ability to "push" account configurations to their on-premises users who use Basic authentication with the ActiveSync protocol. For basic email account authentication for Microsoft Outlook, you can add a configuration policy and set the configuration.

In the **Configuraiton settings** pane, select the following:
    - Conifguration settings format: **Use configuration designer**
    - Configure email account settings: **Yes**
    - Authentication type: **Basic authentication**

For basic email account authentication for Microsoft Outlook, you can configure the following settings:
- **Username attribute from AAD**: This name is the attribute Intune gets from Azure Active Directory (Azure AD). Intune dynamically generates the username that's used by this profile. Your options include:
  - **User Principal Name**: Gets the name, such as `user1` or `user1@contoso.com`
  - **Primary SMTP address**: Gets the name in email address format, such as `user1@contoso.com`
- **Account domain**: (Optional) The domain of the account.
- **Email address attribute from AAD**: Choose how the email address for the user is generated. Select **User principal name** (`user1@contoso.com` or `user1`) to use the full principal name as the email address, or **Primary SMTP address** (`user1@contoso.com`) to use the primary SMTP address to sign in to Exchange. The recommendation is to select **Primary SMTP address**.
- **Email server**: Enter the host name of your on-premises Exchange server (e.g., mail.contoso.com).
- **Email account name**: Enter the display name for the email account. This name is shown to users on their devices.

### Modern authentication for email account configuration
Outlook for iOS and Android offers Exchange administrators the ability to "push" account configurations to their on-premises users who use Basic authentication with the ActiveSync protocol. For basic email account authentication for Microsoft Outlook, you can add a configuration policy and set the configuration.

In the **Configuraiton settings** pane, select the following:
    - Conifguration settings format: **Use configuration designer**
    - Configure email account settings: **Yes**
    - Authentication type: **Modern authentication**

For modern email account authentication for Microsoft Outlook, you can configure the following settings:
- **Username attribute from AAD**: This name is the attribute Intune gets from Azure Active Directory (Azure AD). Intune dynamically generates the username that's used by this profile. Your options include:
  - **User Principal Name**: Gets the name, such as `user1` or `user1@contoso.com`
  - **Primary SMTP address**: Gets the name in email address format, such as `user1@contoso.com`
- **Email address attribute from AAD**: Choose how the email address for the user is generated. Select **User principal name** (`user1@contoso.com` or `user1`) to use the full principal name as the email address, or **Primary SMTP address** (`user1@contoso.com`) to use the primary SMTP address to sign in to Exchange. The recommendation is to select **Primary SMTP address**.
- **Allow only work or school accounts** - By enabling this setting, users will be unable to add personal email and storage accounts within Outlook. If the user has a personal account added to Outlook, the user is prompted to remove the personal account. If the user does not remove the personal account, the work or school account cannot be added.​

### Gemeral app configuration for email account configuration
You can configure the following general app configuration settings:
- **Focused Inbox**: Focused Inbox separates your inbox into two tabs, **Focused** and **Other**. Your most important emails are on the Focused tab while the rest remain easily accessible, but out of the way, on the Other tab. When set as not configured, the default app setting is set to **On**.
- **Require Biometrics to access app**: Biometrics, such as TouchID or FaceID, can be required for users to access the app on their device. When required, biometrics are used in addition to the authentication method selected in this profile. This setting should not be enabled when Intune App Protection Policies are deployed, as the app protection policy includes access requirements prior to accessing managed data. Enabling both will result in multiple access prompts to access Outlook mobile. When set as not configured, the default app setting is set to Off.
- **Save Contacts**: Saving contacts to the mobile device’s native address book allows new calls and text messages to be linked with the user’s existing Outlook contacts. When set as not configured, the default app setting is set to Off.
    - **Allow user to change contact setting**: Specify whether the user is allowed to change the **Save Contacts** setting.
- **External recipients MailTip**: The External Recipients MailTip is displayed if the sender adds a recipient that's external or adds a distribution group that contains external recipients. This MailTip informs senders if a message they're composing will leave the organization, helping them make the correct decisions about wording, tone, and content. Available only for Exchange Online accounts and on-premises accounts leveraging hybrid modern authentication. When set as not configured, the default app setting is set to Off.
    - **Allow user to change setting**: Specify whether the user is allowed to change the **External recipients MailTip** setting.
- **Block external images**: When block external images is enabled, the app will prevent the download of images hosted on the Internet that are embedded in the message body. When set as not configured, the default app setting is set to Off.
    - **Allow user to change setting**: Specify if the user is allowed to change the **Block external images** setting.

For additional information about app configuration policies, see [Add app configuration policies for managed iOS devices](app-configuration-policies-use-ios.md).

## Next steps
[Configure email settings in Intune](email-settings-configure.md)

