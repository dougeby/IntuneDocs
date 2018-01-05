---
# required metadata

title: Windows Advanced Threat Protection settings for Windows 10 in Intune
titlesuffix: "Azure portal"
description: Learn the Intune settings you can use to control settings like network isolation policies on Windows 10 devices."
keywords:
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4de090aa-4733-47f9-b66b-839b5c00b848

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: ilwu
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Windows Advanced Threat Protection settings for Windows 10 and later in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The Windows Advanced Threat Protection protection profile let you control security features on Windows 10 devices, like BitLocker and Windows Defender.

Use the information in this topic to learn how to create Windows Advanced Threat Protection protection profiles.

> [!Note]
> These settings are not supported on the Home and Professional editions of Windows 10.

## Create an Windows Advanced Threat Protection profile

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device configuration**.
2. On the **Device Configuration** blade, choose **Manage** > **Profiles**.
3. On the profiles blade, choose **Create profile**.
4. On the **Create profile** blade, enter a **Name** and **Description** for the device features profile.
5. From the **Platform** drop-down list, select **Windows 10 and later**.
6. From the **Profile type** drop-down list, choose **Windows Defender ATP (Windows 10 Desktop)**.
7. Configure the settings you want. Use the details in this topic to help you understand what each setting does. When you are finished, choose **OK**.
8. Go back to the **Create profile** blade, and choose **Create**.

The profile is created and appears on the profiles list blade.

### Network isolation policies (find a place for these somewhere in the docs if not here)

### Windows Defender Device Guard


### Windows Hello for Business

[Windows Hello for Business](windows-hello.md) lets you use a *user gesture* to sign in, instead of a password.



## Windows Defender Advance Threat Protection

Brief explanation of WDATP

### Onboarding and offboarding



### Configuring settings

## Next steps

If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).
