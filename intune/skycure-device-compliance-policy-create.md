---
# required metadata

title: Create Skycure device compliance policy with Intune
titleSuffix: "Intune Azure preview"
description: "Create Skycure Mobile Threat Defense device compliance policy in the Intune Azure portal"
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6c06b964-e999-45b2-8698-c4bd26ee9b70

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Create Skycure Mobile Threat Defense device compliance policy with Intune

Intune with Skycure Mobile Threat Defense lets you detect threats on mobile devices and assess risk on those devices. You can create an Intune compliance policy rule that assesses risk to determine if the device is compliant. You can then use conditional access policy to block access to services based on device compliance.

## Before you begin

Prerequisites for compliance policy with Skycure device threat protection:

-   [Set up Skycure integration with Intune](skycure-mtd-connector-integration.md)

-   [Enable the Skycure connection in Intune](skycure-mtd-connector-enable.md)

As part of the Skycure Mobile Threat Defense setup, in the Skycure console, you created a policy that classifies various threats as high, medium and low. You now need to set the maximum allowed threat level in the Intune compliance policy.

## To create Skycure compliance policy

1.  Go to the [Intune classic console](https://manage.microsoft.com/) then enter your credentials.

2.  Choose **Policy** &gt; **Compliance Policies**. You can either use an existing compliance policy or create a new one.

3.  Choose **Add** &gt; **Device Health**, then enable **Device Threat Protection**.

4.  Select the **Maximum allowed threat level**:

    a.  **None (Secured)**: This is the most secure. The device cannot have any threats present and still access company resources. If any threats are found, the device is evaluated as non-compliant.

    b.  **Low**: The device is compliant if only low level threats are present. Anything higher puts the device in a non-compliant status.

    c.  **Medium**: The device is compliant if the threats found on the device are low or medium level. If high level threats are detected, the device is determined as non-compliant.

    d.  **High**: This is the least secure. This allows all threat levels, and uses Skycure Mobile Threat Defense for reporting purposes only.

> [!IMPORTANT]
> If you create conditional access policies for Office 365 or other services, this compliance evaluation is assessed and non-compliant devices are blocked from accessing those services until the threat is resolved.
