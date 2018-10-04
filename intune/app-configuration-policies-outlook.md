---
# required metadata

title: Outlook settings for iOS and Android devices in Microsoft Intune
description: Create a configuration policy to set Microsoft Outlook settings running on iOS and Android devices.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/04/2018
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

# Outlook configuration settings 

Use a configuration policy to set Microsoft Outlook settings running on iOS and Android devices. 

To create an app configuration policy for managed iOS devices, see [Add app configuration policies for managed iOS devices](app-configuration-policies-use-ios.md). To create an app configuration policy for managed Android devices, see [Add app configuration policies for managed Android devices](app-configuration-policies-use-android.md). 

## Microsoft Outlook configuration settings

When adding a configuration policy in Intune, you can set specific settings to configure Microsoft Outlook. In the **Configuration settings** pane you can set the email account configuration, as well as the application configuration.

### Email account settings

The following configuration settings are specific to Microsoft Outlook.

- **Email server**: Enter the host name of your Exchange server.
- **Email account name**: Enter the display name for the email account. This name is shown to users on their devices.
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
- **Account domain**: (Optional) The domain of the account.

### Application configuration

The following application configuration settings are specific to Microsoft Outlook:

- **Allow users to change contact setting**: Select **Enable** to allow Outlook users to change their contact settings. Select **Disable** to prevent users from changing their contact settings.
- **Focused Inbox**: Select **Enable** to allow the email inbox to display a **Focused** tab. Select **Disable** to prevent the display of the **Focused** inbox tab.
- **Contact sync**: Select **Enable** to allow the user to sync their contacts with the Outlook app. Select **Disable** to prevent the user from syncing their contacts with hte Outlook app.
- **Biometrix required to access app**: Select **Require** to enforce the user of biometrics to access the Outlook app. Select **Not configured** to not require the user of biometrics to access the Outlook app.
- **Exteral recipients tool tip**: Select **Enable** to provide additional information to the user when sending email to external recipients. Select **Disable** to not privide any additional information to the user when sending email to external recipients.
- **Allow user to change external recipients setting**: Select **Enable** to allow users of Outlook to change whether the external recipients tool tip can be enabled. Select **Disable** to prevent the users of Outlook from changing the external recipients tool tip option.

## Next steps
[Configure email settings in Intune](email-settings-configure.md)

