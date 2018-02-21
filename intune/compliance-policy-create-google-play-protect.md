---
# required metadata

title: Enable Google Play Protect compliance with Intune
titleSuffix: Azure portal
description: Learn how to create a compliance policy for Android devices to enable Google Play Protect.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/20/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: E9810BEB-000A-4DFB-B5C7-A22A92082B22

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: muhosabe
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to create a device compliance policy to enable Google Play Protect

You can create a new compliance policy for the Android platform to check for Google Play Protect (GPP) compliance.

The compliance policy that requires these settings can then be targeted to a group of Android users or devices. If a device does not have these settings enabled, it falls out of compliance.

## Create a compliance policy

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
2. Choose **Device compliance** in the **Manage** group. 
3. Choose **Policies**, and choose **Create policy**.
4. Type the policy **Name** and **Description**.
5. Select **Android** for the Platform.
6. Choose **Settings** > **Device Health**.
7. Configure the **Google Play Protect** settings.
8. When you have set the Google Play Protect settings, specify the **System Security** and **Device Properties** settings. When you are done, choose **OK**.

## Configure the Google Play Protect settings

 - **Google Play Services is configured**  
   Require that the Google Play services app is installed and enabled. Google Play services allows security updates and is a base-level dependency for many security features on certified-Google devices.
 - **Up-to-date security provider**  
   Require that an up-to-date security provider can protect a device from known vulnerabilities.
 - **Threat scan on apps**  
   Require that the Android **Verify Apps** feature is enabled.
    > [!Note]  
    > On the legacy Android platform, this feature is a compliance setting. Intune can only check whether this setting is enabled at the device level. On devices with work profiles, formerly Android for Work, this setting can be found as a configuration policy setting. This allows administrators to enable the setting for a device.

    If your enterprise uses Android work profiles, you can enabled **Threat scan on apps** for your enrolled devices. Establish a device profile and require the system security setting. For more information, see [Android for Work device restriction settings in Microsoft Intune](device-restrictions-android-for-work.md).

 - **SafetyNet device attestation**  
   Set the level of SafetyNet device attestation integrity that must be met. Levels include **Not configured**, **Check basic integrity**, and **Check basic integrity & certified devices**.




## Next steps

To learn more about working with Intune device compliance policies, see [Get started with Intune device compliance policies](device-compliance-get-started.md).