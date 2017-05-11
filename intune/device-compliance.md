---
# required metadata

title: Device compliancetitleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Use this topic to learn about device compliance in Microsoft Intune"
keywords:
author: andredm7ms.author: andredmmanager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: muhosabe
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# What is device compliance in Intune Azure preview?

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Device compliance policies in Intune define the rules and settings that a device must comply with in order to be considered compliant by Intune and EMS conditional access polices. You can also use device compliance policies to monitor and remediate compliance issues with devices. 

These rules include the following:

- Use a password to access devices
- Encryption
- Whether the device is jail-broken or rooted
- Minimum OS version required
- Maximum OS version allowed
- Require the device to be at or under the Mobile Threat Defense level

<!---##  Concepts
Following are some terms and concepts that are useful to understanding how to use compliance policies.

### Device compliance requirements
Compliance requirements are essentially rules like requiring a device PIN or encryption that you can specify as required or not required for a compliance policy.

### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be non-compliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

##  How should I use a device compliance policy?

### Using EMS conditional access
You can use compliance policy with EMS conditional access to allow only devices that comply with one or more device compliance policy rules to access email and other corporate resources.

### Not using EMS conditional access
You can also use device compliance policies independently of EMS conditional access.
When you use compliance policies independently, the targeted devices are evaluated and reported with their compliance status. For example, you
can get a report on how many devices are not encrypted, or which devices are jail-broken or rooted. But when you use compliance policies independently, no access restrictions to company resources are in place.

You deploy compliance policy to users. When a compliance policy is deployed to a user, the user's devices are checked for compliance. To learn about how long it takes for mobile devices to get a policy after the policy is deployed, see Manage settings and features on your devices.

##  Intune classic admin console vs. Intune Azure preview portal

If you have been using the Intune classic admin console, note the following differences to help transition to the new device compliance policy work-flow in the Azure portal:

-   In the Azure portal, the compliance policies are created separately for each supported platform. In the Intune Admin console, one compliance policy was common to all supported platforms.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  Migration from Intune classic console to Intune Azure preview portal

Device compliance policies created in the [Intune classic console](https://manage.microsoft.com) will not appear in the new [Intune Azure portal](https://portal.azure.com). However, they’ll still be targeted to users and manageable via the Intune classic console.

If you want to take advantage of the new device compliance related features in the Intune Azure portal, you’ll need to create new device compliance policies in the Intune Azure portal itself. If you assign a new device compliance policy in the Intune Azure portal to a user who also has been assigned with a device compliance policy from the Intune classic portal, then the device compliance policies from the Intune Azure portal takes precedence over the ones created in the Intune classic console.

##  Next steps

[Get started on device compliance policies](device-compliance-get-started.md)


<!---### See also

Conditional access--->
