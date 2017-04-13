---
# required metadata
title: "Known issues in the Microsoft Intune Preview"titleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Read about known issues in the preview"
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/13/2017
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

# Known issues in the Microsoft Intune preview


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Use this topic to learn about any known issues in the Intune preview.

If you want to report a bug that is not listed here, [open a support request](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

If you want to request a new feature be added to Intune, consider filing a report on our [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) site.

## Groups created by Intune during migration might affect functionality of other Microsoft products

When you migrate from classic Intune to the Azure Portal, you might see a new group named **All Users - b0b08746-4dbe-4a37-9adf-9e7652c0b421**. Note that this group contains all users in your Azure Active Directory, not just Intune licensed users. This might cause issues with other Microsoft products if you expect some existing or new users to not be a member of any groups.

## Altering groups created by Intune during migration will delay migration

In preparation for migration, your groups are copied from Intune to Azure AD. Any further changes you make in the classic Intune portal will be updated in the Azure AD group. However, any changes made in Azure AD will not be synchronized back to the classic Intune console. This might result in your migration to the Azure portal failing, and delays to your migration.

##Compliance policies from Intune will not show up in new console. 

Any compliance policies you created in the classic Intune portal are migrated, but are not displayed in the Azure portal. This is because of design change in the Azure portal. Compliance policies you created in the classic Intune portal are still enforced, but you must view and edit them in the classic portal.
Additionally, new compliance policies you create in the Azure portal will not be visible in the classic portal.
For more information, see [What is device compliance](https://docs.microsoft.com/en-us/intune-azure/set-device-compliance/what-is-device-compliance).




## Administration and accounts

Global Admins (also referred to as Tenant Admins) can continue to do day-to-day administration tasks without a separate Intune or Enterprise Mobility Suite (EMS) license. However, if Global Admins want to use the service, such as to enroll their own device, a corporate device, or use the Intune Company Portal, they will need an Intune or EMS license just like any other user.

## Apple enrollment profile migration
In the next few months, Intune will enable managing your Apple Device Enrollment Program and Apple Configurator enrollments through the new Azure Portal. If you delete the Apple Device Enrollment Program token and do not upload an updated token, the original token will be restored in the new Azure Portal as part of migrating your Intune account. To remove this token and prevent DEP enrollment, simply delete the token in the Azure Portal. 
