---
# required metadata

title: Intune device restriction settings for Windows Phone 8.1titleSuffix: "Azure portal"
description: Learn the Intune settings you can use to control device settings and functionality on Windows Phone 8.1 devices."
keywords:
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c2d42714-49ca-43b3-b080-2e67a4268198

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Windows Phone 8.1 device restriction settings in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## General

- 	**Camera** - Enables or blocks the device's camera.
- 	**Copy and paste** - Enables or blocks copy and paste functionality on devices.
- 	**Removable storage** - Lets the device use removable storage such as SD cards.
- 	**Geolocation** - Enables the device to utilize location information.
- 	**Microsoft account** - Enable or block the user from linking a Microsoft account to the device.
- 	**Screen capture** - Lets the user capture the contents of the screen as an image file.
- 	**Diagnostic data submission** - Enables the device to submit diagnostic information to Microsoft.
- 	**Custom email accounts sync** - Enables the device to connect to non-Microsoft email accounts.

## Password

- 	**Password** - Require the end user to enter a password to access the device.
	- 	**Required password type** - Specifies the type of password that will be required, such as alphanumeric or numeric only.
	- 	**Minimum password length** - Specifies the minimum number of characters that are required in the password.
	- 	**Simple passwords** - Specifies that simple passwords such as ‘0000’ and ‘1234’ can be used.
	- 	**Number of sign-in failures before wiping device** - Specifies the number of times an incorrect password can be entered before the device is wiped.
	- 	**Maximum minutes of inactivity until screen locks** - Specifies the amount of time a device must remain idle before the screen is automatically locked.
	- 	**Password expiration (days)** - Specifies the number of days before the device password must be changed.
	- 	**Prevent reuse of previous passwords** - Specifies how many previously used passwords are remembered.
- 	**Encryption** - Requires that the data on supported mobile devices be encrypted.

## App Store

- 	**App store** - Lets users connect to the app store from the device.

## Restricted apps

In the restricted apps list, you can configure one of the following lists:

A **Blocked apps** list - List the apps (not managed by Intune) that users are not allowed to install and run.
An **Allowed apps** list - List the apps that users are allowed to install. Apps that are managed by Intune are automatically allowed.

To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.

### How to specify the URL to an app in the store

To specify an app URL in the allowed and blocked apps list, use the following format:

From the [Windows Phone Store](https://www.microsoft.com/store/apps/windows-phone) page, search for the app that you want to use.

Open the app’s page, and copy the URL to the clipboard. You can now use this as the URL in either the allowed or blocked apps list.

Example: Search the store for the Skype app. The URL you use will be **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.



### Additional options

You can also click **Import** to populate the list from a csv file in the format <*app url*>, <*app name*>, <*app publisher*> or click **Export** to create a csv file containing the contents of the restricted apps list in the same format.


## Browser

- 	**Web browser** - Enables or blocks the built-in web browser on devices.

## Cellular and Connectivity

- 	**Wi-Fi** - Enables or disables the Wi-Fi functionality of the device.
- 	**Wi-Fi tethering** - Enables the use of Wi-Fi tethering on the device.
- 	**Automatically connect to Wi-Fi hotspots** - Enables the device to automatically connect to free Wi-Fi hotspots and automatically accept any terms of use.
- 	**Wi-Fi hotspot reporting** - Sends information about Wi-Fi connections to help the user discover nearby connections.
- 	**NFC** - Enables or disables operations that use near field communication on devices that support it.
- 	**Bluetooth** - Enables or disables the Bluetooth functionality of the device.
