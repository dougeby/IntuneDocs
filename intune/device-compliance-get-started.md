---
# required metadata

title: Intune device compliance policies
titleSuffix: "Azure portal"
description: Use this topic to learn about device compliance in Microsoft Intune"
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 2/6/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Get started with Intune device compliance policies

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## What is device compliance in Intune?

Intune device compliance policies define the rules and settings that a device must comply with in order to be considered compliant by Intune.

These rules include the following:

- Use a password to access devices

- Encryption

- Whether the device is jail-broken or rooted

- Minimum OS version required

- Maximum OS version allowed

- Require the device to be at or under the Mobile Threat Defense level

You can also use device compliance policies to monitor the compliance status in your devices.

### Device compliance requirements

Compliance requirements are essentially rules like requiring a device PIN or encryption that you can specify as required or not required for a compliance policy.

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

##  Pre-requisites

You need to have the following subscriptions to use device compliance policies with Intune:

- Intune EMS

- Azure AD Premium

###  Supported Platforms:

-   Android

-   iOS

-   macOS (preview)

-   Windows 8.1

-   Windows Phone 8.1

-   Windows 10

> [!IMPORTANT]
> Devices must be enrolled into Intune to report their compliance statuses.

## How Intune device compliance policies work with Azure AD

When a device is enrolled into Intune, the Azure AD registration process happens, which updates the device attributes with more information into Azure AD. One key device information is the device compliance status, which is used by conditional access policies to block or allow access to e-mail and other corporate resources.

- Learn more about [Azure AD registration process](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction).

### Assigning a resulting device configuration profile status

If a device has multiple configuration profiles assigned to it, and the device has different compliance statuses for two or more of the assigned configuration profiles, then a single resulting compliance status must be assigned. This assignment is based on a conceptual severity level assigned to each compliance status. Each compliance status has the following severity level:


|Status  |Severity  |
|---------|---------|
|Pending     |1|
|Succeeded     |2|
|Failed     |3|
|Error     |4|

A resulting status of two or more configuration profiles is then assigned by selecting the highest severity level of all profiles assigned to a device.

For example, say a device has three profiles assigned to it: one Pending status (severity = 1), one Succeeded status (severity = 2), and one Error status (severity = 4). The Error status has the highest severity level, so it is assigned as the resulting compliance status for all three profiles.

### Assigning an InGracePeriod status for an assigned compliance policy

The InGracePeriod status for a compliance policy is a value determined by considering the combination of a device’s grace period and a device’s actual status for the assigned compliance policy. 

Specifically, if a device has a NonCompliant status for an assigned compliance policy, and:

- the device has no grace period assigned to it, then the assigned value for the compliance policy is NonCompliant.
- the device has a grace period that is expired, then the assigned value for the compliance policy is NonCompliant.
- the device has a grace period that is in the future, then the assigned value for the compliance policy is InGracePeriod.

The following table summarizes the previous points:


|Actual compliance status|Value of assigned grace period|Effective compliance status|
|---------|---------|---------|
|NonCompliant |No grace period assigned |NonCompliant |
|NonCompliant |Yesterday’s date|NonCompliant|
|NonCompliant |Tomorrow’s date|InGracePeriod|

For more information about monitoring device compliance policies, see [Monitor Intune Device compliance policies](compliance-policy-monitor.md).

### Assigning a resulting compliance policy status

If a device has multiple compliance policies assigned to it, and the device has different compliance statuses for two or more of the assigned compliance policies, then a single resulting compliance status must be assigned. This assignment is based on a conceptual severity level assigned to each compliance status. Each compliance status has the following severity level: 

|Status  |Severity  |
|---------|---------|
|Unknown     |1|
|NotApplicable     |2|
|Compliant|3|
|InGracePeriod|4|
|NonCompliant|5|
|Error|6|

A resulting status of two or more compliance policies is then determined by selecting the highest severity level of all policies assigned to a device.
 
For example, say a device has three compliance polices assigned to it: one Unknown status (severity = 1), one Compliant status (severity = 3), and one InGracePeriod status (severity = 4). The InGracePeriod status has the highest severity level, so it is assigned as the resulting compliance status for all three profiles.  

##  Ways to use device compliance policies

### With conditional access
You can use compliance policy with conditional access to allow only devices that comply with one or more device compliance policy rules to access email and other corporate resources.

### Without conditional access
You can also use device compliance policies independently of conditional access. When you use compliance policies independently, the targeted devices are evaluated and reported with their compliance status. For example, you can get a report on how many devices are not encrypted, or which devices are jail-broken or rooted. But when you use compliance policies independently, no access restrictions to company resources are in place.

You deploy compliance policy to users. When a compliance policy is deployed to a user, the user's devices are checked for compliance. To learn about how long it takes for mobile devices to get a policy after the policy is deployed, see Manage settings and features on your devices.

#### Actions for non-compliance

The actions for noncompliance allow you to configure a time-ordered sequence of actions that are applied to devices that don't meet the compliance policy criteria. For more information, see [Automate actions for noncompliance](actions-for-noncompliance.md).

##  Using device compliance policies in the Intune classic portal vs. Azure portal

Note the main differences to help you transition to the new device compliance policy work-flow in the Azure portal.

- In the Azure portal, the compliance policies are created separately for each supported platform.
- In the Intune classic portal, one device compliance policy was common to all supported platforms.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  Migrate device compliance policies from the Intune classic portal to the Azure portal

Device compliance policies created in the [Intune classic portal](https://manage.microsoft.com) do not appear in the new [Intune Azure portal](https://portal.azure.com). However, they’re still targeted to users and manageable via the Intune classic portal.

If you want to take advantage of the new device compliance-related features in the Azure portal, you need to create new device compliance policies in the Azure portal itself. If you assign a new device compliance policy in the Azure portal to a user who also has been assigned with a device compliance policy from the Intune classic portal, the device compliance policies from the Intune Azure portal takes precedence over the ones created in the Intune classic portal.

##  Next steps

- Create a device compliance policy for the following platforms:

   - [Android](compliance-policy-create-android.md)
   - [Android for work](compliance-policy-create-android-for-work.md)
   - [iOS](compliance-policy-create-ios.md)
   - [macOS](compliance-policy-create-mac-os.md)
   - [Windows](compliance-policy-create-windows.md)

- For information about the Intune Data Warehouse policy entities, see [Reference for policy entities](reports-ref-policy.md).
