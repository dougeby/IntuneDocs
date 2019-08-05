---
# required metadata

title: macOS device feature settings in Microsoft Intune - Azure | Microsoft Docs
description: See the settings to configure macOS devices for AirPrint and customize the Login window to show or hide power buttons in Microsoft Intune. See the steps to get the IP address, path, and port settings of an AirPrint server in your network. Use these settings in a device configuration profile to configure macOS device features.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
search.appverid:
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# macOS device feature settings in Intune

Intune includes some built-in settings to customize features on your macOS devices. This article lists these settings, and describes what each setting does. It also lists the steps to get the IP address, path, and port of AirPrint printers using the Terminal app (emulator).

This feature applies to:

- macOS

As part of your mobile device management (MDM) solution, use these settings to create a banner, choose how users sign in, add an AirPrint server, and more.

These settings are added to a device configuration profile in Intune, and then assigned or deployed to your macOS devices.

## Before you begin

[Create a macOS device configuration profile](device-features-configure.md).

## AirPrint

- **IP address**: Enter the IPv4 or IPv6 address of the printer. If you use host names to identify printers, you can get the IP address by pinging the printer in the Terminal app. [Get the IP address and path](#get-the-ip-address-and-path) (in this article) provides more details.
- **Path**: Enter the path of the printer. The path is typically `ipp/print` for printers on your network. [Get the IP address and path](#get-the-ip-address-and-path) (in this article) provides more details.
- **Port** (iOS 11.0 and later): Enter the listening port of the AirPrint destination. If you leave this property blank, AirPrint uses the default port.
- **TLS** (iOS 11.0 and later): Select **Enable** to secure AirPrint connections with Transport Layer Security (TLS).

**Add** The AirPrint server. You can add many AirPrint servers.

- **Import** (optional): You can also **Import** a comma-separated file (.csv) that includes a list of AirPrint printers. Also, after you add AirPrint printers in Intune, you can **Export** this list.

Select **OK** to save your settings.

### Get the IP address and path

To add AirPrinter servers, you need the IP address of the printer, the resource path, and the port. The following steps show you how to get this information.

1. On a Mac that’s connected to the same local network (subnet) as the AirPrint printers, open **Terminal** (from **/Applications/Utilities**).
2. In the Terminal app, type `ippfind`, and select enter.

    Note the printer information. For example, it may return something similar to `ipp://myprinter.local.:631/ipp/port1`. The first part is the name of the printer. The last part (`ipp/port1`) is the resource path.

3. In the Terminal, type `ping myprinter.local`, and select enter.

   Note the IP address. For example, it may return something similar to `PING myprinter.local (10.50.25.21)`.

4. Use the IP address and resource path values. In this example, the IP address is `10.50.25.21`, and the resource path is `/ipp/port1`.

## Login items

- **Files, folders, and custom apps**: **Add** the path of a file, folder, custom app, or system app you want to open when a user signs in to the device. System apps, or apps built or customized for your organization are typically in the `Applications` folder, with a path similar to `/Applications/AppName.app`. 

  For example, enter `/Applications/Calculator.app`, `/Applications`, or `/Applications/Microsoft Office/root/Office16/winword.exe`. Locations of items may vary, they are not always in the Applications folder. If a user moves an item from one location to another, the path changes and the item will no longer be launched at login. 

  You can add many files, folders, and apps. When adding any app, folder, or file be sure to enter the correct path.

## Login window

### Window Layout

- **Show additional information in the menu bar**: When the time area on the menu bar is selected, **Allow** shows the host name and macOS version. **Not configured** (default) doesn't show this information on the menu bar.
- **Banner**: Enter a message that's shown on the sign in screen on the device. For example, enter your organization information, a welcome message, lost and found information, and so on.
- **Choose login format**: Choose how users sign in to the device. Your options:
  - **Prompt for username and password** (default): Requires users to enter a username and password.
  - **List all users, prompt for password**: Requires users to select their username from a user list, and then enter their password. Also configure:

    - **Local users**: **Hide** doesn't show the local user accounts in the user list, which may include the standard and admin accounts. Only the network and system user accounts are shown. **Not configured** (default) shows the local user accounts in the user list.
    - **Mobile accounts**: **Hide** doesn't show mobile accounts in the user list. **Not configured** (default) shows the mobile accounts in the user list. Some mobile accounts may show as network users.
    - **Network users**: Select **Show** to list the network users in the user list. **Not configured** (default) doesn't show the network user accounts in the user list.
    - **Admin users**: **Hide** doesn't show the administrator user accounts in the user list. **Not configured** (default) shows the administrator user accounts in the user list.
    - **Other users**: Select **Show** to list **Other...** users in the user list. **Not configured** (default) doesn't show the other user accounts in the user list.

### Login screen power settings

- **Shut Down button**: **Hide** doesn't show the shutdown button on the sign in screen. **Not configured** (default) shows the shutdown button.
- **Restart button**: **Hide** doesn't show the restart button on the sign in screen. **Not configured** (default) shows the restart button.
- **Sleep button**: **Hide** doesn't show the sleep button on the sign in screen. **Not configured** (default) shows the sleep button.

### Other

- **Disable user login from Console**: **Disable** hides the macOS command line used to sign in. For typical users, **Disable** this setting. **Not configured** (default) allows advanced users to sign in using the macOS command line. To enter console mode, users enter `>console` in the Username field, and must authenticate in the console window.

### Apple Menu

After users sign in to the devices, the following settings impact what they can do.

- **Disable Shut Down**: **Disable** prevents users from selecting the **Shutdown** option after the user signs in. **Not configured** (default) allows users to select the **Shutdown** menu item on the device.
- **Disable Restart**: **Disable** prevents users from selecting the **Restart** option after the user signs in. **Not configured** (default) allows users to select the **Restart** menu item on the device.
- **Disable Power Off**: **Disable** prevents users from selecting the **Power off** option after the user signs in. **Not configured** (default) allows users to select the **Power off** menu item on the device.
- **Disable Log Out** (macOS 10.13 and later): **Disable** prevents users from selecting the **Log out** option after the user signs in. **Not configured** (default) allows users to select the **Log out** menu item on the device.
- **Disable Lock Screen** (macOS 10.13 and later): **Disable** prevents users from selecting the **Lock screen** option after the user signs in. **Not configured** (default) allows users to select the **Lock screen** menu item on the device.

Select **OK** to save your settings.

## Next steps

- View all the settings for [iOS](ios-device-features-settings.md) devices.
- [Assign this profile](device-profile-assign.md) to your groups, and [monitor its status](device-profile-monitor.md).
