---
# required metadata

title: Troubleshoot email profiles 
description: Email profile issues and how to troubleshoot and resolve them.
keywords:
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: tscott
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Troubleshoot email profiles in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Listed here are some email profile issues and how to troubleshoot and resolve them.

If this information does not solve your problem, see [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) to find more ways to get help.


## Unable to send images from  email account
Users who have email accounts automatically configured are unable to send pictures or images from their devices.
This occurs when the option **Allow e-mail to be sent from third-party applications** is not enabled.

### Intune solution

1.  Open the Microsoft Intune Administration Console, select **Policy** workload &gt; **Configuration Policy**.

2.  Select the email profile and choose **Edit**.

3.  Select **Allow e-mail to be sent from third-party applications.**

### Configuration Manager integrated with Intune solution

1.  Open the Configuration Manager console &gt; **Assets and Compliance**.

2.  Expand **Overview** -&gt; **Compliance Settings** -&gt; **Company Resource Access**, and select **Email Profiles**.

3.  Right-click the e-mail profile, and open **Properties**.

4.  On the **Synchronization Settings** tab, select **Allow e-mail to be sent from third-party applications**.


## Device already has an email profile installed

If the user has installed an email profile prior to provision of a profile by Intune, the result of the Intune email profile deployment depends on the device platform:

-**iOS**: Intune detects an existing, duplicate email profile based on hostname and email address. The duplicate email profile created by the user will block the deployment of an Intune admin-created profile. This is a common problem as iOS users will typically create an email profile, then enroll. The company portal will inform the user that they are not compliant due to their manually-configured email profile, and will prompt the user to remove that profile.The user should remove their email profile so that the Intune profile can be deployed. To prevent the problem instruct your users to enroll before installing an email profile and to allow Intune to deploy the profile.

-**Windows**: Intune detects an existing, duplicate email profile based on hostname and email address. Intune will overwrite the existing email profile created by the user.

-**Samsung KNOX Standard**: Intune identifies a duplicate email account based on the email address, and will overwrite it with the Intune profile. If the user configures that account, it will be overwritten again by the Intune profile. Note that this may cause some confusion to the user whose account configuration gets overwritten.

Since Samsung KNOX does not use hostname to identify the profile, we recommend that you not create multiple email profiles to deploy to the same email address on different hosts, as these will overwrite each other.

## Error  0x87D1FDE8 for KNOX Standard device
**Issue**: After creating and deploying an Exchange Active Sync email profile for Samsung KNOX Standard for various Android devices, the error **0x87D1FDE8** or **remediation failed** is reported in the device's properties &gt; policy tab.

Review the configuration of your EAS profile for Samsung KNOX and source policy. The Samsung Notes sync option is no longer supported and that option should not be selected in your profile. Be sure devices have had enough time to process the policy, up to 24 hours.

## Next steps
If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
