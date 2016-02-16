---
title: Protect company data on personal Windows 10 devices with Enterprise Data Protection in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: b97a185c-5772-4b1a-8cfd-ee4775033d76
author: robstackmsft
---
# Protect company data on personal Windows 10 devices with Enterprise Data Protection in Microsoft Intune
With the increase of employee-owned devices in the enterprise, there’s also an increasing risk of accidental data disclosure through apps and services that are outside of the enterprise’s control like email, social media, and the public cloud.

Many of the existing solutions that try to address this issue require employees to switch between personal and work containers and apps  , leading to a less than optimal user experience. The feature code-named Enterprise Data Protection (EDP) offers a better user experience, while helping to better separate and protect enterprise apps and data against disclosure risks across both company and personal devices, without requiring a change in environment.

EDP helps address your everyday challenges in the enterprise, helping you:

-   Avoid potentially negative employee experiences because of your severely restrictive data protection policies.

-   Maintain the privacy of your enterprise data.

-   Manage apps that aren’t policy-aware, especially on mobile devices.

-   Feel more confident about the safety of your enterprise data on employee-owned devices by helping to prevent the accidental release of info.

## Before you start
Before you can use Microsoft Intune to create, manage, and deploy your EDP policy, you must make sure you are managing Windows 10  devices that have been enrolled with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

### Create an Enterprise Data Protection policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Overview** &gt; **Add Policy**.

2.  Click **Windows** &gt; **Enterprise Data Protection (Windows 10 Desktop and Mobile and later)** and then click **Create Policy**.

3.  In the **General** section of the **Create Policy** page, specify a name and a description for the new policy.

4.  In the **Protected apps** section, you can configure a list of apps whose data you would like to protect. Access to Enterprise network locations are restricted to apps that you configure in the protect apps list. Data accessed by apps in this list are encrypted and users are restricted from relocating data out of protected apps. To add apps to the “Protected apps” list

    -   Below the

    -

