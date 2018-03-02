---
# required metadata

title: Enable Mobile Threat Defense connector in Microsoft Intune
titlesuffix: "Azure portal"
description: Enable the connector between your Mobile Threat Defense (MTD) partner and Microsoft Intune.
keywords:
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 06/21/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Enable the Mobile Threat Defense connector in Intune

> [!NOTE] 
> This topic applies to all Mobile Threat Defense partners.

During Mobile Threat Defense (MTD) setup, you've configured a policy for classifying threats in your MTD partner console and you've created the device compliance policy in Intune. If you've already configured the Intune connector in the MTD partner console, you can now enable the MTD connection in Intune.

## To enable the MTD connector

1. Go to the [Azure portal](https://portal.azure.com), and sign in with your Intune credentials. After you've successfully signed in, you see the **Azure Dashboard**.

2. On the **Azure Dashboard**, choose **More services** from the left menu, then type **Intune** in the text box filter.

3. Choose **Intune**, the **Intune Dashboard** opens.

4. On the **Intune Dashboard**, choose **Device compliance**, then choose **Mobile Threat Defense** under the **Setup** section.

5. On the **Mobile Threat Defense** blade, choose **Add**.

6. Choose your MTD solution as the **Mobile Threat Defense connector to setup** from the drop-down list.

	![MTD setup in Intune Azure portal](./media/enable-mtd-connector-1.png)

7. Enable the toggle options according to your organization's requirements.

## MTD toggle options

You can decide which MTD toggle options you need to enable according to your organization's requirements. Here are more details:

- **Connect Android 4.1+ devices to [MTD partner name] for Work MTD**: When you enable this option, you can have Android 4.1+ devices reporting security risk back to Intune.
	- **Mark as noncompliant if no data is received**: If Intune doesn't receive data about a device on this platform from the MTD partner, consider the device noncompliant.
<br></br>
- **Connect iOS 8.0+ devices to [MTD partner name] for Work MTD**: When you enable this option, you can have Android 4.1+ devices reporting security risk back to Intune.
	- **Mark as noncompliant if no data is received**: If Intune doesn't receive data about a device on this platform from the MTD partner, consider the device noncompliant.
<br></br>
- **Block unsupported OS versions**: Block if the device is running an operating system less than the minimum supported version.

- **Number of days until partner is unresponsive**: Number of days of inactivity before Intune considers teh partner to be unresponsive because the connection is lost. Intune ignores compliance state for unresponsive MTD partners.

> [!IMPORTANT] 
> You must add and assign the MTD apps before creating the device compliance and the conditional access policy rules. This ensures that the MTD app is ready and available for end users to install before they can get access to email or other company resources.

> [!TIP]
> You can see the **Connection status** and the **Last synchronized** time between Intune and the MTD partner from the Mobile Threat Defense blade.
