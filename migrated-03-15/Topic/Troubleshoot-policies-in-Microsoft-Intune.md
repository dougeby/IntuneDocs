---
title: Troubleshoot policies in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
author: Nbigman
---
# Troubleshoot policies in Microsoft Intune

## Policy issues
Listed here are some issues that may arise from your [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] policy configuration and troubleshooting recommendations for those issues.

### Is policy applied to device?
**Issue:** It's not clear if a particular policy is being applied to a device, or a device behaves contrary to a policy.

Check the policy information available for each device to understand how a policy affects a particular device.

In the Intune admin console every device has a policy tab under **Device Properties**. If not the device may still be in the process of enrolling or may not have policies applied. Each policy has an **Intended Value** and a **Status**. The intended value is what you meant to achieve when assigning the policy. The status is what is actually achieved when all of the policies that apply to the device, as well as the restrictions and requirements of the hardware and the operating system, are considered together. Possible statuses are:

-   **Conforms**: the device has received the policy and reports to the service that it  conforms to the setting.

-   **Not applicable**: The policy setting is not applicable. For example,  email settings for iOS devices would not apply to an Android device.

-   **Pending**: The policy was sent to the device, but hasn't reported status to the service. For example, encryption on Android, which requires end user to enable encryption, and may therefore be pending.

In the screenshot below you can see two clear examples:

-   **Allow simple passwords** is set to **Yes**, as shown in the **Intended Value** column, but its **Status** is **Not applicable**. This is because simple passwords are not supported for Android devices.

-   Similarly, the expanded policy item**Email settings for iOS devices** is not applied to this device, as it is an Android device.

![](../Image/Intune-Device-Policy-v.2.jpg)

> [!NOTE]
> Remember that when two policies with different levels of restriction apply to the same device or user, the more restrictive policy applies in practice.

### Policy refresh and update intervals
Be aware that policies are refreshed and updated on regular intervals. In general, policies should be registered on devices within 15 minutes of your making a change. Here are more details about regular intervals for policy refreshing:

-   **Windows device enrolled for MDM**: This is triggered by a scheduled task at 3:00am local time on the device and occurs every day.

-   **Windows Phone**: Policy is updated every 8 hours. This can be forced by a refresh in the Company Portal, under **Settings**.

-   **iOS**: Policy is updated once a day at a random time interval. This can also be forced by opening the Company Portal , selecting the device, and clicking **Sync**.

-   **Android**: Policy is updated once a day at a random time interval. This can also be forced by opening the Company Portal , selecting the device, and clicking **Sync**.

### Microsoft Intune policy-related errors in policyplatform.log
For non-MDM Windows devices, policy errors in the policyplatform.log file may be the result of non-default settings in the Windows User Account Control (UAC) on the device. Some non-default UAC settings can affect Microsoft Intune client installations and policy execution.

##### To resolve UAC issues

1.  Retire the computer, as described in [Retire data and devices from Microsoft Intune management](../Topic/Retire-data-and-devices-from-Microsoft-Intune-management.md).

2.  Wait 20 minutes for the client software to be removed.

    > [!NOTE]
    > Do not attempt to remove the client from Programs and Features.

3.  On the start menu type **UAC** to open the User Account Control settings.

4.  Move  the notification slider to the default setting.

### Error  0x87D1FDE8 for KNOX device
**Issue**:After creating and deploying an Exchange Active Sync email profile for Samsung KNOX for  various Android devices they report the error **0x87D1FDE8** or **remediation failed** in the device's properties &gt; policy tab.

Review the configuration of your EAS profile for Samsung KNOX and source policy. The Samsung Notes sync option is no longer supported and that option should not be selected in your profile. Be sure devices have had enough time to process the policy, up to 24 hours.

### Alert: Saving of Access Rules to Exchange has Failed
**Issue**: You receive the alert **Saving of Access Rules to Exchange has Failed**  in the admin console.

If you  created policies in the Exchange On-Premises Policy workspace under the Admin Console but are using O365, the configured policy settings are not are not enforced by Intune. Note the policy source from the alert.  Under the Exchange On-premises Policy workspace delete the legacy rules, as these are Global Exchange rules within Intune for on-premises Exchange, and are not relevant to O365. Then, create new policy for O365.

### ERROR: Cannot obtain the value from the computer, 0x80041013
This can occur if the time on the local system is out of sync by five minutes or more. If the time on the local computer is out of sync, secure transactions will fail because the time stamps will be invalid.

To resolve this issue, set the local system time as close as possible to Internet time, or to the time set on the domain controllers on the network.

## Cannot change security policy for various MDM devices
Windows Phone and Windows RT devices do not allow security policies set via MDM or EAS to be reduced in security once you've set them. For example, you set a **Minimum number of character password** to 8  then try to reduce it to 4. The more restrictive policy has already been applied to the device.

Depending on the device platform, if you want to change the policy  to a less secure value you may need to reset security policies. 
For example, in Windows RT,  on the desktop swipe in from right to open the **Charms** bar and click  **Settings** &gt; **Control Panel**.  Select the **User Accounts** applet. 
In the left hand navigation menu, there is a **Reset Security Policies** link at the bottom. Click  it and then click the **Reset Policies** button. 
Other MDM devices, such as Android, Windows Phone 8.1 and later, and iOS, may need to be retired and re-enrolled back into the service for you to be able to apply a  less restrictive policy.

## Android devices do not force Security Policy Changes without end user Acceptance
Android MDM does not allow the service to force initial policy changes on devices as other platforms allow. This is due to Android functionality, and is not related to the Intune service. Android devices will prompt the end user via the notification window of the related policy change (i.e. Password, Encryption, etc.).  The end user must respond to the prompt and once accepted the policy should be applied.

## See Also
[Troubleshoot software updates in Microsoft Intune](../Topic/Troubleshoot-software-updates-in-Microsoft-Intune.md)

