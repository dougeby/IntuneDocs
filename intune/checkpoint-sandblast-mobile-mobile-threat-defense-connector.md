---
# required metadata

title: Check Point SandBlast Mobile connector with Intune
titleSuffix: "Intune on Azure"
description: "Check Point SandBlast integration with Intune"
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 706a4228-9bdf-41e0-b8d1-64c923dd2d2b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Check Point SandBlast Mobile Threat Defense connector with Intune

You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Check Point SandBlast Mobile, a mobile threat defense solution that integrates with Microsoft Intune. Risk is assessed based on telemetry collected from devices running the Check Point SandBlast Mobile app.

You can configure conditional access policies based on Check Point SandBlast Mobile risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.

## How do Intune and Check Point SandBlast Mobile help protect your company resources?

Check Point Sandblast Mobile app for Android and iOS captures file system, network stack, device and application telemetry where available, then sends the telemetry data to the Check Point SandBlast cloud service to assess the device's risk for mobile threats.

The Intune device compliance policy includes a rule for Check Point SandBlast Mobile Threat Defense, which is based on the Check Point SandBlast risk assessment. When this rule is enabled, Intune evaluates device compliance with the policy that you enabled. If the device is found non-compliant, users are blocked access to corporate resources like Exchange Online and SharePoint Online. Users also receive guidance from the Check Point SandBlast mobile app installed in their devices to resolve the issue and regain access to corporate resources.

<!-- ## Sample scenarios

Here are some common scenarios:

### Control access based on threats from malicious apps

When malicious apps such as malware are detected on devices, you can block devices until the threat is resolved:

-   Connecting to corporate e-mail

-   Syncing corporate files with the OneDrive for Work app

-   Accessing company apps

**Block when malicious apps are detected:**

<image here>

**Access granted on remediation:**

<image here>

### Control access based on threat to network

Detect threats like **Man-in-the-middle** in network, and protect access to Wi-Fi networks based on the device risk.

**Block network access through Wi-Fi:**

<image here>

**Access granted on remediation:**

<image here>

### Control access to SharePoint Online based on threat to network

Detect threats like **Man-in-the-middle** in network, and prevent synchronization of corporate files based on the device risk.

**Block SharePoint Online when network threats are detected:**

<image here>

**Access granted on remediation:**

<image here> -->

## Supported platforms

-   **Android 4.1 and later**

-   **iOS 8 and later**

## Pre-requisites

-   Azure Active Directory Premium

-   Microsoft Intune subscription

-   Check Point SandBlast Mobile Threat Defense subscription
	-   See [CheckPoint SandBlast website](https://www.checkpoint.com/) for more information.

## Next steps

[Set up CheckPoint SandBlast Mobile app](mtd-apps-ios-app-configuration-policy-add-assign.md)

[Integrate CheckPoint SandBlast with Intune](checkpoint-sandblast-mobile-mtd-connector-integration.md)

[Enable CheckPoint SandBlast Mobile MTD connector](mtd-connector-enable.md)

[Create CheckPoint SandBlast Mobile device compliance policy](mtd-device-compliance-policy-create.md)
