---
# required metadata

title: Troubleshooting device profiles in Microsoft Intune 
titlesuffix: "Azure portal"
description: If you're stuck, use this topic to help you solve problems with Intune device profiles."
keywords:
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 1/17/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Troubleshooting device profiles in Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The information in this topic can be used to help you troubleshoot common issues around Intune device profiles.

## Why doesn't a user get a new profile when changing a password or passphrase on an existing Wi-Fi profile? 
When you create a corporate Wi-Fi profile, deploy the profile to a group, change the password, and save the profile, you might expect the user gets the new profile. However, the user might not get the new profile. 

To mitigate this issue, make sure you have a guest Wi-Fi set up such that the user falls back to the guest Wi-Fi if the corporate Wi-Fi fails. The automatically connect setting needs to be enabled. This guest Wi-Fi profile needs to be deployed to all users.

There are some additional best practices that you can follow:
- Since the Wi-Fi network you're connecting to takes a password or passphrase, make sure you can connect to the Wi-Fi router directly. You can test with an iOS device.
- After you successfully connect to the Wi-Fi endpoint (Wi-Fi router,) note the SSID and the credential used (this is the password or passphrase.)
- Enter the SSID and credential (password or passphrase) in the Pre-Shared Key field. 
- Deploy to a test group which has limited number of users, preferably only the IT team. 
- Sync your iOS device to Intune. Enroll if you haven’t already enrolled. 
- Test connecting to the same Wi-Fi endpoint (as mentioned in the first step) again.
- Roll out to larger groups and eventually to all expected users in your organization. 

## How long does it take for mobile devices to get a policy or apps after they have been assigned?
When a policy or an app is assigned, Intune immediately begins attempting to notify the device that it should check in with the Intune service. This typically takes less than five minutes.

If a device doesn't check in to get the policy after the first notification is sent, Intune makes three more attempts.  If the device is offline (for example, it is turned off or not connected to a network), it might not receive the notifications. In this case, the device will get the policy on its next scheduled check-in with the Intune service as follows:

- iOS and macOS: Every six hours.
- Android: Every eight hours.
- Windows Phone: Every eight hours.
- Windows 8.1 and Windows 10 PCs enrolled as devices: Every eight hours.

If the device has just enrolled, the check-in frequency will be more frequent, as follows:

- iOS and macOS: Every 15 minutes for 6 hours, and then every 6 hours.
- Android: Every 3 minutes for 15 minutes, then every 15 minutes for 2 hours, and then every 8 hours.
- Windows Phone: Every 5 minutes for 15 minutes, then every 15 minutes for 2 hours, and then every 8 hours.
- Windows PCs enrolled as devices: Every 3 minutes for 30 minutes, and then every 8 hours.

Users can also open the Company Portal app and sync the device to immediately check for the policy anytime.

For devices without user affinity, the sync frequency immediately following enrollment can vary from hours to a day or more. Intune sends requests at various intervals for a device to check-in with the service. However it is still up to the device to actually do so. After initial enrollment, depending on the type of device enrollment and the policies and profiles assigned to a device, how long it takes a device to complete that check-in cannot be predicted. However, once the device is enrolled and all initial policies have been applied, the device should check for new policies approximately every six hours.

## What actions cause Intune to immediately send a notification to a device?
Devices check in with Intune either when they receive a notification that tells them to check in or during their regularly scheduled check-in.  When you target a device or user specifically with an action such as a wipe, lock, passcode reset, app assignment, profile assignment (Wi-Fi, VPN, email, etc.), or policy assignment, Intune will immediately begin trying to notify the device that it should check in with the Intune service to receive these updates.

Other changes, such as revising the contact information in the company portal, do not cause an immediate notification to devices.

## If multiple policies are assigned to the same user or device, how do I know which settings will get applied?
When two or more policies are assigned to the same user or device, the evaluation for which setting is applied happens at the individual setting level:

-   Compliance policy settings always have precedence over configuration policy settings.

-   The most restrictive compliance policy setting is applied if it is evaluated against the same setting in a different compliance policy.

-   If a configuration policy setting conflicts with a setting in a different configuration policy, this conflict will be displayed in the Azure portal. You must manually resolve such conflicts.

## What happens when app protection policies conflict with each other? Which one will be applied to the app?
Conflict values are the most restrictive settings available in an app protection policy, except for the number entry fields (like PIN attempts before reset).  The number entry fields will be set the same as the values, as if you created a MAM policy in the console by using the recommended settings option.

Conflicts occur when two profile settings are the same.  For example, you configured two MAM policies that are identical except for the copy/paste setting.  In this scenario, the copy/paste setting will be set to the most restrictive value, but the rest of the settings will be applied as configured.

If one profile is assignedd to the app and takes effect, and then a second one is assigned, the first one will take precedence and stay applied, while the second shows in conflict. If they are both applied at the same time, meaning that there is no preceding profile, then they will both be in conflict. Any conflicting settings will be set to the most restrictive values.

## What happens when iOS custom policies conflict?
Intune does not evaluate the payload of Apple Configuration files or a custom Open Mobile Alliance Uniform Resource Identifier (OMA-URI) profile. It merely serves as the delivery mechanism.

When you assign a custom profile, ensure that the configured settings do not conflict with compliance, configuration, or other custom policies. In the case of a custom profile with settings conflicts, the order in which settings are applied is random.

## What happens when a profile is deleted or no longer applicable?
When you delete a profile, or you remove a device from a group to which a profile was assigned, the profile and settings will be removed from the device according to the following lists.

### Enrolled devices

- Wi-Fi, VPN, certificate, and email profiles: These profiles are removed from all supported enrolled devices.
- All other profile types:
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

## I changed a device restriction profile, but the changes haven't taken effect
Windows Phone devices do not allow security policies set via MDM or EAS to be reduced in security once you've set them. For example, you set a **Minimum number of character password** to 8  then try to reduce it to 4. The more restrictive profile has already been applied to the device.

Depending on the device platform, if you want to change the profile to a less secure value you may need to reset security policies.
For example, in Windows,  on the desktop swipe in from right to open the **Charms** bar and choose  **Settings** &gt; **Control Panel**.  Select the **User Accounts** applet.
In the left hand navigation menu, there is a **Reset Security Policies** link at the bottom. Choose it and then choose the **Reset Policies** button.
Other MDM devices, such as Android, Windows Phone 8.1 and later, and iOS, may need to be retired and re-enrolled back into the service for you to be able to apply a less restrictive profile.


### Next steps
If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](get-support.md).