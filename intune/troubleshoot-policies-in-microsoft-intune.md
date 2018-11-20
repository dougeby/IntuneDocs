---
# required metadata

title: Troubleshoot policies in Microsoft Intune - Azure | Microsoft Docs
description: Common problems or issues and resolutions when using policies in Microsoft Intune
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/14/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS:

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Troubleshoot policies in Intune

If you're having problems deploying and managing Intune policies, start here. This article describes some common problems you might experience, and possible solutions.

## General Issues

### Was a deployed policy applied to the device?
**Issue:** You're unsure if a policy is correctly applied.

In Intune > **Devices** > **All devices** > select the device > **Device configuration**, every device lists its policies. Each policy has a **Status**. The status is applied when all of the policies that apply to the device, including the restrictions and requirements of the hardware and the operating system, are considered together. Possible statuses are:

- **Conforms**: The device has received the policy and reports to the service that it conforms to the setting.

- **Not applicable**: The policy setting isn't applicable. For example, email settings for iOS devices would not apply to an Android device.

- **Pending**: The policy is sent to the device, but hasn't reported the status to the service. For example, encryption on Android requires the user to enable encryption, and might show as pending.

> [!NOTE]
> When two policies with different levels of restriction apply to the same device or user, the more restrictive policy applies.

## Issues with enrolled devices

### Alert: Saving of Access Rules to Exchange has Failed
**Issue**: You receive the alert **Saving of Access Rules to Exchange has Failed**  in the admin console.

If you  created policies in the Exchange On-Premises Policy workspace under the Admin Console but are using O365, then the configured policy settings aren't enforced by Intune. Note the policy source from the alert.  Under the Exchange On-premises Policy workspace delete the legacy rules. The legacy rules are Global Exchange rules within Intune for on-premises Exchange, and aren't relevant to O365. Then, create new policy for O365.

### Cannot change security policy for various enrolled devices
Windows Phone devices don't allow security policies set via MDM or EAS to be reduced in security once you've set them. For example, you set a **Minimum number of character password** to 8  then try to reduce it to 4. The more restrictive policy has already been applied to the device.

Depending on the device platform, if you want to change the policy  to a less secure value you may need to reset security policies.

For example, in Windows, on the desktop, swipe in from right to open the **Charms** bar. Choose **Settings** > **Control Panel**, and select **User Accounts**. On the left, select **Reset Security Policies** link, and choose **Reset Policies**.

Other MDM devices, such as Android, Windows Phone 8.1 and later, and iOS, may need to be retired and re-enrolled into the service to apply a less restrictive policy.

## Issues with PCs that run the Intune software client

Applies to the classic portal.

### Microsoft Intune policy-related errors in policyplatform.log
For Windows PCs managed with the Intune software client, policy errors in the policyplatform.log file may be the result of non-default settings in the Windows User Account Control (UAC) on the device. Some non-default UAC settings can affect Microsoft Intune client installations and policy execution.

#### Resolve UAC issues

1. Retire the computer. See [Remove devices](devices-wipe.md).

2. Wait 20 minutes for the client software to be removed.

    > [!NOTE]
    > Don't attempt to remove the client from Programs and Features.

3. On the start menu type **UAC** to open the User Account Control settings.

4. Move  the notification slider to the default setting.

### ERROR: Cannot obtain the value from the computer, 0x80041013
Occurs if the time on the local system is out of sync by five minutes or more. If the time on the local computer is out of sync, secure transactions will fail because the time stamps will be invalid.

To resolve this issue, set the local system time as close as possible to Internet time, or to the time set on the domain controllers on the network.

### Next steps
If this troubleshooting information didn't help, contact Microsoft Support as described in [get support for Microsoft Intune](get-support.md).
