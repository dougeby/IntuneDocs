---
# required metadata

title: Use security baselines in Microsoft Intune - Azure | Microsoft Docs
description: Learn how to enroll Android work profile devices in Intune.
keywords:
author: MandiOhlinger 
ms.author: mandia
manager: dougeby
ms.date: 9/11/2018
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

# Create a security baseline in Intune

Security baselines are available in Microsoft Intune on devices running Windows 10 and later. This feature includes many Intune settings to help secure and protect your users and devices. It also automatically sets these settings to values recommended by Microsoft. For example, the baseline automatically enables BitLocker, automatically requires a password to unlock a device, automatically disables basic authentication, and more.

The goal of using security baselines is to provide an end-to-end secure workflow when working with Microsoft 365. Some of the benefits include:

- A security baseline includes the best practices and recommendations on settings that impact security. Intune partners with the same Windows security team that creates Group Policy security baselines to offer their extensive experience for guidance and recommendations.
- If you're brand new to Intune, and not sure where to start, then security baselines gives you an advantage. You can quickly create and deploy a secure profile to help protect your organization's resources and data.
- If you're currently using Group Policy, migrating to Intune for management is much easier with these baselines natively built into Intune's modern management platform.

Security baselines creates a configuration profile in Intune. This profile includes all the settings in the baseline. You then apply or assign this profile to your users, groups, and devices.

After the profile is assigned, you can monitor the profile, and monitor the baseline. For example, you can see which devices match the baseline, or don't match the baseline.

This topic shows you how to use security baselines to create a profile, assign the profile, and monitor the profile.

[Windows security baselines](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) is a great resource to learn more about this feature, including using security baselines on Windows server environments.

## Create the profile

1. In the [Azure portal](https://portal.azure.com/), select **All services**, filter on **Intune**, and select **Microsoft Intune**.
2. Select **Security Baselines**. A list of the available baselines are available. As more baselines are added, you'll see them here:

    INSERT IMAGE

3. Select the baseline you'd like to use, for example: **MDM Security Baseline for October 2018** > **Create profile**.
4. In **Basics**, enter the following properties:

    - **Name**: Enter a name for your security baselines profile. For example, enter `Windows 10 MDM baseline - Oct 2018`.
    - **Description**: Enter some text that describes what this baseline does. The description is for you to enter any text you prefer. 

5. Expand **Settings**. In the list, you see all the settings in this security baseline, and what the setting is automatically set to. These settings are recommended by Microsoft, and can be changed by you.

    INSERT IMAGE

  Expand some of the settings to check their values. For example, expand **Windows Defender**. Notice some of the settings, and what they are set to:

    INSERT IMAGE

6. **Create** the profile.

The profile is created. But, it's not doing anything yet. Next, assign the profile.

## Assign the profile

After the profile is created, it's ready to be assigned to your users, devices, and groups. Once assigned, the profile and its settings are applied to the users, devices and groups you choose.

1. In Intune, select **Security Baselines** > **MDM Security Baseline** > **Profiles created**.
2. Select your profile > **Assignments**.

    INSERT IMAGE

3. In the **Include** tab, add the groups, users, or devices you want this policy to apply.

  > [!TIP]
  > Notice that you can also **Exclude** groups. If you apply a policy to **All Users**, considering excluding the administrator groups. In case something happens, you and your administrators don’t want to get locked out.

4. **Save** your changes.

As soon as you save, the profile is pushed to devices when they check-in with Intune. So, this can happen immediately.

## Next steps
[Review all the settings](NEED LINK TO NEW SETTINGS LIST), and their default values.  
Check the status and monitor the [baseline and profile](security-baselines-monitor.md).
