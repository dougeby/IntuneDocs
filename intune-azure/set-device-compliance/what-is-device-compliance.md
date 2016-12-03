---
# required metadata

title: Device compliance | Microsoft Docs
description: Use this topic to learn about device compliance in Microsoft Intune
keywords:
author: karthikaramanms.author: karaman
manager: angrobe
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
#ms.custom:

---

# What is device compliance in Microsoft Intune?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

To help protect company data, you need to make sure that the devices used to access company apps and data comply with certain rules. These rules might include using a PIN to access devices and encrypting data
stored on devices. A set of such rules is called a **compliance policy**.

##  How should I use a device compliance policy?


You can use compliance policy with conditional access to allow only devices that comply with compliance policy rules to access email and other services.

You can also use compliance policy independently of conditional access.
When you use compliance policies independently, the targeted devices are evaluated and reported with their compliance status. For example, you
can get a report on how many devices are not encrypted, or which devices are jailbroken or rooted. But when you use compliance policies independently, no access restrictions to company resources are in place.

You deploy compliance policy to users. When a compliance policy is deployed to a user, the user's devices are checked for compliance. To learn about how long it takes for mobile devices to get a policy after the policy is deployed, see Manage settings and features on your devices.

##  Concepts

Following are some terms and concepts that are useful to understanding how to use compliance policys.

### Compliance requirements

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

##  Differences between Intune admin console and the Azure portal


If you have been using the Intune admin console previously, note the following differences to help transition to the new device compliance workflow in the Azure portal:


-   In the Azure portal, the compliance policies are created separately for each supported platform. In the Intune Admin console, one compliance policy was common to all supported platforms.


<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  Next steps

[Get started on compliance policys](get-started-with-device-compliance.md)


### See also

Conditional access
