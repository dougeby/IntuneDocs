---
# required metadata

title: Check the status of the security baseline in Microsoft Intune - Azure | Microsoft Docs
description: 
keywords:
author: MandiOhlinger 
ms.author: mandia
manager: dougeby
ms.date: 9/12/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Monitor the security baseline and profile in Microsoft Intune

There are different monitoring options when using security baselines. You can monitor the security baselines profile that applies to your users and devices. You can also monitor the actual baseline, and any devices that match (or don't match) the recommended values.

This topic walks you through both monitoring options.

[Security baselines in Intune](security-baselines.md) provides more details on the security baselines feature in Microsoft Intune.

## Monitor the baseline and your devices

Monitoring the baseline gives you insight into the security state of your devices based on Microsoft's recommendations.

1. In the [Azure portal](https://portal.azure.com/), select **All services**, filter on **Intune**, and select **Microsoft Intune**.
2. Select **Security Baselines** > **MDM Security Baseline**.
3. In **Overview**, the graph shows how many devices are impacted by the baseline, and the different statuses:

    INSERT IMAGE WITH DEVICES

  The following status are available:

  - **Matches baseline**: All the settings in the baseline match the Microsoft-recommended settings. 
  - **Does not match baseline**: At least one setting in the baseline doesn't match the Microsoft-recommended settings.
  - **Misconfigured**: At least one setting is not properly configured. This means the setting is in a conflict, error, or pending state.
  - **Not applicable**: At least one setting is not applicable, and thus is not applied.

4. Select one of that statuses that has devices. For example, select the **Device does not match baseline** status:

    INSERT IMAGE

5. A list of all the devices with that status is shown. You can select a specific device to get more details:

    INSERT IMAGE

## Monitor the profile

Monitoring the profile gives you insight into the deployment state of your devices, but not the security state based on Microsoft's baseline recommendations.

1. In Intune, select **Security Baselines** > **MDM Security Baseline** > **Profiles created**.
2. Select a profile. In **Overview**, the images shows you how many devices have this profile assigned: 

    INSERT IMAGE

3. In **Monitor**, you can see the deployment status of the profile on individual devices, the status for each user, and the status for each setting in the baseline:

    INSERT IMAGE

  For example, select **Per-setting status**. In the list, you see all the settings in the security baseline. You are also shown the settings that successfully applied, any settings that have a conflict or error state, and more:

    INSERT IMAGE

## Next steps
[Review all the settings](NEED LINK TO NEW SETTINGS LIST), and their default values.
