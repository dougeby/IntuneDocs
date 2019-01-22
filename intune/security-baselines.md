---
# required metadata

title: Use security baselines in Microsoft Intune - Azure | Microsoft Docs
description: 
keywords:
author: MandiOhlinger 
ms.author: mandia
manager: dougeby
ms.date: 11/20/2018
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

Security baselines is a feature in preview that's available for devices running Windows 10 and later. This feature includes many Intune settings to help secure and protect your users and devices. It also automatically sets these settings to values recommended by security teams. For example, the baseline automatically enables BitLocker, automatically requires a password to unlock a device, automatically disables basic authentication, and more.

The goal of using security baselines is to provide an end-to-end secure workflow when working with Microsoft 365. Some of the benefits include:

- A security baseline includes the best practices and recommendations on settings that impact security. Intune partners with the same Windows security team that creates group policy security baselines. These recommendations are based on guidance and extensive experience.
- If you're brand new to Intune, and not sure where to start, then security baselines gives you an advantage. You can quickly create and deploy a secure profile, knowing that youre helping protect your organization's resources and data.
- If you're currently using group policy, migrating to Intune for management is much easier with these baselines. These baselines are natively built in to Intune, and include a modern management experience.

Security baselines create a configuration profile in Intune. This profile includes all the settings in the baseline. You then apply or assign this profile to your users, groups, and devices.

After the profile is assigned, you can monitor the profile, and monitor the baseline. For example, you can see which devices match the baseline, or don't match the baseline.

  > [!NOTE]
  > While security baselines is in preview, Microsoft does not recommend using profiles in a production environment, as the baselines may change over the course of the preview.

This article shows you how to use security baselines to create a profile, assign the profile, and monitor the profile.

[Windows security baselines](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) is a great resource to learn more about this feature.

## Prerequisites

Security baselines work the same way on Microsoft Intune MDM managed and Configuration Manager co-managed devices. Co-managed devices require you to switch over the **Device configuration** workload. 
  
  [Learn more about switching co-management workloads here](https://docs.microsoft.com/en-us/sccm/comanage/overview#workloads)

## Create the profile

1. In the [Azure portal](https://portal.azure.com/), select **All services** > filter on **Intune** > select **Intune**.
2. Select **Security Baselines (preview)**. A list of the available baselines is available. As more baselines are added, you'll see them here:

    ![See a list of the currently available security baselines](./media/security-baselines/available-baselines.png)

3. Select the baseline you'd like to use.
4. In **Basics**, enter the following properties:

    - **Name**: Enter a name for your security baselines profile. For example, enter `Windows 10 MDM baseline - Oct 2018`.
    - **Description**: Enter some text that describes what this baseline does. The description is for you to enter any text you want.

5. Expand **Settings**. In the list, you see all the settings in this security baseline, and what the setting is automatically set to. These settings are recommended, and can be changed by you.

    ![Expand setting to see all the settings in this security baseline](./media/security-baselines/sample-list-of-settings.png)

    Expand some of the settings to check their values. For example, expand **Windows Defender**. Notice some of the settings, and what they're set to:

    ![See how some of the Windows Defender settings are automatically configured](./media/security-baselines/expand-windows-defender.png)

6. **Create** the profile.

The profile is created. But, it's not doing anything yet. Next, assign the profile.

## Assign the profile

After the profile is created, it's ready to be assigned to your users, devices, and groups. Once assigned, the profile and its settings are applied to the users, devices, and groups you choose.

1. In Intune, select **Security Baselines** > choose a baseline > **Profiles created**.
2. Select your profile > **Assignments**.

    ![Choose your profile, and click assignments](./media/security-baselines/assignments.png)

3. In the **Include** tab, add the groups, users, or devices you want this policy to apply.

    > [!TIP]
    > Notice that you can also **Exclude** groups. If you apply a policy to **All Users**, considering excluding the administrator groups. In case something happens, you and your administrators don’t want to get locked out.

  > [!NOTE]
  > While security baselines is in preview, Microsoft does not recommend using profiles in a production environment, as the baselines may change over the course of the preview.

4. **Save** your changes.

As soon as you save, the profile is pushed to devices when they check in with Intune. So, it can happen immediately.

## Q & A

#### Why these settings?

The Microsoft security team has years of experience working directly with Windows developers and the security community to create these recommendations. The settings in this baseline are considered the most relevant security-related configuration options. In each new build of Windows, the team adjusts its recommendations based on newly released features.

#### Is there a difference in the recommendations for Windows security baselines for group policy vs. Intune?

The same Microsoft security team created the content for each baseline. Intune includes all the relevant settings in the Intune security baseline. There are some settings in the group policy baseline that are specific to an on-premises domain controller. These settings are excluded from Intune's recommendations. All the other settings are the same.

#### Are the Intune security baselines CIS or NSIT compliant?

Strictly speaking, no. The Microsoft security team consults organizations, such as CIS, to compile its recommendations. But, there isn't a one-to-one mapping between “CIS-compliant” and Microsoft baselines.

#### What certifications does Microsoft’s security baselines have? 

- Microsoft continues to publish security baselines for group policies (GPOs) and the [Security Compliance Toolkit](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10), as it has for many years. These baselines are used by many organizations. The recommendations in these baselines are from the Microsoft security team’s engagement with enterprise customers and external agencies, including the Department of Defense (DoD), National Institute of Standards and Technology (NIST), and more. We share our recommendations and baselines with these organizations. These organizations also have their own recommendations that closely mirror Microsoft's. As mobile device management (MDM) continues to grow into the cloud, Microsoft created equivalent MDM recommendations of these group policy baselines. These additional baselines are built into Microsoft Intune, and include compliance reporting on users, groups, and devices that follow (or don't follow) the baseline.

- Many customers are using the Intune baseline recommendations as a starting point, and then customizing it to meet their IT and security demands. Microsoft’s Windows 10 RS5 **MDM Security Baseline** is the first baseline to release. This baseline is built as a generic infrastructure that allows customers to eventually import other security baselines based on CIS, NIST, and other standards. Currently, it's available for Windows and will eventually include iOS and Android.

- Migrating from on-premises Active Directory group policies to a pure cloud solution using Azure Active Directory (AD) with Microsoft Intune is a journey. To help, there are companion GPOs published for hybrid AD and Azure AD-joined devices. These devices can get MDM settings from the cloud (Intune) and group policy settings from on-premises domain controllers as needed.

## Next steps

Check the status and monitor the [baseline and profile](security-baselines-monitor.md).
