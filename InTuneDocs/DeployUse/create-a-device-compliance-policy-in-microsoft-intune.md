---
title: Create a compliance policy in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service:
ms.suite: na
ms.tgt_pltfrm: na
ms.topic:
ms.assetid:
author: karthikaraman
---
# Create a compliance policy in Microsoft Intune

##  Step1: Add a Policy
  In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Compliance Policies** &gt; **Add**.

  ![Screenshot of the compliance policy page in the Intune admin console, showing the add option in the menu at the top of page](./media/intune-sa-3a-add-compliance-policy.png)

##  Step2:  Configure settings
On the **Create Policy** page, configure the settings you require:
  -   The System security settings like password, and encryption
  -   Device health settings like whether or not a device is jailbroken or is reported healthy by the Windows device health attestation service.
  -   Device property settings like the miniumum OS version required or maximum OS version allowed.
![IntuneSA3bCreatePolicy](./media/intune-sa-3b-create-policy.png)

##  Step3: Save the policy
When you are finished, choose **Save Policy**.

You will be given the option to deploy the policy now, or you can choose to deploy it later. The new policy displays in the **Compliance Policies** node of the **Policy** workspace.

Select one of the following to review the list of compliance settings supported on each platform:
> [!div class="op_single_selector"]
- [Compliance policy settings for iOS devices](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Compliance policy settings for Android devices](android-compliance-policy-settings-in-microsoft-intune.md)
- [Compliance policy settings for Windows devices](windows-compliance-policy-settings-in-microsoft-intune.md)


## Next Steps
[Deploy and monitor a compliance policy](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### See also
[Introducution to device compliance policies](introduction-to-device-compliance-policies-in-microsoft-intune.md)
