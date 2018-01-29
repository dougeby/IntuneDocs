---
# required metadata

title: Lookout Mobile Threat Defense connector with Intune
titlesuffix: "Azure portal"
description: Set up Lookout Mobile Threat Defense connector with Intune.
keywords:
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 06/09/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3a730a5d-2a90-42b0-aa28-aadfc7a18788

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Lookout Mobile Threat Defense connector with Intune

You can control mobile device access to corporate resources based on risk assessment conducted by Lookout, a Mobile Threat Defense solution integrated with Microsoft Intune. Risk is assessed based on telemetry collected from devices by the Lookout service including:
- Operating system vulnerabilities
- Malicious apps installed
- Malicious network profiles

You can configure conditional access policies based on Lookout's risk assessment enabled through Intune compliance policies. Settings let you allow or block noncompliant devices based on detected threats.

## How do Intune and Lookout Mobile Threat Defense help protect company resources?
Lookout’s mobile app, **Lookout for work**, is installed and run on mobile devices. This app captures file system, network stack, and device and application telemetry where available, then sends it to the Lookout cloud service to assess the device's risk for mobile threats. You can change risk level classifications for threats in the Lookout console to suit your requirements.  

The compliance policy in Intune includes a rule for Lookout Mobile Threat Defense based on Lookout risk assessment. When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.

If the device is found noncompliant, access to resources like Exchange Online and SharePoint Online can blocked. Users on blocked devices receive a steps to resolve the issue and regain access. Guidance is launched from the Lookout for work app.

## Supported platforms
The following platforms are supported for Lookout when enrolled in Intune:
* **Android 4.1 and later**
* **iOS 8 and later**
For additional information about platform and language support, visit the [Lookout website](https://personal.support.lookout.com/hc/articles/114094140253).

## Prerequisites
* Microsoft Intune subscription
* Azure Active Directory
* Lookout Mobile Endpoint Security enterprise subscription  

For more information, see [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)

## Sample scenarios

Here are the common scenarios when using Lookout Mobile Threat Defense with Intune.

### Control access based on threats from malicious apps
When malicious apps such as malware are detected on devices, you can block devices from the following until the threat is resolved:
* Connecting to corporate e-mail
* Syncing corporate files with the OneDrive for Work app
* Accessing company apps

**Block when malicious apps are detected:**

![diagram showing conditional access policy blocking access when device is determined to be noncompliant due to malicious apps on the device](./media/malicious-apps-blocked.png)

**Access granted on remediation:**

![diagram showing conditional access policy granting access when device is determined to be compliant after remediation](./media/malicious-apps-unblocked.png)

### Control access based on threat to network
Detect threats to your network such as man-in-the-middle attacks and protect access to WiFi networks based on the device risk.

**Block network access through WiFi:**

![diagram showing conditional access blocking WiFi access based on network threats](./media/network-wifi-blocked.png)

**Access granted on remediation:**

![diagram showing conditional access allowing access on remediation of the threat](./media/network-wifi-unblocked.png)
### Control access to SharePoint Online based on threat to network

Detect threats to your network such as Man-in-the-middle attacks, and prevent synchronization of corporate files based on the device risk.

**Block SharePoint Online when network threats are detected:**

![Diagram showing conditional access blocking device access to SharePoint Online based on threat detection](./media/network-spo-blocked.png)


**Access granted on remediation:**

![Diagram showing conditional access allowing access after the network threat is remediated](./media/network-spo-unblocked.png)

## Next steps
Here are the main steps you must do to implement this solution:
1.	[Set up your Lookout integration](lookout-mtd-connector-integration.md)
2.	[Enable Lookout Mobile Threat Defense in Intune](mtd-connector-enable.md)
3.  [Add and assign the Lookout for Work app](mtd-apps-ios-app-configuration-policy-add-assign.md)
4.	[Configure Lookout device compliance policy](mtd-device-compliance-policy-create.md)
