---
# required metadata

title: Prepare Intune for mobile device management 
description: The purpose of this article is to help the readers evaluate their business and technical requirements before migrating to Intune.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 58591442-6606-4f39-a06b-f17a1f25af25

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Phase 1: Prepare Intune for mobile device management (MDM)

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Before diving into the details of setting up Intune, let’s review the mobile device management requirements of your organization. It might be helpful to run reports of active users in your current MDM provider to identify the critical user groups, then you can begin addressing the questions under the [Assess MDM requirements section](migration-guide-prepare.md#assess-mdm-requirements).

## Assess MDM requirements

### What kinds of devices do you need to manage?

-   Which [platforms](/intune-classic/get-started/supported-mobile-devices-and-computers) do you need to support?

-   Are the devices you need to support corporate or BYOD?

-   What kind of connectivity is used? Wi-Fi, cellular, VPN?

### What do your users need to do on managed devices?

-   Do you need to provision apps to your end-users?

-   Do you use custom line-of-business apps? Or do you only need public store apps?

-   Do you need to provision email accounts?

### What kinds of users?

-   How many users will use a single device?

-   What Terms of Use do you need?

    -   Make sure to involve your legal department early in this.

    -   What localization is required?

-   Are the users familiar with technology and IT in general?

### What is your device security policy?

-   Do you need device-level encryption?

-   Device passcode/pin code lengths?

-   Do you need to disable device features, or restrict certain device behaviors?

    -   You can control a variety of platform-specific settings with device configuration profiles, for example: Disable camera, Lock to single-app mode.
<br></br>
-   What kinds of authentication must you support?

    -   If you need cert-based authentication, what kinds of certificates must be provisioned?

        -   Intune can provision certificates with resource access profiles for enrolled devices.
<br></br>
    -   What kind of Public Key Infrastructure (PKI) infra do you need to support?
<br></br>
-   Do you need to support Virtual Private Network (VPN) at the device or app level?

    -   Intune can provision VPN configurations for third-party VPN providers.
<br></br>
-   Can temporary exceptions be made for certain requirements to avoid down time? Or must devices with access always comply with all security requirements?

## Additional information

-   For more detailed examples, review these [case studies](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune) from different industry sectors to see how organizations assessed their requirements for mobile device management.

## Next steps

[Basic Setup](migration-guide-setup.md)
