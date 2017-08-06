---
# required metadata

title: Configure Windows 10 edition upgrades with Intune
titleSuffix: "Intune on Azure"
description: Learn how to use Intune to upgrade Windows 10 devices you manage to a different edition."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: coryfe
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to configure Windows 10 edition upgrades in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use the information in this topic to learn how to configure a Windows 10 edition upgrade profile. This profile lets you automatically upgrade devices that run one of the following Windows 10 versions to a different edition:

- Windows 10 Home
- Windows 10 Holographic
- Windows 10 Mobile


The following upgrade paths are supported:

- From Windows 10 Pro to Windows 10 Enterprise
- From Windows 10 Home to Windows 10 Education
- From Windows 10 Mobile to Windows 10 Mobile Enterprise
- From Windows 10 Holographic Pro to Windows 10 Holographic Enterprise


## Before you start
Before you begin to upgrade devices to the latest version, you need one of:

- A product key that is valid to install the new version of Windows on all devices that you target with the policy (for Windows 10 Desktop editions). You can use either Multiple Activation Keys (MAK) or Key Management Server (KMS) keys or A license file from Microsoft that contains the licensing information to install the new version of Windows on all devices that you target with the policy (for Windows 10 Mobile and Windows 10 Holographic editions).
- The Windows 10 devices to which you assign the policy must be enrolled in Microsoft Intune. You cannot use the edition upgrade policy with PCs that run the Intune PC client software.

## Create a device profile containing device restriction settings

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device configuration**.
2. On the **Device Configuration** blade, choose **Manage** > **Profiles**.
3. On the profiles blade, choose **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the edition upgrade profile.
5. From the **Platform** drop-down list, choose **Windows 10 and later**.
6. From the **Profile type** drop-down list, choose **Edition upgrade**.
7. On the **Edition Upgrade** blade, configure the following settings:
	- **Edition to upgrade from** - From the drop-down list, select the Windows 10 version that you want to upgrade on devices.
	- **Edition to upgrade to** - From the drop-down list, select the version of Windows 10 Desktop, Windows 10 Holographic, or Windows 10 Mobile that you want to upgrade targeted devices to.
	- **Product Key** - Specify the product key that you obtained from Microsoft, which can be used to upgrade all targeted Windows 10 Desktop devices.<br>.After you create a policy that contains a product key, you cannot edit the product key later. This is because the key is obscured for security reasons. To change the product key, you must enter the entire key again.
	- **License File** - Choose **Browse** to select the license file you obtained from Microsoft that contains license information for the Windows Holographic, or Windows 10 Mobile edition that you want to upgrade targeted devices to.
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile is created and appears on the profiles list blade.

## Next steps

If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).

>[!NOTE]
>If you later remove the policy assignment, the version of Windows on the device is not reverted, and continues to function normally.

