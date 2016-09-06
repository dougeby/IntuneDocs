---
# required metadata

title: Restrict access using mobile threat protection | Microsoft Intune
description: Restrict access to company resources based on device, network and application risk.
keywords:
author: karthikaraman
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod:
ms.service:
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

# Restrict access to company resource based on device, network, and application risk
Microsoft Intune gives you the ability to control access from mobile devices to corporate resources based on risk assessments conducted by mobile threat protection (MTP) solutions.  The risk is based on telemetry that the MTP service collects from devices around operating system (OS) vulnerabilities, installed malicious apps, and network profiles. 
For this release, Microsoft is collaborating with Lookout security to provide you the risk assessment capabilities and compliance policy rule support for **Android devices 4.1 and later**.
## What problem does this solve?
Companies and organizations need to protect sensitive data from emerging threat vectors that include physical, app-based, and network-based threats, as well as OS vulnerabilities.

Historically, companies and organizations have taken an aggressive position of protecting their PCs against malicious attacks. Mobile is an emerging area that often goes unprotected. Although the mobile platform has built-in protection of the OS using techniques such as app isolation and vetted consumer app stores, these platforms continue to be vulnerable to sophisticated attacks. As mobile devices are increasingly used by employees to do work and need access to information that can be sensitive and valuable, these devices need to be protected from a variety of sophisticated attacks.

Intune gives you the ability to control the access to company resources and data based on risk assessment that MTP solutions like Lookout provides.

## How does Intune and Lookout mobile threat protection help protect company resources?
Lookout’s mobile app running on mobile devices will capture file system, network stack, device and application telemetry (where available) and send it to the mobile threat protection (MTP) cloud service to calculate an aggregate device risk for mobile threats. You can also customize the risk level in the MTP console.  
The compliance policy in Intune now includes a new rule for Lookout mobile threat protection. When this rule is enabled, Microsoft Intune then applies a range of non-compliance actions based on the device’s MTP risk assessment calculations.

When the device is determined as noncompliant, access is blocked.   This will launch a remediation experience within the Lookout app that will help the end-users resolve the issue and gain access to company resources.

## Example scenarios
Following are some common scenarios:
### Threat from malicious apps:
When malicious apps such as malware is detected on the device, you can block such devices from:
* Connecting to corporate e-mail before.
* Synchronizing corporate files using the OneDrive for Work app.
* Accessing business critical apps

** Access blocked when malicious apps are detected:**
![diagram showing conditional access policy blocking access when device is determined to be non-compliant due to malicious apps on the device](../media/mtp/malicious-apps-blocked.png)

** Device unblocked and is able to access company resources when the threat is remediated:**

![diagram showing conditional access policy granting access when device is determined to be compliant after remdiation](../media/mtp/malicious-apps_unblocked.png)
### Threat to network:
Detect threats to your network such as Man-in-the-middle attacks and restrict access to Wi-Fi networks based on the device risk.

** Access to network through WiFi blocked:**
![diagram showing conditional access blocking Wi-Fi access based on network threats](../media/mtp/network-wifi-blocked.png)

** Access granted on remediation:**
![diagram showing conditional access allowing access on remediation of the threat](../media/mtp/network-wifi-unblocked.png)
### Threat to network (preving access to SharePoint Online):

Detect threats to your network such as Man-in-the-middle attacks, and prevent synchronization of corporate files based on the device risk.

**  Access blocked SharePoint Online based on network threat detected on the device:**
![Diagram showing conditional access blocking device access to SharePoint Online based on threat detection](../media/mtp/network-spo-blocked.png)

** Access granted on remediation:**

![Diagram showing conditional access allowing access after the network threat is remediated](../media/mtp/network-spo-unblocked.png)

## Next steps
Here are the main steps you must do to implement this solution:
1.	[Setup mobile your Lookout mobile threat protection](set-up-your-subscription-with-lookout-mtp.md)
2.	[Enable Lookout MTP connection in Intune](enable-lookout-mtp-connection-in-intune.md)
3.  [Configure and deploy Lookout for work application](configure-and-deploy-lookout-for-work-apps.md)
4.	[Configure compliance policy](enable-device-threat-protection-rule-in-compliance-policy.md)
5.	[Troubleshooting Lookout Integration](troubleshooting-lookout-integration.md)
