---
title: Introduction to device compliance policies in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
author: karthikaraman
---
# Introduction to device compliance policies in Microsoft Intune
## What's a compliance policy?
A **compliance policy** defines the rules and settings that a device must comply with in order to be considered compliant.  Compliance policy settings include security requirements and other properties like PIN, Encryption, and OS version requirements.

## How should I use compliance policies?
You can use compliance policies with conditional access policies to make sure that only devices that comply with these rules are allowed to access company email and data.

You can also use compliance policies independently of conditional access.

You deploy compliance policies to users and devices. When a compliance policy is deployed to a user, then all of the users devices are checked for compliance.

The following table lists the device types supported by compliance policies and how noncompliant settings are managed when the policy is used with a conditional access policy.

|Policy Setting|Windows 8.1 and later|Windows Phone 8.1 and later|iOS 6.0 and later|Android 4.0 and later|Samsung KNOX Standard 4.0 and later|
|:------|:------:|:------:|:-----:|:-------:|
|**PIN or Password Configuration** |Remediated|Remediated|Remediated|Quarantined|Quarantined|
|**Device encryption**|N/A|Remediated|Remediated (by setting PIN)|Quarantined|Quarantined|
|**Jailbroken or rooted device**|N/A|N/A|Quarantined (not a setting)|Quarantined (not a setting)|Quarantined (not a setting)|
|**Email profile**|N/A|N/A|Quarantined|N/A|N/A|
|**Minimum OS version**|Quarantined|Quarantined|Quarantined|Quarantined|Quarantined|
|**Maximum OS version**|Quarantined|Quarantined|Quarantined|Quarantined|Quarantined|
|**Windows health attestation**|Windows 10 and Windows 10 Mobile are Quarantined.<br /><br />Setting is not applicable to Windows 8.1|N/A|N/A|N/A|N/A|
--------------
**Remediated** = Compliance is enforced by the device operating system (for example, the user is forced to set a PIN).  There is never a case when the setting will be noncompliant.

**Quarantined** = The device operating system does not enforce compliance (for example, Android devices do not force the user to encrypt the device).  In this case:

-   The device will be blocked if the user is targeted by a conditional access policy.

-   The company portal or web portal will notify the user about any compliance issues.

## Next Steps
[Create a device compliance policy](create-a-device-compliance-policy-in-microsoft-intune.md)
[Deploy a device compliance policy](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### See also
[Manage access to email and SharePoint with Microsoft Intune](manage-access-to-email-and-O365-services-with-intune.md)
