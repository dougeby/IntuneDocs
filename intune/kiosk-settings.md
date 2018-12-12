---
# required metadata

title: Kiosk settings for Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Configure your Windows 10 (and later) devices as single-app and multi-app kiosks, including customizing the start menu, adding apps, the task bar, and configuring a web browser. Also configure Windows Holographic for Business devices as multip-app kiosks in Microsoft Intune. 
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2018
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

# Kiosk settings for Windows 10 (and later) in Intune

On Windows 10 devices, you can use Intune to run these devices as a kiosk. The kiosk can run one app, or run many apps. You can also show and customize a start menu, add different apps, including Win32 apps, add a specific home page to a web browser, and more. 

Use this steps in this article to create a single-app kiosk, or multi-app kiosk in Intune.

Intune supports one kiosk profile per device. If you need multiple kiosk profiles on a single device, you can use a [Custom OMA-URI](custom-settings-windows-10.md).

## Kiosk settings

1. In the [Azure portal](https://portal.azure.com), select **All Services**, filter on **Intune**, and select **Microsoft Intune**.
2. Select **Device configuration** > **Profiles** > **Create Profile**.
3. Enter the following properties:

   - **Name**: Enter a descriptive name for the new profile.
   - **Description**: Enter a description for the profile. This setting is optional, but recommended.
   - **Platform**: Select **Windows 10 and later**
   - **Profile type**: Select **Kiosk (Preview)**

4. Select a **kiosk mode**. **Kiosk mode** identifies the type of kiosk mode supported by the policy. Options include:

    - **Not Configured** (default): The policy doesn't enable kiosk mode.
    - **Single app, full-screen kiosk**: The device runs as a single user account, and locks it to a single Store app. So when the user signs in, a specific app starts. This mode also restricts the user from opening new apps, or changing the running app.
    - **Multi app kiosk**: The device runs multiple Store apps, Win32 apps, or inbox Windows apps by using the Application User Model ID (AUMID). Only the apps you add are available on the device.

        The benefit of a multi-app kiosk, or fixed-purpose device, is to provide an easy-to-understand experience for users by only accessing apps they need. And, also removing from their view the apps they don’t need.

## Single full-screen app kiosks
When you choose single app kiosk mode, enter the following settings:

- **User logon type**: The apps you add run as the user account you enter. Your options:

  - **Auto logon (Windows 10 version 1803 and later)**: For kiosks in public-facing environments that don't require the user to logon, similar to a guest account. This setting uses the [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Local user account**: Enter the local (to the device) user account. The account you enter is used to sign in to the kiosk.

- **Application type**: Select **Store app**.

- **App to run in kiosk mode**: Choose **Add a store app**, and select an app from the list.

    Don't have any apps listed? Add some using the steps at [Client Apps](apps-add.md).

    Select **OK** to save your changes.

- **Kiosk browser settings**: These settings control a web browser app on the kiosk. Be sure you get the [Kiosk broswer app](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) from the Store, add it to Intune as a [Client App](apps-add.md), and then assign the app to the kiosk devices.

  Enter the following settings:

  - **Default home page URL**: Enter the default URL shown when the kiosk browser opens or when the browser restarts. For example, enter `http://bing.com` or `http://www.contoso.com`.

  - **Home button**: **Show** or **hide** the kiosk browser's home button. By default, the button isn't shown.

  - **Navigation buttons**: **Show** or **hide** the forward and back buttons. By default, the navigation buttons aren't shown.

  - **End session button**: **Show** or **hide** the end session button. When shown, the user selects the button, and the app prompts to end the session. When confirmed, the browser clears all browsing data (cookies, cache, and so on), and then opens the default URL. By default, the button isn't shown.

  - **Refresh browser after idle time**: Enter the amount of idle time (1-1440 minutes) until the kiosk browser restarts in a fresh state. Idle time is the number of minutes since the user’s last interaction. By default, the value is empty or blank, which means there isn't any idle timeout.

  - **Allowed websites**: Use this setting to allow specific websites to open. In other words, use this feature to restrict or prevent websites on the device. For example, you can allow all websites at `http://contoso.com*` to open. By default, all websites are allowed.
 
      To allow specific websites, upload a file that includes a list of the allowed websites on separate lines. If you don't add a file, all websites are allowed. Intune supports * (asterisk) as a wild card.

      Your sample file should look similar to the following list:

      `http://bing.com`  
      `https://bing.com`  
      `http://contoso.com/*`  
      `https://contoso.com/*`  

  Select **OK** to save your changes.

## Multi-app kiosks

Apps in this mode are available on the start menu. These apps are the only apps the user can open.

When you choose multi app kiosk mode, enter the following settings:

- **Target Windows 10 in S mode devices**: Choose **Yes** to allow store apps and AUMID apps (excludes Win32 apps) in the kiosk profile. Choose **No** to allow store apps, Win32 apps, and AUMID apps in the kiosk profile. When you choose **No**, this kiosk profile isn't deployed to S-mode devices.

- **User logon type**: The apps you add run as the user account you enter. Your options:

  - **Auto logon (Windows 10 version 1803 and later)**: For kiosks in public-facing environments that don't require the user to logon, similar to a guest account. This setting uses the [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Local user account**: **Add** the local (to the device) user account. The account you enter is used to sign in to the kiosk.
  - **Azure AD user or group (Windows 10 version 1803 and later)**: Select **Add** to choose Azure AD users or groups from the list. You can select multiple users and groups. Choose **Select** to save your changes.
  - **HoloLens visitor**: The visitor account is a guest account that doesn't require any user credentials or authentication, as described in [shared PC mode concepts](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Applications**: Add the apps to run on the kiosk device. Remember, you can add several apps.

  - **Add store app**: Add an app from the Microsoft Store for Business. If you don't have any apps listed, then you can get apps, and [add them to Intune](store-apps-windows.md). For example, you can add Kiosk Browser, Excel, OneNote, and more.

  - **Add Win32 App**: A Win32 app is a traditional desktop app, such as Visual Studio Code or Google Chrome. Enter the following properties:

    - **Application name**: Required. Enter a name for the application.
    - **Local path**: Required. Enter the path to the executable, such as `C:\Program Files (x86)\Microsoft VS Code\Code.exe` or `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
    - **Application user model ID (AUMID)**: Enter the Application user model ID (AUMID) of the Win32 app. This setting determines the start layout of the tile on the desktop. To get this ID, see [find the Application User Model ID of an installed app](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps).
    - **Tile size**: Required. Choose a Small, Medium, Wide, or Large app tile size.
  
  - **Add by AUMID**: Use this option to add inbox Windows apps, such as Notepad or Calculator. Enter the following properties: 

    - **Application name**: Required. Enter a name for the application.
    - **Application user model ID (AUMID)**: Required. Enter the Application user model ID (AUMID) of the Windows app. To get this ID, see [find the Application User Model ID of an installed app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Tile size**: Required. Choose a Small, Medium, Wide, or Large app tile size.

  > [!TIP]
  > After you add all the apps, you can change the display order by clicking-and-dragging the apps in the list.  

  Select **OK** to save your changes.

- **Kiosk browser settings**: These settings control a web browser app on the kiosk. Be sure you deploy a web browser app to the kiosk devices using [Client Apps](apps-add.md).

  Enter the following settings:

  - **Default home page URL**: Enter the default URL shown when the kiosk browser opens or when the browser restarts. For example, enter `http://bing.com` or `http://www.contoso.com`.

  - **Home button**: **Show** or **hide** the kiosk browser's home button. By default, the button isn't shown.

  - **Navigation buttons**: **Show** or **hide** the forward and back buttons. By default, the navigation buttons aren't shown.

  - **End session button**: **Show** or **hide** the end session button. When shown, the user selects the button, and the app prompts to end the session. When confirmed, the browser clears all browsing data (cookies, cache, and so on), and then opens the default URL. By default, the button isn't shown.

  - **Refresh browser after idle time**: Enter the amount of idle time (1-1440 minutes) until the kiosk browser restarts in a fresh state. Idle time is the number of minutes since the user’s last interaction. By default, the value is empty or blank, which means there isn't any idle timeout.

  - **Allowed websites**: Use this setting to allow specific websites to open. In other words, use this feature to restrict or prevent websites on the device. For example, you can allow all websites at `contoso.com*` to open. By default, all websites are allowed.

    To allow specific websites, upload a .csv file that includes a list of the allowed websites. If you don't add a .csv file, all websites are allowed.

  Select **OK** to save your changes.

- **Use alternative Start layout**: Choose **Yes** to enter an XML file that describes how the apps appear on the start menu, including the order of the apps. Use this option if you require more customization in your start menu. [Customize and export Start layout](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) provides some guidance, and sample XML.

- **Windows Taskbar**: Choose to **Show** or **hide** the taskbar. By default, the taskbar isn't shown.

## Windows Holographic for Business

On Windows Holographic for Business devices, you can configure these devices to run in single-app kiosk mode, or multi-app kiosk mode. Some features aren't supported on Windows Holographic for Business.

#### Single full-screen app kiosks
When you choose single app kiosk mode, enter the following settings:

- **User logon type**: Select **Local user account** to enter the local (to the device) user account, or a Microsoft Account (MSA) account associated with the kiosk app. **Autologon** user account types aren't supported on Windows Holographic for Business.

- **Application type**: Select **Store app**.

- **App to run in kiosk mode**: Choose **Add a store app**, and select an app from the list.

    Don't have any apps listed? Add some using the steps at [Client Apps](apps-add.md).

    Select **OK** to save your changes.

#### Multi-app kiosks
Apps in this mode are available on the start menu. These apps are the only apps the user can open. When you choose multi app kiosk mode, enter the following settings:

- **Target Windows 10 in S mode devices**: Choose **No**. S mode is not supported on Windows Holographic for Business.

- **User logon type**: Add one or more user accounts that can use the apps you add. Your options: 

  - **Auto logon**: Not supported on Windows Holographic for Business.
  - **Local user accounts**: **Add** the local (to the device) user account. The account you enter is used to sign in to the kiosk.
  - **Azure AD user or group (Windows 10, version 1803 and later)**: Requires user credentials to sign in to the device. Select **Add** to choose Azure AD users or groups from the list. You can select multiple users and groups. Choose **Select** to save your changes.
  - **HoloLens visitor**: The visitor account is a guest account that doesn't require any user credentials or authentication, as described in [shared PC mode concepts](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Applications**: Add the apps to run on the kiosk device. Remember, you can add several apps.

  - **Add Store apps**: Select an existing app you added using [Client Apps](apps-add.md). If you don't have any apps listed, then you can get apps, and [add them to Intune](store-apps-windows.md).
  - **Add Win32 app**: Not supported on Windows Holographic for Business.
  - **Add by AUMID**: Use this option to add inbox Windows apps. Enter the following properties: 

    - **Application name**: Required. Enter a name for the application.
    - **Application user model ID (AUMID)**: Required. Enter the Application user model ID (AUMID) of the Windows app. To get this ID, see [find the Application User Model ID of an installed app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Tile size**: Required. Choose a Small, Medium, Wide, or Large app tile size.

- **Kiosk browser settings**: Not supported on Windows Holographic for Business.

- **Use alternative Start layout**: Choose **Yes** to enter an XML file that describes how the apps appear on the start menu, including the order of the apps. Use this option if you require more customization in your start menu. [Customize and export start layout](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) provides some guidance, and includes a specific XML file for Windows Holographic for Business devices.

- **Windows Taskbar**: Not supported on Windows Holographic for Business.



## Next steps
[Assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).

You can also create kiosk profiles for [Android](device-restrictions-android.md#kiosk) and [Android Enterprise](device-restrictions-android-for-work.md#kiosk-settings) devices.