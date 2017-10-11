---
# required metadata

title: Intune device compliance policiestitleSuffix: "Azure portal"
description: Use this topic to learn about device compliance in Microsoft Intune"
keywords:
author: andredm7ms.author: andredmmanager: angrobe
ms.date: 07/18/2017
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

-   When the device is first determined to be non-compliant, an email with noncompliant notification is sent to the user.

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

When a device is enrolled into Intune, the Azure AD registration process happens, which updates the device atributes with more information into Azure AD. One of the key device information is the device compliance status, which is used by conditional access policies to block or allow access to e-mail and other corporate resources.

- Learn more about [Azure AD registration process](https://docs.microsoft.com/azure/active-directory/active-directory-device-registration-overview).

##  Ways to use device compliance policies

### With conditional access
You can use compliance policy with conditional access to allow only devices that comply with one or more device compliance policy rules to access email and other corporate resources.

### Without conditional access
You can also use device compliance policies independently of conditional access. When you use compliance policies independently, the targeted devices are evaluated and reported with their compliance status. For example, you can get a report on how many devices are not encrypted, or which devices are jail-broken or rooted. But when you use compliance policies independently, no access restrictions to company resources are in place.

You deploy compliance policy to users. When a compliance policy is deployed to a user, the user's devices are checked for compliance. To learn about how long it takes for mobile devices to get a policy after the policy is deployed, see Manage settings and features on your devices.

##  Using device compliance policies in the Intune classic portal vs. Azure portal

Note the main differences to help you transition to the new device compliance policy work-flow in the Azure portal.

- In the Azure portal, the compliance policies are created separately for each supported platform.
- In the Intune classic portal, one device compliance policy was common to all supported platforms.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  Migrate device compliance policies from the Intune classic portal to the Azure portal

Device compliance policies created in the [Intune classic portal](https://manage.microsoft.com) will not appear in the new [Intune Azure portal](https://portal.azure.com). However, they’re still targeted to users and manageable via the Intune classic portal.

If you want to take advantage of the new device compliance related features in the Azure portal, you need to create new device compliance policies in the Azure portal itself. If you assign a new device compliance policy in the Azure portal to a user who also has been assigned with a device compliance policy from the Intune classic portal, the device compliance policies from the Intune Azure portal takes precedence over the ones created in the Intune classic portal.

##  Next steps

Create a device compliance policy for the following platforms:

- [Android](compliance-policy-create-android.md)
- [Android for work](compliance-policy-create-android-for-work.md)
- [iOS](compliance-policy-create-ios.md)
- [macOS](compliance-policy-create-mac-os.md)
- [Windows](compliance-policy-create-windows.md)
