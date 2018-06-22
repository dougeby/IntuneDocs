---
# required metadata

title: Enroll Android kiosk devices in Intune
titlesuffix: "Microsoft Intune"
description: Learn how to enroll Android kiosk devices in Intune.
keywords:
author: ErikjeMS 
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Set up enrollment of Android work profile devices

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune helps you deploy apps and company resources to Android kiosk devices. When successfully deployed, apps and the data they access remain exclusively within the Android enterprise environment on the device. For specific details about Android enterprise, see [Android enterprise requirements](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

To set up Android kiosk management, follow these steps:

1. [Connect your Intune tenant account to your Android enterprise account](connect-intune-android-enterprise.md).
2. [Tell your users how to enroll their devices](../intune-user-help/enroll-your-device-in-intune-android.md).

## Approve the Company Portal app in the managed Google Play store

To ensure that users always have access to the most up-to-date version of the Company portal app, you must approve the Company Portal app for Android in the managed Google Play store. By approving it, you make sure that each user gets automatic updates. If you don't approve it, the Company Portal will eventually become out of date and may not receive important bug fixes or new features when Microsoft releases them.

Follow these steps to approve the Intune Company Portal:

1.  Browse to the Company Portal app on the [managed Google Play store](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Sign into the managed Google Play store with the same Google account that you used to configure the binding for Android enterprise.
3.  Click **Approve** and a new dialog will open.
4.  Review the permissions in this dialog, then click **Approve**. You need these to allow these permissions in order to allow the Company Portal app to manage the work profile on the device.
5.  Select **Keep approved when app requests new permissions**, then click **Save.**




## Next steps for Android work profiles
- [Deploy Android kiosk apps](android-kiosk-enroll.md)
- [Add Android kiosk configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)