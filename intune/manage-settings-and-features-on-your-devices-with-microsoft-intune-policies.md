---
# required metadata

title: Device policies, profiles, and Q&A with Intune - Azure | Microsoft Docs
description: Read about the different policies and profiles you can use in Microsoft Intune, including policies to configure devices, get access to company resources, enable conditional access, and enroll corporate devices. Also get answers to commonly-asked qeustions.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/14/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2
ROBOTS: 

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---

# Manage settings and features on your devices with Intune policies

Microsoft Intune *policies* are groups of settings that control features on mobile devices and computers. You create policies by using templates that contain recommended or custom settings, and then you deploy them to device or user groups.

## Types of policies

Intune policies fall into the following categories. The category that you use affects how you create and deploy the policy.

- **Configuration policies**: These are commonly used to manage security settings and features on your devices, including access to company resources. Get started at [Intune device profiles](device-profiles.md).
- **Device compliance policies**: These define the rules and settings that a device must comply to be considered compliant by conditional access polices. You can also use compliance policies to monitor and remediate  the compliance of devices independent of conditional access. Get started with [device compliance policies](device-compliance-get-started.md).
- **Conditional access polices**: These policies help you secure email and other services, depending on conditions that you enter. [What is conditional access](conditional-access.md) and [common ways to use conditional access](conditional-access-intune-common-ways-use.md) are good resources to get started.
- **Corporate device enrollment policies**: For information about corporate device enrollment policies, see [enroll iOS devices](ios-enroll.md).

## Frequently asked questions about Intune policies

### How long does it take for mobile devices to get a policy or apps after they have been deployed?
When a policy or an app is deployed, Intune immediately begins attempting to notify the device that it should check in with the Intune service. This typically takes less than five minutes.

If a device doesn't check in to get the policy after the first notification is sent, Intune makes three more attempts.  If the device is offline (for example, it is turned off or not connected to a network), it might not receive the notifications. In this case, the device gets the policy on its next scheduled check-in with the Intune service, as follows:

| Platform | Check-in frequency |
| --- | --- |
| iOS | Every 6 hours | 
| Mac OS X | Every 6 hours |
| Android | Every 8 hours | 
| Windows Phone | Every 8 hours | 
| Windows 8.1  | Every 8 hours |  
| Windows 10 PCs enrolled as devices | Every 8 hours | 

If the device has just enrolled, the check-in frequency is more frequent, as follows:

| Platform | Frequency |
| --- | --- |
| iOS | Every 15 minutes for 6 hours, and then every 6 hours |  
| Mac OS X | Every 15 minutes for 6 hours, and then every 6 hours | 
| Android | Every 3 minutes for 15 minutes, then every 15 minutes for 2 hours, and then every 8 hours | 
| Windows Phone | Every 5 minutes for 15 minutes, then every 15 minutes for 2 hours, and then every 8 hours | 
| Windows PCs enrolled as devices | Every 3 minutes for 30 minutes, and then every 8 hours | 

Users can also open the Company Portal app and sync the device to immediately check for the policy anytime.

### What actions cause Intune to immediately send a notification to a device?
Devices check in with Intune when they receive a notification that tells them to check in, or during their regularly scheduled check-in.  When you target a device or user specifically with an action such as a wipe, lock, passcode reset, app deployment, profile deployment (Wi-Fi, VPN, email, etc.), or policy deployment, Intune immediately begins trying to notify the device that it should check in with the Intune service to receive these updates.

Other changes, such as revising the contact information in the company portal, do not cause an immediate notification to devices.

### If multiple policies are deployed to the same user or device, how do I know which settings is applied?
When two or more policies are deployed to the same user or device, the evaluation for which setting is applied occurs at the individual setting level:

- Compliance policy settings always have precedence over configuration policy settings.

- The most restrictive compliance policy setting is applied if it is evaluated against the same setting in a different compliance policy.

- If a configuration policy setting conflicts with a setting in a different configuration policy, this conflict is shown in Intune. You must manually resolve these conflicts.

### What happens when mobile application management policies conflict with each other? Which one is applied to the app?
Conflict values are the most restrictive settings available in a MAM policy, except for the number entry fields (like PIN attempts before reset).  The number entry fields are set the same as the values, as if you created a MAM policy in the console by using the recommended settings option.

Conflicts occur when two policy settings are the same.  For example, you configured two MAM policies that are identical except for the copy/paste setting.  In this scenario, the copy/paste setting is set to the most restrictive value, but the rest of the settings are applied as configured.

If one policy is deployed to the app and takes effect, and then a second one is deployed, the first app takes precedence and stays applied. The second policy shows in conflict. If they are both applied at the same time, meaning that there is no preceding policy, then they both are in conflict. Any conflicting settings are set to the most restrictive values.

### What happens when iOS custom policies conflict?
Intune does not evaluate the payload of Apple Configuration files or a custom Open Mobile Alliance Uniform Resource Identifier (OMA-URI) policy. It merely serves as the delivery mechanism.

When you deploy a custom policy, ensure that the configured settings do not conflict with compliance, configuration, or other custom policies. In the case of a custom policy with settings conflicts, the order in which settings are applied is random.

### What happens when a policy is deleted or no longer applicable?
When you delete a policy, or you remove a device from a group that has a deployed policy, then the policy and settings are removed from the device according to the following lists.

#### Enrolled devices

- Wi-Fi, VPN, certificate, and email profiles: These profiles are removed from all supported enrolled devices.
- All other policy types:
  - **Windows and Android devices**: Settings are not removed from the device.
  - **Windows Phone 8.1 devices**: The following settings are removed:
    - Require a password to unlock mobile devices
    - Allow simple passwords
    - Minimum password length
    - Required password type
    - Password expiration (days)
    - Remember password history
    - Number of repeated sign-in failures to allow before the device is wiped
    - Minutes of inactivity before password is required
    - Required password type – minimum number of character sets
    - Allow camera
    - Require encryption on mobile device
    - Allow removable storage
    - Allow web browser
    - Allow application store
    - Allow screen capture
    - Allow geolocation
    - Allow Microsoft account
    - Allow copy and paste
    - Allow Wi-Fi tethering
    - Allow automatic connection to free Wi-Fi hotspots
    - Allow Wi-Fi hotspot reporting
    - Allow factory reset
    - Allow Bluetooth
    - Allow NFC
    - Allow Wi-Fi

  - **iOS**: All settings are removed, except:
    - Allow voice roaming
    - Allow data roaming
    - Allow automatic synchronization while roaming

### Where can I find help troubleshooting policies?

See [Troubleshoot policies](troubleshoot-policies-in-microsoft-intune.md).
