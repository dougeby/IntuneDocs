---
# required metadata

title: Enable Lookout Mobile Threat Defense connector in Intune
titleSuffix: "Intune Azure preview"
description: Enable Lookout MTD connector in Intune.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 913a9785-9d8c-4727-9cc5-ebbe9d453e8a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Enable Lookout MTD connector in the Intune Azure portal

To enable the Lookout Mobile Threat Defense (MTD) connection in Intune, you should have already configured the Intune Lookout Mobile Threat Defense Connector in the Lookout console.  If you have not already done so, you should [Set up your Lookout Mobile Threat Defense subscription](lookout-mtd-subscription-setup.md).

## To enable the Lookout MTD connector in Intune 

1. Go to the [Azure portal](https://portal.azure.com), and sign in with your Intune credentials. After you've successfully signed in, you see the **Azure Dashboard**.

2. On the **Azure Dashboard**, choose **More services** from the left menu, then type **Intune** in the text box filter.

3. Choose **Intune**, you see the **Intune Dashboard**.

4. On the **Intune Dashboard**, choose **Device compliance**, then choose **Mobile Threat Defense** under the **Setup** section.

5. On the **Mobile Threat Defense** blade, choose **Add**.

6. Choose **Lookout** as the **Mobile Threat Defense connector to setup** from the drop-down list.

	![Lookout MTD setup in Intune Azure portal](./media/Intune-azure-lookout-1.png)

7. Enable the toggle options according to your organization's requirements.

> [!NOTE]
> You can see the **Connection status** and the **Last synchronized** time between Intune and the MTD partner from the Mobile Threat Defense blade.

## Lookout MTD toogle options in Intune

You can decide which Lookout MTD toggle options you need to enable according you organization's requirements. Here are more details:

- **Connect Android 4.1+ devices to Lookout for Work MTD**: When you enable this option, you can have Android 4.1+ devices reporting security risk back to Intune.
	- **Mark as non-compliant if no data is received**: If Intune doesn't receive data about a device on this platform from the MTD partner, consider the device non-compliant.
<br></br>
- **Connect iOS 8.0+ devices to Lookout for Work MTD**: When you enable this option, you can have Android 4.1+ devices reporting security risk back to Intune.
	- **Mark as non-compliant if no data is received**: If Intune doesn't receive data about a device on this platform from the MTD partner, consider the device non-compliant.
<br></br>
- **Block unsupported OS versions**: Block if the device is running an operating system less than the minimum supported version.

- **Number of days until partner is unresponsive**: Number of days of inactivity before Intune considers teh partner to be unresponsive because the connection is lost. Intune ignores compliance state for unresponsive MTD partners.

> [!IMPORTANT]
> You must configure the Lookout for Work app before creating device compliance policy rules, and configuring conditional access. This ensures that the app is ready and available for the end-users so they can install before getting access to email or other company resources.

## Next steps

The next two steps to fully integrate Lookout with Intune are:

1. Deploy the [Lookout for Work apps](lookout-for-work-app-configure-deploy.md).
2. Setup the [Device compliance policy](lookout-device-compliance-policy-create.md).
