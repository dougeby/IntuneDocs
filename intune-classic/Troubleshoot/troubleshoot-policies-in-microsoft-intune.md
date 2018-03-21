---
# required metadata

title: Troubleshoot policies 
description: Troubleshoot policy configuration issues.
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 01/04/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: tscott
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Troubleshoot policies in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

If you are having problems deploying and managing Intune policies, start here. This topic contains some common problems you might encounter together with solutions.

## General Issues

### Was a deployed policy applied to the device?
**Issue:** You are unsure if a policy was correctly applied.

In the Intune admin console every device has a policy tab under **Device Properties**. Each policy has an **Intended Value** and a **Status**. The intended value is what you meant to achieve when assigning the policy. The status is what is actually applied when all of the policies that apply to the device, as well as the restrictions and requirements of the hardware and the operating system, are considered together. Possible statuses are:

-   **Conforms**: the device has received the policy and reports to the service that it  conforms to the setting.

-   **Not applicable**: The policy setting is not applicable. For example,  email settings for iOS devices would not apply to an Android device.

-   **Pending**: The policy was sent to the device, but hasn't reported status to the service. For example, encryption on Android requires the user to enable encryption and might therefore be pending.

In the screenshot below you can see two clear examples:

-   **Allow simple passwords** is set to **Yes**, as shown in the **Intended Value** column, but its **Status** is **Not applicable**. This is because simple passwords are not supported for Android devices.

-   Similarly, the expanded policy item **Email settings for iOS devices** is not applied to this device, as it is an Android device.

![Intune device policy](../media/Intune-Device-Policy-v.2.jpg)

> [!NOTE]
> Remember that when two policies with different levels of restriction apply to the same device or user, the more restrictive policy applies in practice.


## Issues with enrolled devices

### Alert: Saving of Access Rules to Exchange has Failed
**Issue**: You receive the alert **Saving of Access Rules to Exchange has Failed**  in the admin console.

If you  created policies in the Exchange On-Premises Policy workspace under the Admin Console but are using O365, the configured policy settings are not enforced by Intune. Note the policy source from the alert.  Under the Exchange On-premises Policy workspace delete the legacy rules, as these are Global Exchange rules within Intune for on-premises Exchange, and are not relevant to O365. Then, create new policy for O365.

### Cannot change security policy for various enrolled devices
Windows Phone devices do not allow security policies set via MDM or EAS to be reduced in security once you've set them. For example, you set a **Minimum number of character password** to 8  then try to reduce it to 4. The more restrictive policy has already been applied to the device.

Depending on the device platform, if you want to change the policy  to a less secure value you may need to reset security policies.
For example, in Windows,  on the desktop swipe in from right to open the **Charms** bar and choose  **Settings** &gt; **Control Panel**.  Select the **User Accounts** applet.
In the left hand navigation menu, there is a **Reset Security Policies** link at the bottom. Choose it and then choose the **Reset Policies** button.
Other MDM devices, such as Android, Windows Phone 8.1 and later, and iOS, may need to be retired and re-enrolled back into the service for you to be able to apply a less restrictive policy.

## Issues with PCs that run the Intune software client

### Microsoft Intune policy-related errors in policyplatform.log
For Windows PCs managed with the Intune software client, policy errors in the policyplatform.log file may be the result of non-default settings in the Windows User Account Control (UAC) on the device. Some non-default UAC settings can affect Microsoft Intune client installations and policy execution.

#### To resolve UAC issues

1.  Retire the computer, as described in [Retire devices from Microsoft Intune management](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management).

2.  Wait 20 minutes for the client software to be removed.

    > [!NOTE]
    > Do not attempt to remove the client from Programs and Features.

3.  On the start menu type **UAC** to open the User Account Control settings.

4.  Move  the notification slider to the default setting.

### ERROR: Cannot obtain the value from the computer, 0x80041013
This can occur if the time on the local system is out of sync by five minutes or more. If the time on the local computer is out of sync, secure transactions will fail because the time stamps will be invalid.

To resolve this issue, set the local system time as close as possible to Internet time, or to the time set on the domain controllers on the network.








### Next steps
If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
