---
# required metadata

title: Frequently asked questions about MAM and app protection
description: This article provides answers to some frequently asked questions on Intune mobile application management (MAM) and Intune app protection.
keywords:
author: oydang
ms.author: oydang
manager: mtillman
ms.date: 01/20/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 149def73-9d08-494b-97b7-4ba1572f0623ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: oydang
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Frequently asked questions about MAM and app protection

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

This article provides answers to some frequently asked questions on Intune mobile application management (MAM) and Intune app protection.

## MAM Basics


**What is MAM?** [Intune mobile application management](/intune/app-lifecycle) refers to the suite of Intune management features that lets you publish, push, configure, secure, monitor, and update mobile apps for your users.

**What are the benefits of MAM app protection?** MAM protects an organization's data within an application. With MAM-WE, a work or school-related app that contains sensitive data can be managed on almost any device, including personal devices in bring-your-own-device (BYOD) scenarios. Many productivity apps, such as the Microsoft Office apps, are able to be managed by Intune MAM. See the official list of [Intune-enlightened apps](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) available for public use.

**What device configurations does MAM support?** Intune MAM supports two configurations:
  1. **Intune MDM + MAM**: This is the first configuration supported by MAM when it first launched. IT administrators can only manage apps using MAM and app protection policies on devices that are enrolled with Intune mobile device management (MDM). To manage apps using MDM + MAM, customers should use the Intune standalone console at https://manage.microsoft.com.

  2. **MAM without device enrollment**: MAM without device enrollment, or MAM-WE, allows IT administrators to manage apps using MAM and app protection policies on devices not enrolled with Intune MDM. This means apps can be managed by Intune on devices enrolled with third-party EMM providers. To manage apps using MAM-WE, customers should use the Intune console in the Azure portal at http://portal.azure.com.


## App protection policies

**What are app protection policies**? App protection policies are rules that ensure an organization's data remains safe or contained in a managed app. A policy can be a rule that is enforced when the user attempts to access or move "corporate" data, or a set of actions that are prohibited or monitored when the user is inside the app.

**What are examples of app protection policies?** See the [Android app protection policy settings](../deploy-use/android-mam-policy-settings.md) and [iOS app protection policy settings](../deploy-use/ios-mam-policy-settings.md) for detailed information on each app protection policy setting.

## Apps you can manage with app protection policies

**Which apps can be managed by app protection policies?** Any app that has been enlightened by the [Intune App SDK](/intune/app-sdk) or wrapped by the [Intune App Wrapping Tool](/intune/apps-prepare-mobile-application-management) can be managed using Intune app protection policies. See the official list of [Intune-enlightened apps](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) available for public use.

