---
# required metadata

title: Enable device protection rule 
description: Enable mobile threat protection rule in the device compliance policy.
keywords:
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/21/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: sandera
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Create Lookout device compliance policy in Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune with Lookout Mobile Threat Defense lets you detect threats on mobile devices and assess risk on those devices. You can create a compliance policy rule that assesses risk to determine if the device is compliant. You can then use conditional access policy to block access to services based on device compliance.

Prerequisites for compliance policy with Lookout Mobile Threat Defense:

- [Set up Lookout Mobile Threat Defense subscription](setup-your-lookout-mtd-subscription.md)
- [Enable the Lookout connection in Intune](enable-lookout-mtd-connection.md)
- [Configure and deploy the Lookout for work app](configure-deploy-lookout-for-work-app.md)

As part of the Lookout Mobile Threat Defense setup, in the [Lookout console](https://aad.lookout.com), you created a policy that classifies various threats as high, medium and low. In the Intune compliance policy, you set the maximum allowed threat level.

1. In the [Intune administrator console](https://manage.microsoft.com), go to the **Compliance Policies** page. You can either use an existing compliance policy or create a new one. Go to **Device Health** and enable **Device Threat Protection**.
  ![screenshot showing the device threat protection rule setting in ](../media/mtp/mtp-compliance-policy-rule.png)

2. Select the **Maximum allowed threat level**:
  * **None (Secured)**: This is the most secure.  The device cannot have any threats present and still access company resources.  If any threats are found, the device is evaluated as noncompliant.  
  * **Low**: The device is compliant if only low level threats are present. Anything higher puts the device in a noncompliant status.
  * **Medium**: The device is compliant if the threats found on the device are low or medium level. If high level threats are detected, the device is determined as noncompliant.
  * **High**: This is the least secure. This allows all threat levels, and uses Lookout mobile threat protection for reporting purposes only.

![screenshot showing the threat level option for the device threat protection rule setting](../media/mtp/mtp-compliance-policy-setting.png)

If you create conditional access policies for Office 365 or other services, this compliance evaluation is assessed and noncompliant devices are blocked from accessing those services until the threat is resolved.

## Monitor device threats
To see the compliance state of a device, go to the [Intune administrator console](https://manage.microsoft.com) and view **All Devices**.

![screenshot of the devices page in the Intune admin console showing the compliance status of a device](../media/mtp/mtp-device-status-intune-console.png)

## Next steps
* Create conditional access policy
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange On-premises](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)
