---
# required metadata
title: "Known issues in the Microsoft Intune on Azure"
titleSuffix: "Intune on Azure"
description: Read about known issues in Intune"
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/07/2017
ms.topic: get-started-article
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

# Known issues in the Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Use this topic to learn about any known issues in the Microsoft Intune.

If you want to report a bug that is not listed here, [open a support request](https://docs.microsoft.com/intune-classic/troubleshoot/get-support).

If you want to request a new feature for Intune, consider filing a report on our [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) site.

## Groups created by Intune during migration might affect functionality of other Microsoft products

When you migrate from classic Intune to the Azure, you might see a new group named **All Users - b0b08746-4dbe-4a37-9adf-9e7652c0b421**. This group contains all users in your Azure Active Directory, not only Intune licensed users. This can cause issues with other Microsoft products if you expect some existing or new users to not be a member of any groups.

## Secondary migration required for select capabilities

Intune accounts created before January 2017 require a one-time migration before these capabilities can be managed in the Azure portal:
- Corporate Device Enrollment profiles
- Apple Device Enrollment Program
-	Corporate Pre-enrolled devices by iOS Serial Number group
-	Device Enrollment Managers
-	Apple Volume Purchase Program

Because these capabilities cannot be managed from both the classic Silverlight and Azure consoles, the migration will disable them in the classic console and enable them in the Azure console.  Management of these features will be moved to the Azure Portal. The schedule for migration has not been announced yet, but details will be made available as soon as possible. Be aware of the following change.

#### Removes default Corporate Device Enrollment profiles in Apple DEP
The Azure portal does not support a default Corporate Device Enrollment profile for Apple Device Enrollment Program (DEP) devices. This functionality, available in the classic Silverlight Intune console, is discontinued to prevent unintentional profile assignment. When DEP serial numbers sync in the Azure portal, no Corporate Device Enrollment profile is assigned. An enrollment profile must be assigned prior to using the device.

## Altering groups created by Intune during migration delays migration

In preparation for migration, your groups are copied from Intune to Azure AD. Any further changes you make in the classic Intune portal are updated in the Azure AD group. However, any changes made in Azure AD are not synchronized back to the classic Intune console. This situation might result in your migration to the Azure portal failing, and delays to your migration.

## Compliance policies from Intune do not show up in new console

Any compliance policies you created in the classic Intune portal are migrated, but are not displayed in the Azure portal. This is because of design changes in the Azure portal. Compliance policies you created in the classic Intune portal are still enforced, but you must view and edit them in the classic Intune portal.
Additionally, new compliance policies you create in the Azure portal are not visible in the classic Intune portal.
For more information, see [What is device compliance](device-compliance.md).

## Administration and accounts

Global Admins (also referred to as Tenant Admins) can continue day-to-day administration tasks without a separate Intune or Enterprise Mobility Suite (EMS) license. However, to use the service, such as to enroll their own device, a corporate device, or use the Intune Company Portal, they need an Intune or EMS license.

## Apple enrollment profile migration
In the next few months, Intune enables managing your Apple Device Enrollment Program and Apple Configurator enrollments through the new Azure Portal. If you delete the Apple Device Enrollment Program token and do not upload an updated token, the original token is restored in the new Azure Portal when migrating your Intune account. To remove this token and prevent DEP enrollment, delete the token in the Azure Portal. 

## Using the numeric password type with macOS Sierra devices

Currently, if you select the **Numeric** **Required password type** in a device restriction profile for macOS Sierra devices, it is enforced as **Alphanumeric**. If you want to use a numeric password with these devices, do not configure this setting.
This issue might be corrected in a future version of macOS.

For more information about these settings, see [macOS device restriction settings in Microsoft Intune](device-restrictions-macos.md)
