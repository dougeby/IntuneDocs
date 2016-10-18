---
# required metadata

title: Device compliance policies | Microsoft Intune
description: This topic explains concepts that help you learn what device compliance policies are and how they work.
keywords:
author: karthikaraman
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Device compliance policies in Microsoft Intune
## What is a compliance policy?
To help protect company data, you need to make sure that the devices used to access company apps and data comply with certain rules, like using a PIN to access the device and encrypting data stored on the device. A set of such rules is called a compliance policy.

## How should I use compliance policies?
You can use compliance policies with conditional access policies to allow only devices that comply with compliance policy rules to access email and other services. To learn how the two policies can be used together, read the [Restrict access to email and O365 services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) article.

You can also use compliance policies independently of conditional access. When you use compliance policies independently, the targeted devices are evaluated and reported with their compliance status. For example, you might want to report about how many devices are not encrypted, or which devices are jailbroken or rooted. But when you use compliance policies independently, no access restrictions to company resources are in place.

You deploy compliance policies to users. When a compliance policy is deployed to a user, the user's devices are checked for compliance.
To learn about how long it takes for mobile devices to get a policy after the policy is deployed, see [Manage settings and features on your devices](https://docs.microsoft.com/en-us/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#frequently-asked-questions-about-intune-policies).

The following table lists the device types that compliance policies support. The table also describes how noncompliant settings are managed when a compliance policy is used with a conditional access policy.

-----------------------------

|Policy setting| Windows 8.1 and later| Windows Phone 8.1 and later| iOS 8.0 and later|Android 4.0 and later<br/>Samsung KNOX Standard 4.0 and later|
|-----|----|----|----|----|
|**PIN or Password Configuration** |Remediated|Remediated|Remediated|Quarantined|
|**Device encryption**|N/A|Remediated|Remediated (by setting PIN)|Quarantined|
|**Jailbroken or rooted device**|N/A|N/A|Quarantined (not a setting)|Quarantined (not a setting)|
|**Email profile**|N/A|N/A|Quarantined|N/A|
|**Minimum OS version**|Quarantined|Quarantined|Quarantined|Quarantined|
|**Maximum OS version**|Quarantined| Quarantined| Quarantined| Quarantined|
|**Windows health attestation**|Windows 10 and Windows 10 Mobile are quarantined.<br /><br />Setting is not applicable to Windows 8.1.|N/A|N/A|N/A|

------------------------------

**Remediated** = Compliance is enforced by the device operating system. (For example, the user is forced to set a PIN.) The setting is always compliant.

**Quarantined** = The device operating system does not enforce compliance. (For example, Android devices do not force the user to encrypt the device.) When the devices is not compliant, the following actions take place:

-   The device is blocked if a conditional access policy applies to the user.

-   The company portal notifies the user about any compliance issues.

## Next steps
[Create a device compliance policy](create-a-device-compliance-policy-in-microsoft-intune.md)

[Deploy and monitor a device compliance policy](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### See also
[Restrict access to email and O365 services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)
