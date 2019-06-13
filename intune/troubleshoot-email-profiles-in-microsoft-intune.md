---
# required metadata

title: Troubleshoot email profiles in Microsoft Intune - Azure | Microsoft Docs
description: See common issues and solutions with email profiles in Microsoft Intune, including duplicate email profiles and errors on Samsung KNOX Standard Android devices.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
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

# Common issues and resolutions with email profiles in Microsoft Intune

Review some common email profile issues, and how to troubleshoot and resolve them.

- Email profiles can only be deployed for the user who enrolled the device. Intune uses the AAD attributes (specified in the email profile) of the user during enrollment to configure the email profile.
- After migrating from CM hybrid to Intune Standalone, the email profile from CM hybrid stays on the device for 7 days. This is expected behavior. Contact support if you need the email profile removed sooner.
- For Android Enterprise, ensure you have also deployed Gmail or Nine for Work using the Managed Play Store [Add Managed Google Play apps](apps-add-android-for-work.md)
- Microsoft Outlook for iOS and Android doesn't support email profiles, instead deploy an app configuration policy, see [Outlook Configuration setting](app-configuration-policies-outlook.md)
- Email profile targeted to device group isn't delivered to the device. As long as the device has an associated primary user then device targeting will work. However if the email profile contains user certificates then you will need to target user groups. 
- Users are prompted repeatedly to enter their password for the email profile. Check all the certs in the chain that is referenced in the email profile. If one of the certs is not targeted to the user, then the Intune service will keep retrying the email profile.

## Device already has an email profile installed

If users create an email profile before enrolling in Intune or Office 365 MDM, the email profile deployed by Intune may not work as expected:

- **iOS**: Intune detects an existing, duplicate email profile based on hostname and email address. The user-created email profile blocks the deployment of the Intune-created profile. This is a common problem as iOS users typically create an email profile, then enroll. The Company Portal app states that the user isn't compliant, and may prompt the user to remove the email profile.

  The user should remove their email profile so the Intune profile can be deployed. To prevent this issue, instruct your users to enroll, and allow Intune to deploy the email profile. Then, users can create their email profile.

- **Windows**: Intune detects an existing, duplicate email profile based on hostname and email address. Intune overwrites the existing email profile created by the user.

- **Samsung KNOX Standard**: Intune identifies a duplicate email account based on the email address, and overwrites it with the Intune profile. If the user configures that account, it's overwritten again by the Intune profile. This may cause some confusion to the user whose account configuration gets overwritten.

Samsung KNOX doesn't use hostname to identify the profile. We recommend you don't create multiple email profiles to deploy to the same email address on different hosts, as they overwrite each other.

## Error 0x87D1FDE8 for KNOX Standard device

**Issue**: After creating and deploying an Exchange Active Sync email profile for Samsung KNOX Standard for different Android devices, the **0x87D1FDE8** or **remediation failed** error shows in the device's properties > policy tab.

Review the configuration of your EAS profile for Samsung KNOX and source policy. The Samsung Notes sync option is no longer supported, and that option shouldn't be selected in your profile. Be sure devices have enough time to process the policy, up to 24 hours.

## Unable to send images from  email account

Users who have email accounts automatically configured can't send pictures or images from their devices. This scenario can happen if **Allow e-mail to be sent from third-party applications** isn't enabled.

### Intune solution

1. Open the Microsoft Intune Console, select  **Device Configuration** workload.

2. Select the email profile and choose **Edit**.

3. Enable the setting **Allow e-mail to be sent from third-party applications.**

### Configuration Manager hybrid

1. Open the Configuration Manager console > **Assets and Compliance**.

2. Expand **Overview** > **Compliance Settings** > **Company Resource Access**, and select **Email Profiles**.

3. Right-click the e-mail profile, and open **Properties**.

4. On the **Synchronization Settings** tab, select **Allow e-mail to be sent from third-party applications**.

## Next steps

Get [support help from Microsoft](get-support.md), or use the [community forums](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
