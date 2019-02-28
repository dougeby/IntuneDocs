---
# required metadata

title: macOS device feature settings in Microsoft Intune - Azure | Microsoft Docs
description: See all the settings to configure macOS devices for AirPrint in Microsoft Intune. Also see the steps to get the IP address, path, and port settings of an AirPrint server in your network. Use these settings in a device configuration profile to configure macOS devices to use AirPrint servers in your network.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/05/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
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

Intune includes some built-in settings to allow macOS users to print to AirPrint printers in your network. This article lists these settings, and describes what each setting does. It also lists the steps to get the IP address, path, and port of AirPrint printers using the Terminal app (emulator).

## Before you begin

[Create a macOS device configuration profile](device-features-configure.md).

## AirPrint settings

1. In **Settings**, select **AirPrint**. Enter the following properties of the AirPrint server:

    - **IP address**: Enter the IPv4 or IPv6 address of the printer. If you use hostnames to identify printers, you can get the IP address by pinging the printer in the Terminal app. [Get the IP address and path](#get-the-ip-address-and-path) (in this article) provides more details.
    - **Path**: Enter the path of the printer. The path is typically `ipp/print` for printers on your network. [Get the IP address and path](#get-the-ip-address-and-path) (in this article) provides more details.
    - **Port**: Enter the listening port of the AirPrint destination. If you leave this property blank, AirPrint uses the default port. Available on iOS 11.0 and later.
    - **TLS**: Choose **Enable** to secure AirPrint connections with Transport Layer Security (TLS). Available on iOS 11.0 and later.

2. Select **Add**. The AirPrint server is added to the list. You can add many AirPrint servers.

    You can also **Import** a comma-separated file (.csv) that includes a list of AirPrint printers. Also, after you add AirPrint printers in Intune, you can **Export** this list.

3. When finished, select **OK** to save your list.

## Get the IP address and path

To add AirPrinter servers, you need the IP address of the printer, the resource path, and the port. The following steps show you how to get this information.

1. On a Mac that’s connected to the same local network (subnet) as the AirPrint printers, open **Terminal** (from **/Applications/Utilities**).
2. In the Terminal app, type `ippfind`, and select enter.

    Note the printer information. For example, it may return something similar to `ipp://myprinter.local.:631/ipp/port1`. The first part is the name of the printer. The last part (`ipp/port1`) is the resource path.

3. In the Terminal, type `ping myprinter.local`, and select enter.

   Note the IP address. For example, it may return something similar to `PING myprinter.local (10.50.25.21)`.

4. Use the IP address and resource path values. In this example, the IP address is `10.50.25.21`, and the resource path is `/ipp/port1`.

## Next steps

- View all the settings for [iOS](ios-device-features-settings.md) devices.
- Assign this profile to groups; see [assign device profiles](device-profile-assign.md).
