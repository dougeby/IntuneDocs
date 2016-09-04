---
# required metadata

title: Enable MTP rule in compliance policy | Microsoft Intune
description: Enable mobile threat protection rule in the device compliance policy.
keywords:
author: karthikaraman
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: sandera
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Enable device threat protection rule in the compliance policy
Intune with Lookout integration gives you the ability to detect mobile threats and make a risk assessment on the device.  
Compliance policy rule allows you to use this risk assessment to determine if the device is compliant with your threat policy. You can then use the conditional access policy to allow or block to Exchange, SharePoint, and other services based on device compliance.

To have Lookout MTP threat detection influence the compliance policy for the device:

1.	The  Device Threat Protection rule must be enabled on the compliance policy.

2.	The Lookout Status page must show **Active**.


## Configure device threat protection rule

We recommend that you set up your subscription with Lookout MTP, and configure the Lookout for work app, before creating the device threat protection rule in the compliancy policy. The compliance rule is only enforced once the setup is completed.

As part of the Lookout MTP configuration, you would have create a threat policy which classifies various threats into high, medium and low categories. Now in the compliance policy rule, you will select the level of threat that is acceptable for the device to be considered compliant.

To enable the device threat protection rule, you can either use an existing compliance policy or create a new one.
In a compliance policy, go to Device Health, and enable Device Threat Protection using the toggle option. Then select the maximum allowed threat level, which is one of the following:
* **None (secured)**: This is the most secure.  This means that the device cannot have any threats.  If the device is detected as having any level of threats, it will be assessed as non-compliant.  Access to company resources is blocked based on your conditional access policies.  
* **Low**: Device is evaluated as compliant if only low level threats are present. Anything higher puts the device in a non-compliant status.
* **Medium**: Device is evaluated as compliant if the threats that are present on the device are low or medium level. If the device is detected to have high level threats, it is determined as non-compliant.
* **High**: This is the least secure. Essentially, this allows all threat levels, and perhaps only useful if you using this solution only  for reporting purposes.

![screenshot showing the device threat protection rule setting in ](../media/mtp/mtp-compliance-policy-rule.png)

![screenshot showing the threat level option for the device threat protection rule setting](../media/mtp/mtp-compliance-policy-setting.png)

If you create conditional access policies for O365 and other services, the above compliance evaluation is taken into consideration, and non-compliant devices are blocked access until the threat is resolved.

You can see the compliance state of a device in the Intune Console.

![screenshot of the devices page in the Intune admin console showing the compliance status of a device](../media/mtp/mtp-device-status-intune-console.png)

## Next steps
* Create conditional access policy
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange On-premises](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune,md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)
