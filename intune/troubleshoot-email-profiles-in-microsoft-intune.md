---
# required metadata

title: Troubleshoot email profiles in Microsoft Intune - Azure | Microsoft Docs
description: Email profile issues and how to troubleshoot and resolve them.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/14/2018
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS:

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-classic
ms.collection: M365-identity-device-management
---

# Troubleshoot email profiles in Microsoft Intune

Review some common email profile issues, and how to troubleshoot and resolve them.

If this information doesn't help, you can also [get support for Microsoft Intune](get-support.md).

## Unable to send images from  email account
Applies to Intune in the Azure classic portal.

Users who have email accounts automatically configured are unable to send pictures or images from their devices. This scenario can happen if **Allow e-mail to be sent from third-party applications** isn't enabled.

### Intune solution

1. Open the Microsoft Intune Administration Console, select **Policy** workload > **Configuration Policy**.

2. Select the email profile and choose **Edit**.

3. Select **Allow e-mail to be sent from third-party applications.**

### Configuration Manager integrated with Intune solution

1. Open the Configuration Manager console > **Assets and Compliance**.

2. Expand **Overview** > **Compliance Settings** > **Company Resource Access**, and select **Email Profiles**.

3. Right-click the e-mail profile, and open **Properties**.

4. On the **Synchronization Settings** tab, select **Allow e-mail to be sent from third-party applications**.

## Device already has an email profile installed

If the user installed an email profile before provisionining an Intune profile, the result of the Intune email profile deployment depends on the device platform:

- **iOS**: Intune detects an existing, duplicate email profile based on hostname and email address. The duplicate email profile created by the user blocks the deployment of an Intune admin-created profile. This is a common problem as iOS users typically create an email profile, then enroll. The company portal updates the user that they aren't compliant due to their manually configured email profile, and prompts the user to remove that profile. The user should remove their email profile so that the Intune profile can be deployed. To prevent this issue, instruct your users to enroll, and allow Intune to deploy the profile. Then, install the user-created email profile.

- **Windows**: Intune detects an existing, duplicate email profile based on hostname and email address. Intune overwrites the existing email profile created by the user.

- **Samsung KNOX Standard**: Intune identifies a duplicate email account based on the email address, and overwrites it with the Intune profile. If the user configures that account, it's overwritten again by the Intune profile. This may cause some confusion to the user whose account configuration gets overwritten.

Samsung KNOX doesn't use hostname to identify the profile. We recommend that you don't create multiple email profiles to deploy to the same email address on different hosts, as they overwrite each other.

## Error  0x87D1FDE8 for KNOX Standard device
**Issue**: After creating and deploying an Exchange Active Sync email profile for Samsung KNOX Standard for various Android devices, the error **0x87D1FDE8** or **remediation failed** is reported in the device's properties > policy tab.

Review the configuration of your EAS profile for Samsung KNOX and source policy. The Samsung Notes sync option is no longer supported and that option should not be selected in your profile. Be sure devices have enough time to process the policy, up to 24 hours.

## Next steps
If this information doesn't help, you can also [get support for Microsoft Intune](get-support.md).
