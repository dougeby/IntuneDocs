---
# required metadata

title: Release notes for Microsoft Intune
description: Intune release notes
keywords:
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Release notes for Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune is an integrated, cloud-based client management solution that provides tools, reports, and upgrade licenses to the latest version of Windows. It also helps keep your computers up-to-date and secure. In addition, Intune lets you manage mobile devices on the network either through Exchange ActiveSync or directly through Intune. The following release notes describe important information and known issues in Microsoft Intune.

<!-- 3-6-17: customer asked if this is still current; Stacie asked Chris Baldwin about it. Chris said it's a Samsung issue, but that he hasn't heard any reports about it for months, so he suggested that I share that with the customer and remove this item from the release notes. I'm only going to comment it out in case it resurfaces.
## Android users can’t send email when conditional access for Exchange Online is implemented

**Issue:** Users running Samsung Android 5.1.1 and later on their devices can't send email when conditional access for Exchange Online has been set up. Samsung acknowledges that the issue is in its built-in email client in Android 5.1.1 and later, and is investigating a fix.

**Workaround 1:** Advise users to use the Outlook app for Android.

**Workaround 2:** To let affected users send email, you can follow these steps:

1. Put each affected user in a security group in the “exempted groups” section of the conditional access policy for Exchange Online.
2. Let the user temporarily sync email on the built-in email client.
3. Remove the affected user from the exempted group, and confirm that the user can now send email.

Microsoft will continue to work closely with Samsung on a fix or additional workarounds.
-->


## Changing resource access profiles between groups for iOS and Android might fail
**Issue:** When you change email or Simple Certificate Enrollment Protocol (SCEP) resource access profiles between groups, the profiles might conflict and fail. For example, let’s say that you have an existing email profile that points to an on-premises Exchange server, targeted to Group A. Then, you create a new email profile that points to Exchange Online, targeted to Group B. When you move users from Group A to Group B, devices will keep the on-premises Exchange email profile and try to install the Exchange Online email profile that is targeted to Group B.

At this point, one of the following occurs: 
* If email profiles A and B are identical, the device rejects email profile B because email profile B already contains email profile A.
* If email profile A is different from email profile B, as mentioned in the example, the device ends up with two email profiles.

> [!NOTE]
> The host name and the attribute used for user name are checked to distinguish one email profile from another.

In both cases, the resource access profile (email profile) was not removed from the device in order to prevent the unintentional removal of a user’s access to email or the client's SCEP certificate.

**Workaround:** None.

## Microsoft Intune App Wrapping Tool for Android has no built-in uninstall capability
**Issue:** The **Microsoft App Wrapping Tool for Android** does not have built-in functionality for uninstalling the tool.

**Workaround:** Browse to the location where you installed the tool, and delete the directory. The default installation location is: **C:\Program Files\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool. For more about the app wrapping tool, see [Prepare Android apps for management with App Wrapping Tool](/intune/app-wrapper-prepare-android).

## Remote assistance is not available on computers that run Windows 8 or Windows 8.1
**Issue:** In this release, the remote assistance feature is not available on computers that run Windows 8 or Windows 8.1.

**Workaround:** None.

## Alert notifications for recipients that are automatically added might not work
**Issue:** If recipients are automatically added to an alert notification, they might not always receive a notification.

**Workaround:** To make sure that recipients will receive message notifications, you should manually add recipients to alert notifications.

## Language support in the Azure portal
The Azure portal supports these languages: Chinese (Simplified), Chinese (Traditional), Czech, Dutch, English, German, Hungarian, Italian, Japanese, Portuguese (Brazil), Portuguese (Portugal), Russian, Spanish, English, French, Korean, Polish, Swedish, Turkish.

The Intune Admin Console and the user-facing mobile experiences support Danish, Greek, Finnish, Norwegian, and Romanian, in addition to all the languages that the Azure portal supports.
