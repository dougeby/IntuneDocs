---
# required metadata

title: Kiosk settings for Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Configure your Windows 10 (and later) devices as single-app and multi-app kiosks, including customizing the Start menu, adding apps, the task bar, and configuring a web browser. Also configure Windows Holographic for Business devices as multip-app kiosks in Microsoft Intune. 
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/18/2018
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

# Kiosk settings for Windows 10 (and later) in Intune

Kiosk profiles are used to configure Windows 10 devices to run one app, or run multiple apps. When you create a kiosk profile, you also choose if there's a start menu shown, if a web browser is installed, and more.

## Kiosk settings

1. Select **Add** to create a kiosk environment.
2. Enter a **Kiosk configuration name** for your kiosk. This name identifies a group of applications, the layout of these apps on the start menu, and the users that are assigned to this kiosk configuration.
3. Select the **Kiosk mode**. **Kiosk mode** Identifies the type of kiosk mode supported by the policy. Options include:

  - **Not Configured** (default): The policy doesn't enable kiosk mode.
  - **Single full-screen app kiosk**: The profile enables the device to run as a single user account, and locks it to a single Universal Windows Platform (UWP) app. So when the user signs in, a specific app starts. This mode also restricts the user from opening new apps, or changing the running app.
  - **Multi-app kiosk**: The profile enables the device to run multiple Universal Windows Platform (UWP) apps, or Win32 apps. You can also assign different apps to different user accounts. Only the apps you add are available to the users. The benefit of a multi-app kiosk, or fixed-purpose device, is to provide an easy-to-understand experience for users by only accessing apps they need. And, also removing from their view the apps they don’t need.

#### Single full-screen app kiosks
Enter the following settings:

- **Universal Windows Platform (UWP) app identifier**: Enter the **Application user model ID (AUMID)** of the kiosk app. Or select an existing managed app you added using [Mobile Apps](apps-add.md).

    See [Find the Application User Model ID of an installed app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

- **User account type**: Your options:

  - **Autologon**: For kiosks in public-facing environments with autologon enabled, a user with the least privilege (such as the local standard user account) should be used. To configure an Azure Active Directory (AD) account for kiosk mode, use the `AzureAD\user@contoso.com` format.
  - **Local user account**: Enter the local (to the device) user account or the Azure AD account log in associated with the kiosk app. For accounts joined to Azure AD domains, enter the account using the `domain\username@tenant.org` format.

#### Multi-app kiosks
Apps in this mode are available on the Start menu. These apps are the only apps the user can open. 

[Multi-app kiosks](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune) use a kiosk configuration that lists the allowed apps, and other settings.

Enter the following settings:

- **Add Win32 App**: A Win32 app is a traditional desktop app. Enter the **App name**, and the **Identifier**. The **Identifier** is the fully qualified pathname of the executable, with respect to the device.
- **Add managed apps**: Select an existing managed app you added using [Mobile Apps in Intune](apps-add.md).
- **Add app by AUMID**: Enter the [app's AUMID](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (UWP apps).
- **Taskbar**: Choose to **Enable** (show) the taskbar, or keep it **Not configured** (hidden) on the kiosk.
- **Start menu layout**: Enter an XML file that describes how the apps appear on the Start menu, including the order of the apps. [Customize and export Start layout](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) provides some guidance, and sample XML.

  [Create a Windows 10 kiosk that runs multiple apps](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file) provides more details on using and creating XML files.

- **User account type**: Add one or more user accounts that can use the apps you add. When the account signs in, only the apps defined in the configuration are available. The account may be local to the device or an Azure AD account log in associated with the kiosk app.

    For kiosks in public-facing environments with autologon enabled, a user type with the least privilege (such as the local standard user account) should be used. To configure an Azure Active Directory (AD) account for kiosk mode, use the `domain\user@tenant.com` format.

## Kiosk web browser settings

These settings control a web browser app on the kiosk. Be sure you deployed a web browser app to the kiosk devices using [Mobile Apps](apps-add.md).

1. Enter the following settings:

  - **Default home page URL**: Enter the default URL the kiosk browser opens when the browser opens or restarts.

  - **Home button**: Show (**Allow**), or hide (**Not configured**) the kiosk browser's home button. By default, the button is Not configured.

  - **Navigation button**: Show (**Allow**), or hide (**Not configured**) the forward and back buttons. By default, the navigation buttons are Not configured.

  - **End session button**: Show (**Allow**), or hide (**Not configured**) the end session button. When shown, the user selects the button, and the app prompts to end the session. When confirmed, the browser clears all browsing data (cookies, cache, and so on), and navigates back to the default URL.

    By default, the button is Not configured. 

  - **Refresh browser when user exceeds idle time limit**: Enter the amount of session idle time in minutes until the kiosk browser restarts in a fresh state. The value is an int 1-1440 minutes. By default, the value is empty or blank, which means there is no idle timeout.

  - **Blocked websites**: List of blocked website URLs (with wildcard support). Use this setting to prevent the browser from opening specific sites. You can also **Import** a .csv file that contains a list. Or, create a .csv file (**Export**) that contains the sites you add.

  - **Website exceptions**: List of exceptions to the blocked website URLs (with wildcard support). Use this setting to allow the browser to open specific sites. These exceptions are a subset of the blocked URLs. If a URL is in the blocked website list and the website exception list, then the exception takes effect.

    You can also **Import** a .csv file that contains a list. Or, create a .csv file (**Export**) that contains the sites you add.

2. Select **OK** to save your changes.

## Windows Holographic for Business

On Windows Holographic for Business devices, you can configure these devices to run in single-app kiosk mode, or multi-app kiosk mode. 

#### Single full-screen app kiosks
Enter the following settings:

- **Universal Windows Platform (UWP) app identifier**: Enter the **Application user model ID (AUMID)** of the kiosk app. Or select an existing managed app you added using [Mobile Apps](apps-add.md).

    See [Find the Application User Model ID of an installed app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) to get the ID.

- **User account type**: Select **Local user account** to enter the local (to the device) user account, or a Microsoft Account (MSA) account log in associated with the kiosk app. **Autologon** user account types aren't supported on Windows Holographic for Business.

#### Multi-app kiosks
Apps in this mode are available on the Start menu. These apps are the only apps the user can open.

Enter the following settings:

- **Add managed apps**: Select an existing managed app you added using [Mobile Apps in Intune](apps-add.md).
- **Add app by AUMID**: Enter the [app's AUMID](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (UWP apps).
- **Start menu layout**: Enter an XML file that describes how the apps appear on the Start menu, including the order of the apps. [Customize and export start layout](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) provides some guidance, and includes a specific XML file for Windows Holographic for Business devices.
- **User account type**: Add one or more user accounts that can use the apps you add. The supported options include: 
  - **HoloLens visitor**: The visitor account is a guest account that doesn't require any user credentials or authentication, as described in [shared PC mode concepts](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).
  - **Azure AD users**: Requires user credentials to sign in to the device. Use the `domain\user@tenant.com` format.
  - **Local User Accounts**: Requires user credentials to sign in to the device. 

When the account signs in, only the apps defined in the configuration are available.

## Next steps
[Assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).
