---
# required metadata

title: Skycure connector with Intune
titlesuffix: "Azure portal"
description: "Skycure connector integration with Intune."
keywords:
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 12/09/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: df4ce3f6-a093-432c-ab86-7a83865e389e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Skycure Mobile Threat Defense connector

You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Skycure, a mobile threat defense solution that integrates with Microsoft Intune. Risk is assessed based on telemetry collected from devices running Skycure, including:

-   Physical defense

-   Network defense

-   Application defense

-   Vulnerabilities defense

You can configure conditional access policies based on Skycure risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.

## How do Intune and Skycure help protect your company resources?

Skycure mobile app for Android or iOS captures file system, network stack, device and application telemetry where available, then sends it to the Skycure cloud service to assess the device's risk for mobile threats.

The Intune device compliance policy includes a rule for Skycure Mobile Threat Defense, which is based on the Skycure risk assessment. When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.

If the device is found non-compliant, access to resources like Exchange Online and SharePoint Online are blocked. Users on blocked devices receive guidance from the Skycure mobile app to resolve the issue and regain access to corporate resources.

Intune supports two modes of integration with Skycure:

-   **Basic setup** which is a read only mode that allows Skycure visibility for devices in Intune.

-   **Full integration** which allows Skycure to report device risk and security incident details to Intune.

## Sample scenarios

Here are some common scenarios:

### Control access based on threats from malicious apps

When malicious apps such as malware are detected on devices, you can block devices until the threat is resolved:

-   Connecting to corporate e-mail

-   Syncing corporate files with the OneDrive for Work app

-   Accessing company apps

**Block when malicious apps are detected:**

![Malicious apps detected](./media/skycure-arch-1.png)

**Access granted on remediation:**

![Malicious apps detected access granted](./media/skycure-arch-2.png)

### Control access based on threat to network

Detect threats like **Man-in-the-middle** in network, and protect access to Wi-Fi networks based on the device risk.

**Block network access through Wi-Fi:**

![Block network access through Wi-Fi](./media/skycure-arch-3.png)

**Access granted on remediation:**

![Access granted on remediation](./media/skycure-arch-4.png)

### Control access to SharePoint Online based on threat to network

Detect threats like **Man-in-the-middle** in network, and prevent synchronization of corporate files based on the device risk.

**Block SharePoint Online when network threats are detected:**

![Block SharePoint Online when network threats are detected](./media/skycure-arch-5.png)

**Access granted on remediation:**

![Access granted on remediation for Sharepoint example](./media/skycure-arch-6.png)

## Supported platforms

-   **Android 4.1 and later**

-   **iOS 8 and later**

## Pre-requisites

-   Azure Active Directory Premium

-   Microsoft Intune subscription

-   Skycure Mobile Threat Defense subscription

For more information, check [Skycure website](https://www.skycure.com/skycure-microsoft-integration/).

## Next steps

Here are the steps you need to complete to integrate Intune with Skycure:

- [Set up Skycure integration with Intune](skycure-mtd-connector-integration.md)

- [Add and assign Skycure apps, Microsoft Authenticator and iOS app configuration policy](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Create Skycure device compliance policy with Intune](mtd-device-compliance-policy-create.md)

- [Enable Skycure MTD connector in Intune](mtd-connector-enable.md)
