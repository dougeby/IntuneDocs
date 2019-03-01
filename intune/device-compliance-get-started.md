---
# required metadata

title: Device compliance policies in Microsoft Intune - Azure | Microsoft Docs
description: Get started with use device compliance policies, overview of status and severity levels, using the InGracePeriod status, working with conditional access, handling devices without an assigned policy, and the differences in compliance in the Azure portal and classic portal in Microsoft Intune
keywords:

author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/28/2019

ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.reviewer: joglocke

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Set rules on devices to allow access to resources in your organization using Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Many mobile device management (MDM) solutions help protect organizational data by requiring users and devices to meet some requirements. In Intune, this feature is called "compliance policies". Compliance policies define the rules and settings that users and devices must meet to be compliant. When combined with conditional access, administrators can block users and devices that don't meet the rules. 

For example, an Intune administrator can require:

- End users use a password to access organizational data on mobile devices
- The device isn't jail-broken or rooted
- A minimum or maximum operating system version on the device
- The device to be at, or under a threat level

You can also use this feature to monitor the compliance status on devices in your organization.

> [!IMPORTANT]
> Intune follows the device check-in schedule for all compliance evaluations on the device. [Learn more about the device check-in schedule](https://docs.microsoft.com/intune/device-profile-troubleshoot#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be noncompliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

## Prerequisites

To use device compliance policies, be sure you:

- Use the following subscriptions:

  - Intune
  - Azure Active Directory (AD) Premium

- Use a supported platform:

  - Android
  - iOS
  - macOS (preview)
  - Windows 8.1
  - Windows Phone 8.1
  - Windows 10

- Enroll devices in Intune to see the compliance status

- Enroll devices to one user, or enroll without a primary user. Devices enrolled to multiple users aren't supported.

## How device compliance policies work with Azure AD

When a device is enrolled in Intune, the Azure AD registration process starts, and updates the device attributes into Azure AD. One key piece of information is the device compliance status. This compliance status is used by conditional access policies to block or allow access to e-mail and other corporate resources.

[Azure AD registration process](https://docs.microsoft.com/azure/active-directory/device-management-introduction) provides more information.

## Refresh cycle times

When checking for compliance, Intune uses the same refresh cycle as configuration profiles. In general, the times are:

| Platform | Refresh cycle|
| --- | --- |
| iOS | Every 6 hours |
| macOS | Every 6 hours |
| Android | Every 8 hours |
| Windows 10 PCs enrolled as devices | Every 8 hours |
| Windows Phone | Every 8 hours |
| Windows 8.1 | Every 8 hours |

If the device recently enrolled, the compliance check-in runs more frequently:

| Platform | Frequency |
| --- | --- |
| iOS | Every 15 minutes for 6 hours, and then every 6 hours |  
| Mac OS X | Every 15 minutes for 6 hours, and then every 6 hours | 
| Android | Every 3 minutes for 15 minutes, then every 15 minutes for 2 hours, and then every 8 hours | 
| Windows Phone | Every 5 minutes for 15 minutes, then every 15 minutes for 2 hours, and then every 8 hours | 
| Windows PCs enrolled as devices | Every 3 minutes for 30 minutes, and then every 8 hours | 

At anytime, users can open the Company Portal app, and sync the device to immediately check for a policy.

### Assign an InGracePeriod status

The InGracePeriod status for a compliance policy is a value. This value is determined by the combination of a device’s grace period, and a device’s actual status for that compliance policy.

Specifically, if a device has a NonCompliant status for an assigned compliance policy, and:

- the device has no grace period assigned to it, then the assigned value for the compliance policy is NonCompliant
- the device has a grace period that is expired, then the assigned value for the compliance policy is NonCompliant
- the device has a grace period that is in the future, then the assigned value for the compliance policy is InGracePeriod

The following table summarizes these points:

|Actual compliance status|Value of assigned grace period|Effective compliance status|
|---------|---------|---------|
|NonCompliant |No grace period assigned |NonCompliant |
|NonCompliant |Yesterday’s date|NonCompliant|
|NonCompliant |Tomorrow’s date|InGracePeriod|

For more information about monitoring device compliance policies, see [Monitor Intune Device compliance policies](compliance-policy-monitor.md).

### Assign a resulting compliance policy status

If a device has multiple compliance policies, and the device has different compliance statuses for two or more of the assigned compliance policies, then a single resulting compliance status is assigned. This assignment is based on a conceptual severity level assigned to each compliance status. Each compliance status has the following severity level:

|Status  |Severity  |
|---------|---------|
|Unknown     |1|
|NotApplicable     |2|
|Compliant|3|
|InGracePeriod|4|
|NonCompliant|5|
|Error|6|

When a device has multiple compliance policies, then the highest severity level of all the policies is assigned to that device.

For example, say a device has three compliance policies assigned to it: one Unknown status (severity = 1), one Compliant status (severity = 3), and one InGracePeriod status (severity = 4). The InGracePeriod status has the highest severity level, so all three policies have the InGracePeriod compliance status.

## Ways to use device compliance policies

#### With conditional access
For devices that comply to policy rules, you can give those devices access to email and other corporate resources. If the devices don't comply to policy rules, then they don't get access to corporate resources. This is conditional access.

#### Without conditional access
You can also use device compliance policies without any conditional access. When you use compliance policies independently, the targeted devices are evaluated and reported with their compliance status. For example, you can get a report on how many devices aren't encrypted, or which devices are jail-broken or rooted. When you use compliance policies without conditional access, there aren't any access restrictions to organization resources.

## Ways to deploy device compliance policies
You can deploy compliance policy to users in user groups or devices in device groups. When a compliance policy is deployed to a user, all of the user's devices are checked for compliance. On Windows 10 version 1803 and newer devices, it's recommended to deploy to device groups *if* the primary user didn't enroll the device. Using device groups in this scenario helps with compliance reporting.

A set of built-in compliance policy settings (**Intune** > **Device compliance**) gets evaluated on all Intune-enrolled devices. These include:

- **Mark devices with no compliance policy assigned as**: This property has two values:

  - **Compliant**: security feature off
  - **Not compliant** (default): security feature on

  If a device doesn't have a compliance policy assigned, then this device is considered not compliant. By default, devices are marked as **Not compliant**. If you use conditional access, we recommended you change the setting to **Not compliant**. If an end user isn't compliant because a policy isn't assigned, then Company Portal shows `No compliance policies have been assigned`.

- **Enhanced jailbreak detection**: When enabled, this setting causes iOS devices to check in with Intune more frequently. Enabling this property uses the device’s location services, and impacts battery usage. The user location data is not stored by Intune.

  Enabling this setting requires devices to:
  - Enable location services at the OS level
  - Allow the company portal to use location services
  - Evaluate and report its jailbreak status to Intune at least once every 72 hours. Otherwise, the device is marked not compliant. Evaluation is triggered by either opening the Company Portal app or physically moving the device 500 meters or more. If the device doesn't move 500 meters in 72 hours, the user needs to open the Company Portal app for enhanced jail break evaluation.

- **Compliance status validity period (days)**: Enter the time period that devices report the status for all received compliance policies. Devices that don't return the status within this time period are treated as noncompliant. The default value is 30 days.

All devices have a **Built-in Device Compliance Policy** (Azure portal > Device compliance > Policy compliance). Use this built-in policy to monitor these settings.

To learn the time it takes for mobile devices to get a policy after the policy is deployed, see [Troubleshooting device profiles](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

Compliance reports are a great way to check the status of devices. See [Monitor compliance policies](compliance-policy-monitor.md) for guidance.

### Actions for noncompliance
You can configure a time-ordered sequence of actions that apply to devices that don't meet the compliance policy criteria. These actions for noncompliance can be automated, as described in [Automate actions for noncompliance](actions-for-noncompliance.md).

## Azure classic portal vs. Azure portal

The main difference when using device compliance policies in the Azure portal:

- In the Azure portal, the compliance policies are created separately for each supported platform
- In the Azure classic portal, one device compliance policy is common to all supported platforms

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

## Device compliance policies in the classic portal and Azure portal

Device compliance policies created in the [classic portal](https://manage.microsoft.com) don't appear in the [Azure portal](https://portal.azure.com). However, they’re still targeted to users and manageable using the classic portal.

To use the device compliance-related features in the Azure portal, you must create new device compliance policies in the Azure portal. If you assign a device compliance policy in the Azure portal to a user who is also assigned a device compliance policy from the classic portal, then the device compliance policies from the Azure portal take precedence over the policies created in the classic portal.

## Next steps

- Create a device compliance policy for the following platforms:

  - [Android](compliance-policy-create-android.md)
  - [Android work profile](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- For information about the Intune Data Warehouse policy entities, see [Reference for policy entities](reports-ref-policy.md).
