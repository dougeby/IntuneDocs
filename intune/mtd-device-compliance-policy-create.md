---
# required metadata

title: Create Mobile Threat Defense device compliance policy with Intune
titleSuffix: "Intune on Azure"
description: "Create Mobile Threat Defense device compliance policy in Intune"
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Create Mobile Threat Defense (MTD) device compliance policy with Intune

> [!NOTE] 
> This topic applies to all Mobile Threat Defense partners.

Intune with MTD helps you detect threats and assess risk on mobile devices. You can create an Intune device compliance policy rule that assesses risk to determine if the device is compliant or not. You can then use a conditional access policy to block access to services based on device compliance.

## Before you begin

As part of the MTD setup, in the MTD partner console, you created a policy that classifies various threats as high, medium and low. You now need to set the Mobile Threat Defense level in the Intune device compliance policy.

Prerequisites for device compliance policy with MTD:

-   Set up MTD integration with Intune

-   Enable the MTD connector in Intune

## To create a MTD device compliance policy

1.  Go to the [Azure portal](https://portal.azure.com/), and sign in with your Intune credentials.

2.  On the **Azure Dashboard**, choose **More services** from the left menu, then type **Intune** in the text box filter.

3.  Choose **Intune**, the **Intune Dashboard** opens.

4. On the **Intune Dashboard**, choose **Device compliance**, then choose **Policies** under the **Manage** section.

5.  Choose **Create policy**, enter the device compliance **Name**, **Description**, select the **Platform**, then choose **Configure** under the **Settings** section.

6.  On the **compliance policy** blade, choose **Device Health**.

7.  On the **Device Health** blade, choose the Mobile Threat Level from the drop-down list under the **Require the device to be at or under the Mobile threat Defense Level**.

    a.  **Secured**: This is the most secure. The device cannot have any threats present and still access company resources. If any threats are found, the device is evaluated as non-compliant.

    b.  **Low**: The device is compliant if only low level threats are present. Anything higher puts the device in a non-compliant status.

    c.  **Medium**: The device is compliant if the threats found on the device are low or medium level. If high level threats are detected, the device is determined as non-compliant.

    d.  **High**: This is the least secure. This allows all threat levels, and uses Mobile Threat Defense for reporting purposes only. Devices are required to have the MTD app activated with this setting.

8.  Click **OK** twice, then choose **Create**.

> [!IMPORTANT]
> If you create conditional access policies for Office 365 or other services, the device compliance evaluation is assessed and non-compliant devices are blocked from accessing corporate resources until the threat is resolved in the device.

## To assign a MTD device compliance policy

To assign a device compliance policy to users, choose a policy that you have previously configured. Existing policies can be found in the **Device Compliance policies** blade.

1. Choose the policy you want to assign to users and choose **Assignments**. This opens the blade where you can select **Azure Active Directory security groups** and assign them to the policy.

2. Choose **Select groups** to open the blade that displays the Azure AD security groups.  Choosing **Select**  deploys the policy to users.

	> [!NOTE] 
	> You have applied the policy to users. The devices used by the users who are targeted by the policy will be evaluated for compliance.