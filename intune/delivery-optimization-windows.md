---
# required metadata

title: Delivery optimizatin settings for Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: 
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/16/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Windows 10 (and newer) delivery optimization settings in Microsoft Intune

This article lists and describes all the delivery optimization settings you can configure for Windows 10 devices. These settings are added to a device configuration profile, and then assigned or deployed to your devices using Microsoft Intune.

## Prerequisites

**Software updates – Windows 10 Update Rings** are replaced by the **Delivery optimization** settings. Your existing update rings can be easily moved to the **Delivery optimization** settings using Intune.

1. Create a delivery optimization configuration profile:

    1. In Intune, select **Device configuration** > **Profiles** > **Create profile**.
    2. Enter a **Name** and **Description** for the profile.
    3. For **Platform**, choose **Windows 10 and later**. For **Profile type**, choose **Delivery optimization**.
    4. Select **Settings**. For **Delivery optimization download mode**, choose the same mode used by the existing software update ring. Your options:
        - **Not configured​**
        - **HTTP only, no peering​**
        - **HTTP blended with peering behind the same NAT HTTP blended with peering across a private group​**
        - **HTTP blended with Internet peering​**
        - **Simple download mode with no peering​**
        - **Bypass mode**

2. Assign this new profile to the same devices and users as the existing software update ring. [Assign the profile](device-profile-assign.md) lists the steps.
3. Unconfigure the existing software ring:
    1. In Intune, go to **Software updates** > Windows 10 Update Rings.
    2. In the list, select your update ring.
    3. In the settings, set the **Delivery optimization download mode** to **Not configured**.
    4. **OK** > **Save** your changes.

## Settings

After you 

**Delivery optimization download mode**: Choose how updates are to be delivered to your devices. Your options: 

- **Not configured​**: 

- **HTTP only, no peering​**: 

- **HTTP blended with peering behind the same NAT HTTP blended with peering across a private group​**: Peering occurs on devices in the same Active Directory Site (if it exists) or the same domain by default. When this option is selected, peering crosses NATs.

- **HTTP blended with Internet peering​**: 

- **Simple download mode with no peering​**: Delivery Optimization downloads using HTTP only. It doesn't contact the Delivery Optimization cloud services.

- **Bypass mode**: Do not use Delivery Optimization Use BITS instead.


## Next steps
[Assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md) its status.