---
# required metadata

title: Configure Intune education settings for iOS | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn about the settings you can use to control education settings on iOS devices."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/18/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 44c427f8-0f22-43c2-8c29-e0f9fa533b1f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# How to configure Intune education settings for iOS devices in Intune Azure preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## Create a device profile containing iOS education settings

1. Sign into the Azure portal.
2. Choose **More Services** > **Other** > **Intune**.
3. On the **Intune** blade, choose **Configure devices**.
2. On the **Device Configuration** blade, select **Manage** > **Profiles**.
3. On the profiles blade, choose **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the edition upgrade profile.
5. From the **Platform** drop-down list, choose **iOS**.
6. From the **Profile type** drop-down list, choose **Education**.
7. On the **Education** blade, select the following:
	- **Teacher root certificate file**
	- **Teacher PKCS12 / PFX profile**
	- **Student root certificate file**
	- **Student PKCS12 / PFX profile**
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.
