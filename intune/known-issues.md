---
# required metadata
title: "Known issues in Microsoft Intune in the Azure portal"
titlesuffix: "Azure portal"
description: Read about known issues in Intune"
keywords:
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Known issues in Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Use this topic to learn about any known issues in Microsoft Intune.

If you want to report a bug that is not listed here, [open a support request](get-support.md).

If you want to request a new feature for Intune, consider filing a report on our [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) site.

## Migration

### Intune legacy PC client features are only available in the Silverlight console

The ability to manage Windows 10 in the Intune on Azure portal is available via Windows MDM enrollment. For more information, see [Intune on Azure console and legacy Intune PC Client](https://docs.microsoft.com/intune-classic/deploy-use/intune-on-azure).

### Groups created by Intune during migration might affect functionality of other Microsoft products

When you migrate from Intune to the Azure portal, you might see a new group named **All Users - b0b08746-4dbe-4a37-9adf-9e7652c0b421**. This group contains all users in your Azure Active Directory, not only Intune licensed users. This usage can cause issues with other Microsoft products if you expect some existing or new users to not be a member of any groups.

### Status blades for migrated policies do not work

You cannot view status information for policies that were migrated from the classic portal in the Azure portal. However, you can continue to view reports for these policies in the classic portal. To view status information for migrated configuration policies, recreate them in the Azure portal.

## Apps

### iOS volume-purchased apps only available in default Intune tenant language
iOS volume-purchased apps are displayed, and can be assigned only for the same country code as your Intune account. Intune only sync apps from the same iTunes locale as the Intune tenant account country code. For example, if you purchase an app which is only available in the U.S. store, but your Intune account is German, Intune will not show that app.

### Multiple copies of the same iOS volume-purchase program are uploaded
Do not click the **Upload** button multiple times for the same VPP token. This will result in duplicate VPP tokens being uploaded, and apps syncing multiple times for the same VPP token.


<!-- ## Groups -->

## Device configuration

### You cannot save a Windows Information Protection policy for some devices

For devices not enrolled with Intune, you can only specify a primary domain in the **Corporate Identify** field in the settings for a Windows Information Protection policy.
If you add additional domains (using **Advanced settings** > **Network perimeter** > **Add a protected domain**), you cannot save the policy. The error message you see will soon be changed to be more accurate.

### Cisco AnyConnect VPN client support

The latest release of the Cisco AnyConnect VPN client (4.0.07072) is not currently compatible with Intune.
A future Intune update will include compatibility with this VPN client version. Until then, we recommend that you do not update your Cisco AnyConnect VPN client, and continue to use the existing version.

### Using the numeric password type with macOS Sierra devices

Currently, if you select the **Numeric** **Required password type** in a device restriction profile for macOS Sierra devices, it is enforced as **Alphanumeric**. If you want to use a numeric password with these devices, do not configure this setting.
This issue might be corrected in a future version of macOS.

For more information about these settings, see [macOS device restriction settings in Microsoft Intune](device-restrictions-macos.md).

## Compliance

### Compliance policies from Intune do not show up in new console

Compliance policies you created in the classic portal are migrated, but are not displayed in the Azure portal because of design changes in the Azure portal. Compliance policies you created in the Intune classic portal are still enforced, but you must view and edit them in the classic portal.

Additionally, new compliance policies you create in the Azure portal are not visible in the classic portal.

For more information, see [What is device compliance](device-compliance.md).

<!-- ## Enrollment -->


## Data protection

### iOS app protection policies

You can define [app protection policies for iOS](app-protection-policy-settings-ios.md) that are available for users on devices managed through mobile app management (MAM) without enrollment. Due to a temporary error, you can only define these policies for iOS versions with a single decimal point version rather than multiple decimal points. Instead of setting a minimum version of iOS 10.3.1, you set it for iOS 10.3. This will be resolved with a forthcoming update to the iOS SDK.


## Administration and accounts

Global Admins (also referred to as Tenant Admins) can continue day-to-day administration tasks without a separate Intune or Enterprise Mobility Suite (EMS) license. However, to use the service, such as to enroll their own device, a corporate device, or use the Intune Company Portal, they need an Intune or EMS license.

<!-- ## Additional items -->
