---
# required metadata

title: Kiosk settings for Android in Microsoft Intune - Azure | Microsoft Docs
description: Configure your Android kios devices as single-app and multi-app kiosks. 
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 7/5/2018
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

# Kiosk settings for Android devices in Intune

You can configure a device into single or multi-app kiosk mode by using device configuration settings. When a device is in kiosk mode, use of the device is limited to the app or set of apps defined by the restriction profile. 

## Restrict an Android kiosk device to a single app

When you set a kiosk device's **Kiosk mode** to **single app kiosk**, users can only access a single app. When users sign on to a single app kiosk device, the specific app starts. Users are restricted from opening new apps or changing the running app.

1. Make sure the app you want to be used on the kiosk device has been [deployed to the device](apps-deploy.md) and that you've assigned the app to the device group you created for your kiosk devices.
2. Go to the [Intune portal](https://portal.azure.com) and choose **Device configuration** > **Profiles** > **Create profile**.
3. In the **Create profile** blade, set the following fields:
     - **Name**
     - **Platform**: Android enterprise
     - **Profile type**: Device restrictions
4. Choose **Settings** > **Kiosk**.
5. For **Kiosk mode** choose **Single app kiosk**.
6. Choose **Select a managed app** and then select the managed app that you want to be the only app available for devices using this profile.
7. Choose **OK** > **OK** > **OK** > **Create**.
8. Choose the profile you just created > **Assignments**.
9. Under **Assign to** choose **Selected groups**.
10. Choose **Select groups to include** > choose the device group that you created for your kiosk devices > **Select**.

## Restrict an Android kiosk device to a specified set of apps and/or web links

When you set a kiosk device's **Kiosk mode** to **multi-app kiosk**, users can only access the limited number of apps that you configure. You can also define a set of web links that users can visit. When users sign in, they see icons for the permissable apps on the home screen.

1. Browse to the [Managed Home Screen page on Google Play](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) and sign in with the same account you use for other managed Google Play apps.
2. Choose **Approve**.
3. Go to the [Intune portal](https://portal.azure.com) and choose **Mobile apps** > **Managed Google Play** > **Sync**.
4. Choose **Apps** > **Managed Home Screen** > **Assignments** > **Add group**.
5. Under **Assignment type** choose **Available for enrolled devices**.
6. Choose **Included groups** > **Select groups to include** > choose the device gropu tha tyou created for your kios devices > **Select** > **OK** > **OK** > **Save**.




 
[Multi-app kiosks](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune) use a kiosk configuration that lists the allowed apps, and other settings.

Enter the following settings:

- **Add Win32 App**: A Win32 app is a traditional desktop app. Enter the **App name**, and the **Identifier**. The **Identifier** is the fully qualified pathname of the executable, with respect to the device.
- **Add managed apps**: Select an existing managed app you added using [Mobile Apps in Intune](apps-add.md).
- **Add app by AUMID**: Enter the [app's AUMID](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (UWP apps).
- **Taskbar**: Choose to **Enable** (show) the taskbar, or keep it **Not configured** (hidden) on the kiosk.
- **Start menu layout**: Enter an XML file that describes how the apps appear on the Start menu, including the order of the apps. [Customize and export Start layout](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) provides some guidance, and sample XML.

  [Create a Windows 10 kiosk that runs multiple apps](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file) provides more details on using and creating XML files.

- **User account type**: Add one or more user accounts that can use the apps you add. When the account signs in, only the apps defined in the configuration are available. The account may be local to the device or an Azure AD account login associated with the kiosk app.

    For kiosks in public-facing environments with autologon enabled, a user type with the least privilege (such as the local standard user account) should be used. To configure an Azure Active Directory (AD) account for kiosk mode, use the `domain\user@tenant.com` format.

## Kiosk web browser settings

These settings control a web browser app on the kiosk. Be sure you deployed a web browser app to the kiosk devices using [Mobile Apps](apps-add.md).

1. Enter the following settings:

  - **Default home page URL**: Enter the default URL the kiosk browser opens when the browser opens or restarts.

  - **Show home button**: Show (**Require**), or hide (**Not configured**) the kiosk browser's home button. By default, the button is Not configured.

  - **Show navigation button**: Show (**Require**), or hide (**Not configured**) the forward and back buttons. By default, the navigation buttons are Not configured.

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

- **User account type**: Select **Local user account** to enter the local (to the device) user account, or a Microsoft Account (MSA) account login associated with the kiosk app. **Autologon** user account types are not supported on Windows Holographic for Business.

#### Multi-app kiosks
Apps in this mode are available on the Start menu. These apps are the only apps the user can open.

Enter the following settings:

- **Add managed apps**: Select an existing managed app you added using [Mobile Apps in Intune](apps-add.md).
- **Add app by AUMID**: Enter the [app's AUMID](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (UWP apps).
- **Start menu layout**: Enter an XML file that describes how the apps appear on the Start menu, including the order of the apps. [Customize and export start layout](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) provides some guidance, and includes a specific XML file for Windows Holographic for Business devices.
- **User account type**: Add one or more user accounts that can use the apps you add. The supported options include: 
  - **HoloLens visitor**: The visitor account is a guest account that doesn't require any user credentials or authentication, as described in [shared PC mode concepts](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).
  - **Azure AD users**: Requires user credentials to sign-in to the device. Use the `domain\user@tenant.com` format.
  - **Local User Accounts**: Requires user credentials to sign-in to the device. 

When the account signs in, only the apps defined in the configuration are available.

## Next steps
[Assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).
