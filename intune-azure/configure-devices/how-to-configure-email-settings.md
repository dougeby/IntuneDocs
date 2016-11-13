---
# required metadata

title: How to configure Microsoft Intune email settings | Microsoft Docs
description: Description.
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 484bd9b0-fbf1-4f4f-940c-6b12fa07e228

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# How to configure email settings in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use the information in this topic to learn the basics about configuring an email profile, and then read further topics for each platform to learn about device specifics.

## Create a device profile containing email settings

1. In the Azure Portal, select the **Device Configurations** workload.
2. On the **Device configuration** blade, select **Manage** > **Profiles**.
3. On the profiles blade, click **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the email profile.
5. From the **Platform** drop-down list, select the device platform to which you want to apply email settings. Currently, you can choose one of the following platforms for email device settings:
	- **Android**
	- **iOS**
	- **Windows Phone 8.1**
	- **Windows 10 and later**
6. From the **Profile** type drop-down list, choose **Email**.
7. Depending on the platform you chose, the settings you can configure will be different. Go to one of the following topics for detailed settings for each platform:
	- [Android settings](email-profile-settings-for-android.md)
	- [iOS settings](email-profile-settings-for-ios.md)
	- [Windows Phone 8.1 settings](email-profile-settings-for-windows-phone-8-1.md)
	- [Windows 10 settings](email-profile-settings-for-windows-10.md)
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.

