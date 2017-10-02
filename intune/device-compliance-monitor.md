---
# required metadata

title: How to monitor device compliance
titlesuffix: "Azure portal"
description: Learn how to monitor device compliance."
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: muhosabe
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---
# How to monitor device compliance in Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

You can view the summary of the status of your **compliance profiles** in the **Overview** blade.
You can interactively click through the charts to drill down into the details. If you have multiple compliance profiles configured, you can also view the status for each policy by going to the policy blade and choosing **Reports** in the **Manage** section.  The details of the reports available are listed below.

##  Device compliance

The summarized view of the device compliance report shows starts with showing you the aggregated information about the number of devices that are reporting as one of the following:

- **Compliant**: Device has been evaluated for compliance recently and has been determined as compliant with the compliance profile settings you specified.
- **Noncompliant**: The device has been evaluated and determined as noncompliant.  If there was a grace period specified in the profile, the grace period has expired putting the device in a noncompliant status.
- **Grace period**: Device has been evaluated and determined as noncompliant. However, the grace period still applies before the device is actually marked as noncompliant.

You can drill down on each section to see more details on the individual devices and users.

## Setting compliance

The setting compliance report provides the details for each compliance settings such as:

- Number of devices that are noncompliant with the setting.
- The platform that the setting is applied to.

You can drill down on each of the setting to see more information about the profiles on which these settings have been enabled, and the value of the setting.
