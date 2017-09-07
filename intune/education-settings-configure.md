---
# required metadata

title: Configure Intune education settings for Windows 10titleSuffix: "Azure portal"
description: Learn how to use Intune to configure Windows 10 education settings on devices you manage."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to configure Windows 10 education settings in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Education profiles let you specify details that configure the Windows Take a Test app including account details, and the test URL. When you configure this, the Take a Test app opens with the test you specify, and no other apps can be run on the device until the test is complete.

Use the information in this topic to learn the basics about configuring device restriction profiles, and then read further topics for each platform to learn about device specifics.

## Create a device profile containing education profile settings

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device configuration**.
2. On the **Device Configuration** blade, choose **Manage** > **Profiles**.
3. On the profiles blade, choose **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the device restriction profile.
5. From the **Platform** drop-down list, select **Windows 10 and later**.
6. From the **Profile type** type drop-down list, choose **Education profile**. 
7. Choose Settings > Configure, then, on the **Take a Test** blade, configure the following:
	- **Account user name** - Enter the user name of the account used with Take a Test. This can be a domain account, an Azure Active Directory (AAD) account, or a local computer account.
	- **Assessment URL** - Provide the URL of the test you want users to take. For more information, see the Take a Test documentation.
	- **Screen monitoring** - Specify whether you want to be able to monitor screen activity while users are taking a test.
	- **Text suggestion** - Allow or block text suggestions while users are taking a test.
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.
If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).



