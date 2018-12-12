---
# required metadata

title: Delivery optimization settings for Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Configure how software updates are delivered to your devices using the delivery optimization cloud services available with Windows 10 and later devices. In Intune, create a device configuration profile to install updates from the internet. Also see how to replace existing update rings with a delivery optimization profile.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/05/2018
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

[Delivery Optimization updates](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) is a great resource to learn more about delivery optimization on Windows 10.

## Settings

**Delivery optimization download mode**: Choose how updates are delivered to your devices. Your options:

- **Not configured​**: End users update their devices using their own methods, which may be to use the **Windows Updates** or **Delivery Optimization** settings available with the OS.
- **HTTP only, no peering​**: Get updates only from the internet. Don't get updates from other computers on your network (called peering or peer-to-peer).
- **HTTP blended with peering behind the same NAT HTTP blended with peering across a private group​**: Get updates from the internet and from other computers on your network. Peering occurs on devices in the same Active Directory Site (if it exists) or the same domain. When this option is selected, peering crosses your Network Address Translation (NATs) IP addresses.
- **HTTP blended with Internet peering​**: Get updates from the internet and from other computers on your network.
- **Simple download mode with no peering​**: Gets updates from the internet, directly from the update owner, such as Microsoft. It doesn't contact the delivery optimization cloud services.
- **Bypass mode**: Use Background Intelligent Transfer Service (BITS) to get updates. Don't use delivery optimization.

## Move from existing update rings to delivery optimization

**Software updates – Windows 10 Update Rings** are replaced by the **Delivery optimization** settings. Your existing update rings can be easily changed to use the **Delivery optimization** settings. Steps:

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

## Next steps

[Assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md) its status.
