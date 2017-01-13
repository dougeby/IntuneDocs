---
# required metadata

title: Protect access using device threat protection | Microsoft Docs
description: Protect access to company resources based on device, network and application risk.
keywords:
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: sandera
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Protect access to company resource based on device, network, and application risk

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

You can control mobile device access to corporate resources based on risk assessment conducted by Lookout, a device threat protection solution integrated with Microsoft Intune. Risk is assessed based on telemetry collected from devices by the Lookout service including:
- Operating system vulnerabilities
- Malicious apps installed
- Malicious network profiles

You can  configure conditional access policies based on Lookout's risk assessment enabled through Intune compliance policies. Settings let you allow or block noncompliant devices based on detected threats.  

## What problem does this solve?
Companies need to protect sensitive data from emerging threats including physical, app-based, and network-based threats, as well as operating system vulnerabilities.

Historically, companies have been proactive when protecting PCs from attack, while mobile devices go unmonitored and unprotected. Mobile platforms have built-in protection such as app isolation and vetted consumer app stores, but these platforms remain vulnerable to sophisticated attacks. Today, more employees use devices for work and need access to sensitive information. Devices need to be protected from increasingly sophisticated attacks.

Intune lets you control access to company resources based on risk assessment that device threat protection solutions like Lookout provides.

## How do Intune and Lookout device threat protection help protect company resources?
Lookout’s mobile app, **Lookout for work**, is installed and run on mobile devices. This app captures file system, network stack, and device and application telemetry where available, then sends it to the Lookout cloud service to assess the device's risk for mobile threats. You can change risk level classifications for threats in the Lookout console to suit your requirements.  

The compliance policy in Intune includes a rule for Lookout mobile threat protection based on Lookout risk assessment. When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.

If the device is found noncompliant, access to resources like Exchange Online and SharePoint Online can blocked. Users on blocked devices receive a steps to resolve the issue and regain access. Guidance is launched from the Lookout for work app.

## Supported platforms:
The following platforms are supported for Lookout when enrolled in Intune:
* **Android 4.1 and later**
* **iOS 8 and later**
For additional information about platform and language support, visit the [Lookout website](https://personal.support.lookout.com/hc/en-us/articles/114094140253).

## Prerequisites:
* Microsoft Intune subscription
* Azure Active Directory
* Lookout Mobile Endpoint Security enterprise subscription  

For more information, see [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)

## Sample scenarios
Following are some common scenarios:

### Control access based on threats from malicious apps
When malicious apps such as malware are detected on devices, you can block devices from the following until the threat is resolved:
* Connecting to corporate e-mail
* Syncing corporate files with the OneDrive for Work app
* Accessing company apps

**Block when malicious apps are detected:**
![diagram showing conditional access policy blocking access when device is determined to be non-compliant due to malicious apps on the device](../media/mtp/malicious-apps-blocked.png)

**Access granted on remediation:**

![diagram showing conditional access policy granting access when device is determined to be compliant after remediation](../media/mtp/malicious-apps-unblocked.png)

### Control access based on threat to network
Detect threats to your network such as Man-in-the-middle attacks and protect access to WiFi networks based on the device risk.

**Block network access through WiFi:**
![diagram showing conditional access blocking WiFi access based on network threats](../media/mtp/network-wifi-blocked.png)

**Access granted on remediation:**

![diagram showing conditional access allowing access on remediation of the threat](../media/mtp/network-wifi-unblocked.png)
### Control access to SharePoint Online based on threat to network

Detect threats to your network such as Man-in-the-middle attacks, and prevent synchronization of corporate files based on the device risk.

**Block SharePoint Online when network threats are detected:**

![Diagram showing conditional access blocking device access to SharePoint Online based on threat detection](../media/mtp/network-spo-blocked.png)


**Access granted on remediation:**

![Diagram showing conditional access allowing access after the network threat is remediated](../media/mtp/network-spo-unblocked.png)

## Next steps
Here are the main steps you must do to implement this solution:
1.	[Set up your subscription with Lookout mobile threat protection](set-up-your-subscription-with-lookout-mtp.md)
2.	[Enable Lookout MTP connection in Intune](enable-lookout-mtp-connection-in-intune.md)
3.  [Configure and deploy Lookout for work application](configure-and-deploy-lookout-for-work-apps.md)
4.	[Configure compliance policy](enable-device-threat-protection-rule-in-compliance-policy.md)
5.	[Troubleshoot Lookout Integration](http://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration)