**What are the baseline requirements to use app protection policies on an Intune-enlightened app?**
  1. The end-user must have an Azure Active Directory (AAD) account. See [Add users and give administrative permission to Intune](/intune/users-permissions-add) to learn how to create Intune users in Azure Active Directory.

  2. The end-user must have a license for Microsoft Intune assigned to their Azure Active Directory account. See [Manage Intune licenses](/intune/licenses-assign) to learn how to assign Intune licenses to end-users.

  3. The end-user must belong to a security group that is targeted by an app protection policy. The same app protection policy must target the specific app being used. App protection policies can be created and deployed in the Intune console in the [Azure portal](http://portal.azure.com). Security groups can currently be created in the [Office portal](http://portal.office.com).

  4. The end-user must sign into the app using his or her AAD account.

**What are the additional requirements to use the [Outlook mobile app](https://www.microsoft.com/outlook-com/mobile/)?**

  1. The end-user must have the Outlook mobile app installed to their device.

  2. The end-user must have an [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online) mailbox and license linked to their Azure Active Directory account.

  >[!NOTE]
  > The Outlook mobile app currently only supports Microsoft Exchange Online and does not support Exchange on-premises or Exchange in Office 365 Dedicated.

**What are the additional requirements to use the [Word, Excel, & PowerPoint](https://products.office.com/business/office) apps?**

  1. The end-user must have a license for [Office 365 Business or Enterprise](https://products.office.com/business/compare-more-office-365-for-business-plans) linked to their Azure Active Directory account. The subscription must include the Office apps on mobile devices and a cloud storage account with [OneDrive for Business](https://onedrive.live.com/about/business/). Office 365 licenses can be assigned in the [Office portal](http://portal.office.com) following these [instructions](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

  2. The end-user must have the [OneDrive](https://onedrive.live.com/about/) app installed to their device and sign in with their AAD account.

  3. The OneDrive app must be targeted by the app protection policy deployed to the end-user.

  >[!NOTE]
  > The Office mobile apps currently only support SharePoint Online and not SharePoint on-premises.

**Why is OneDrive needed for Office?** Intune marks all data in the app as either "corporate" or "personal." Data is considered "corporate" when it originates from a business location. For the Office apps, Intune considers the following as business locations: email (Exchange) or cloud storage (OneDrive app with a OneDrive for Business account).

**What are the additional requirements to use Skype for Business?** See [Skype for Business](https://products.office.com/skype-for-business/it-pros) license requirements.
  >[!NOTE]
  > The Skype for Business mobile app currently only supports Skype for Business Online.

## App protection features

**What is multi-identity support?** Multi-identity support is the ability for the Intune App SDK to only apply app protection policies to the work or school account signed into the app. If a personal account is signed into the app, the data is untouched.

**What is the purpose of multi-identity support?** Multi-identity support allows apps with both "corporate" and consumer audiences (ie. the Office apps) to be released publicly with Intune app protection capabilities for the "corporate" accounts.

**When does the PIN screen show up?** The Intune PIN screen only appears when the user is trying to access "corporate" data in the app. For example, in the Word/Excel/PowerPoint apps, it would appear when the end-user attempts to open a document from OneDrive for Business (assuming you successfully deployed an app protection policy enforcing PIN).

**What about Outlook and multi-identity?** Because Outlook has a combined email view of both personal and "corporate" emails, the Outlook app prompts for the Intune PIN on launch.

**What is the Intune app PIN?** The Personal Identification Number (PIN) is a passcode used to verify that the correct user is accessing the organization's data in an application.

  1. **When is the user prompted to enter their PIN?** Intune will only prompt for the user's app PIN when the user is about to access "corporate" data. In multi-identity apps such as Word/Excel/PowerPoint, the user is prompted for their PIN when they try to open a "corporate" document or file. In single-identity apps, such as line-of-business apps enlightened using the Intune App Wrapping Tool, the PIN is prompted at launch, because the Intune App SDK knows the user's experience in the app is always "corporate."

  2. **Is the PIN secure?** The PIN serves to allow only the correct user to access their organization's data in the app. Therefore, an end-user must sign in with their work or school account before they can set or reset their Intune app PIN. This authentication is handled by Azure Active Directory via secure token exchange and is not transparent to the Intune App SDK. From a security perspective, the best way to protect work or school data is to encrypt it. Encryption is not related to the app PIN, but is its own app protection policy.

  3. **How does Intune protect the PIN against brute force attacks?** As part of the app PIN policy, the IT administrator can set the maximum number of times a user can try to authenticate their PIN before locking the app. After the number of attempts has been met, the Intune App SDK can wipe the "corporate" data in the app.

**What about encryption?** IT administrators can deploy an app protection policy that requires app data to be encrypted. As part of the policy, the IT administrator can also specify when the content is encrypted.

  1. **How does Intune encrypt data?** See the [Android app protection policy settings](../deploy-use/android-mam-policy-settings.md) and [iOS app protection policy settings](../deploy-use/ios-mam-policy-settings.md) for detailed information on the encryption app protection policy setting.

  2. **What gets encrypted?** Only data marked as "corporate" is encrypted according to the IT administrator's app protection policy. Data is considered "corporate" when it originates from a business location. For the Office apps, Intune considers the following as business locations: email (Exchange) or cloud storage (OneDrive app with a OneDrive for Business account). For line-of-business apps enlightened by the Intune App Wrapping Tool, all app data is considered "corporate."

**How does Intune remotely wipe data?** Intune can wipe app data in three different ways: full device wipe, selective wipe for MDM, and MAM selective wipe. For more information about remote wipe for MDM, see [Help protect your data with full or selective wipe using Microsoft Intune](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md). For more information about selective wipe using MAM, see [Wipe managed company app data with Microsoft Intune](../deploy-use/wipe-managed-company-app-data-with-microsoft-intune.md)

  1. **What is full wipe?** [Full wipe](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe) removes all user data and settings from **the device** by restoring the device to its factory default settings. The device is removed from Intune.
  >[!NOTE]
  > Full wipe can only be achieved on devices enrolled with Intune mobile device management (MDM).

  2. **What is selective wipe for MDM?** See [Help protect your data with full or selective wipe using Microsoft Intune](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) to read about selective wipe.

  3. **What is selective wipe for MAM?** Selective wipe for MAM simply removes company app data from an app. The request is initiated using the Intune Azure portal. To learn how to initiate a wipe request, see [Wipe managed company app data with Microsoft Intune](../deploy-use/wipe-managed-company-app-data-with-microsoft-intune.md)

  4. **How quickly does selective wipe for MAM happen?** If the user is using the app when selective wipe is initiated, the Intune App SDK checks every 30 minutes for a selective wipe request from the Intune MAM service. It also checks for selective wipe when the user launches the app for the first time and signs in with their work or school account.

**Why don't On-Premises (on-prem) services work with Intune protected apps?** Intune app protection depends on the identity of the user to be consistent between the application and the Intune App SDK. The only way to guarantee that is through modern authentication. There are scenarios in which apps may work with an on-prem configuration, but they are neither consistent nor guaranteed.

**Is there a secure way to open web links from managed apps?** Yes! The IT administrator can deploy and set app protection policy for the [Intune Managed Browser app](../deploy-use/manage-internet-access-using-managed-browser-policies.md), a web browser developed by Microsoft Intune that can be managed easily with Intune. The IT administrator can require all web links in Intune-enlightened apps to be opened using the Managed Browser app.


## App experience on Android

**Why is the Company Portal app needed for Intune app protection to work on Android devices?** Much of app protection functionality is built into the Company Portal app. Device enrollment is _not required_ even though the Company Portal app is always required. For MAM-WE, the end-user just needs to have the Company Portal app installed on the device.

## App experience on iOS

**I am able to use the iOS share extension to open work or school data in unmanaged apps, even with the data transfer policy set to "managed apps only" or "no apps." Doesn't this leak data?** Intune app protection policy cannot control the iOS share extension without managing the device. Therefore, Intune _**encrypts "corporate" data before it is shared outside the app**_. You can validate this by attempting to open the "corporate" file outside of the managed app. The file should be encrypted and unable to be opened outside the managed app.

### See also
- [Android mobile app management policy settings in Microsoft Intune](../deploy-use/android-mam-policy-settings.md)
- [iOS mobile app management policy settings](../deploy-use/ios-mam-policy-settings.md)
- [Validating your mobile application management setup](../deploy-use/validate-mobile-application-management.md)
- [Get ready to configure mobile app management policies with Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
- [How to get support for Microsoft Intune](../troubleshoot/how-to-get-support-for-microsoft-intune.md)
