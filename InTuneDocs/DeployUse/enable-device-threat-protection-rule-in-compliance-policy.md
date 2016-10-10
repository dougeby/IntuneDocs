---
# required metadata

title: Enable device protection rule in compliance policy | Microsoft Intune
description: Enable mobile threat protection rule in the device compliance policy.
keywords:
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
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
Intune with Lookout mobile threat protection gives you the ability to detect mobile threats and make a risk assessment on the device. You can create an compliance policy rule to include the risk assessment to determine if the device is compliant. You can then use the conditional access policy to allow or block access to Exchange, SharePoint, and other services based on device compliance.

To have Lookout device threat detection influence the compliance policy for the device:

* The  **Device Threat Protection** rule must be enabled on the compliance policy.

* The **Lookout Status** page in the **Intune administrator console** must show as **Active**. See the [Enable Lookout MTP connection in Intune](enable-lookout-mtp-connection-in-intune.md) topic for more details and instructions on how to activate Lookout integration.


Before creating the device threat protection rule in the compliancy policy, we recommend that you [set up your subscription with Lookout device threat protection](set-up-your-subscription-with-lookout-mtp.md), [enable the Lookout connection in Intune](enable-lookout-mtp-connection-in-intune.md),and [configure the Lookout for work app](configure-and-deploy-lookout-for-work-apps.md). The compliance rule enforced only after the setup is completed.

To enable the device threat protection rule, you can either use an existing compliance policy or create a new one.

As part of the Lookout device threat protection setup, in the [Lookout console](https://aad.lookout.com), you created a policy that classifies various threats into high, medium and low levels. In the Intune compliance policy you will use the threat level to set the maximum allowed threat level.

On the **Compliance Policies** page in the **Intune administrator console**, go to **Device Health** and enable the **Device Threat Protection** rule using the toggle option. Then select the maximum allowed threat level, which is one of the following:
* **None (secured)**: This is the most secure.  This means that the device cannot have any threats.  If any level of threats are found, the device is evaluated as non-compliant.  
* **Low**: The device is evaluated as compliant if only low level threats are present. Anything higher puts the device in a non-compliant status.
* **Medium**: The device is evaluated as compliant if the threats found on the device are low or medium level. If high level threats are detected, the device is determined as non-compliant.
* **High**: This is the least secure. Essentially, this allows all threat levels, and perhaps only useful if you are using this solution only  for reporting purposes.

![screenshot showing the device threat protection rule setting in ](../media/mtp/mtp-compliance-policy-rule.png)

![screenshot showing the threat level option for the device threat protection rule setting](../media/mtp/mtp-compliance-policy-setting.png)

If you create conditional access policies for Office 365 and other services, the above compliance evaluation is taken into consideration and non-compliant devices are blocked from accessing company resources until the threat is resolved.

You can see the compliance state of a device on the **All Devices** page of the **Intune administrator console**.

![screenshot of the devices page in the Intune admin console showing the compliance status of a device](../media/mtp/mtp-device-status-intune-console.png)

## Next steps
* Create conditional access policy
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange On-premises](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune,md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)
