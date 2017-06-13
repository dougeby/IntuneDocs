---
# required metadata

title: Configure device compliance and app management policies during an Intune migration 
description: The purpose of this article is to provide the necessary steps to configure device compliance and app management policies during an Intune migration.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Configure device compliance and app management policies

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

The main goal when migrating to Intune is to have all devices enrolled, and compliant with its policies. Device policies not only help you to manage corporate-owned single-user devices, but also personal (BYOD), and shared devices such as, kiosks, point-of-sales machines, tablets shared by multiple students in a classroom, or user-less devices (iOS only).

Each device platform may offer different settings, but Intune device policies work with each device platform by providing the following mobile device management capabilities:

-   Regulate numbers of devices each user enrolls.

-   Manage devices settings (e.g. device-level encryption, password length, camera usage).

-   Deliver apps, email profiles, VPN profiles, etc.

-   Evaluate device-level criteria for security compliance policies.

> [!IMPORTANT]
> Device management policies are not assigned directly to individual devices or users, but instead are assigned to user groups. The policies may be directly applied to a user group, and thereby to the user device, or the policies may be applied to a device group, and thereby to group members.

## Task list for device compliance policies

### Task 1: Add device groups (optional)

You can create device groups, when you need to perform a variety of administrative tasks based on device identity, instead of user identity.

Device groups are useful for managing devices without dedicated users, such as kiosk devices, or devices shared by shift workers or assigned to a specific location.

By configuring device groups ahead of device enrollment, you can leverage device categories to auto-group devices upon enrollment to receive their group’s device policies automatically. [Get started with groups](/intune/groups-get-started).

### Task 2: Use resource access profiles (Wi-Fi, VPN, and email certificates)

Resource access profiles provision certificates and access configurations to enrolled devices.

As previously discussed in the Assess MDM requirements section, if you are using certificate-based authentication, [configure certificates](/intune/certificates-configure).

### Task 3: Create and deploy device configuration profiles

You need to create a device configuration profile to enforce device-level settings, for example: disable camera, app-store, configure single-app mode, home screen, etc.

- Learn about [device profiles](/intune/device-profiles).

####  Direct import of iOS configuration profiles (optional)

-   **Apple Configurator iOS Profiles (iOS 7.1 and later):** If your existing MDM solution uses Apple Configurator profiles (.mobileconfig files), Intune can directly import them as custom configuration policies.

-   **iOS Mobile Application Configuration policies:** If your existing MDM solution uses iOS Mobile Application Configuration policies, Intune can directly import them as long as they meet the XML format specified by Apple for property lists.

- Learn how to add a custom policy for [iOS](/intune/custom-settings-ios)

### Task 4: Create and deploy device compliance policies (optional)

Device compliance policies evaluate security oriented settings, and provides reporting which shows whether the devices are compliant with corporate standards or not. Device compliance policies evaluate security oriented factors such as:

-   PIN length

-   Jail-broken status

-   OS Version

See additional resources for device compliance settings:

-   Learn about [device compliance policies](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

-   Learn [how to create a device compliance policy](/intune-classic/deploy-use/create-a-device-compliance-policy-in-microsoft-intune).

### Task 5: Publish and deploy Apps

When using Intune MDM, you can provision apps by either requiring their automatic installation, or making them available in the Company Portal.

-   Learn [how to add apps](/intune-classic/deploy-use/add-apps).

-   Learn [how to deploy apps](/intune-classic/deploy-use/deploy-apps).

### Task 6: Enable device enrollment

Enrollment establishes management by provisioning control on the device. Learn [how to get ready to enroll corporate-owned and user personal's devices](/intune/device-enrollment).

## Next steps 

[Configure App Protection Policies (optional)](migration-guide-app-protection-policies.md)
