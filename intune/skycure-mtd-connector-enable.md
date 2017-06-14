---
# required metadata

title: Enable Skycure Mobile Threat Defense connector with Intune
titleSuffix: "Intune Azure preview"
description: Enable Skycure Mobile Threat Defense connector with Intune.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 47f6739c-f891-468f-ad76-64d6f6b352df

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Enable Skycure Mobile Threat Defense in Intune

To enable the Skycure Mobile Threat Defense (MTD) connection in Intune, you should have already configured the [Intune Connector in the Skycure console](skycure-mtd-connector-integration.md).

## To enable the Skycure MTD connection in Intune

1. Go to the [Azure portal](https://portal.azure.com), and sign in with your Intune credentials. After you've successfully signed in, you see the **Azure Dashboard**.

2. On the **Azure Dashboard**, choose **More services** from the left menu, then type **Intune** in the text box filter.

3. Choose **Intune**, you see the **Intune Dashboard**.

4. On the **Intune Dashboard**, choose **Device compliance**, then choose **Mobile Threat Defense** under the **Setup** section.

5. On the **Mobile Threat Defense** blade, choose **Add**.

6. Choose **Skycure** as the **Mobile Threat Defense connector to setup** from the drop-down list.

	![Skycure MTD setup in Intune Azure portal](./media/Intune-azure-skycure-1.png)

7. Enable the toggle options according to your organization's requirements.

> [!NOTE]
> You can see the **Connection status** and the **Last synchronized** time between Intune and the MTD partner from the Mobile Threat Defense blade.

## Skycure MTD toogle options in Intune

You can decide which Skycure MTD toggle options you need to enable according you organization's requirements. Here are more details:

- **Connect Android 4.1+ devices to Skycure for Work MTD**: When you enable this option, you can have Android 4.1+ devices reporting security risk back to Intune.
	- **Mark as non-compliant if no data is received**: If Intune doesn't receive data about a device on this platform from the MTD partner, consider the device non-compliant.
<br></br>
- **Connect iOS 8.0+ devices to Skycure for Work MTD**: When you enable this option, you can have Android 4.1+ devices reporting security risk back to Intune.
	- **Mark as non-compliant if no data is received**: If Intune doesn't receive data about a device on this platform from the MTD partner, consider the device non-compliant.
<br></br>
- **Block unsupported OS versions**: Block if the device is running an operating system less than the minimum supported version.

- **Number of days until partner is unresponsive**: Number of days of inactivity before Intune considers teh partner to be unresponsive because the connection is lost. Intune ignores compliance state for unresponsive MTD partners.

> [!IMPORTANT] 
> You must configure the Skycure apps before creating compliance policy rules and configuring conditional access. This ensures that the app is ready and available for end users to install before they can get access to email or other company resources.

## Next steps

[Create Skycure Mobile Threat Defense device compliance policy](skycure-device-compliance-policy-create.md)
