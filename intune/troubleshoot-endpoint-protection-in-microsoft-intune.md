---
# required metadata

title: Troubleshoot endpoint protection in Intune - Azure | Microsoft Docs
description: Solve problems while using Microsoft Intune endpoint protection.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/14/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e31df2d2-bb1b-491b-9a71-04e0b18829c1
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

# Troubleshoot Endpoint Protection in Intune

Use the information to help solve problems while using endpoint protection. You can also [review event logs and error codes to troubleshoot issues with Windows Defender AV](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

If this information doesn't help, you can also [get support for Microsoft Intune](get-support.md).

### Error messages
This section describes potential causes and solutions for the following errors and warnings.

|Status item|Potential causes|Potential solutions|
|---------------|--------------------|-----------------------|
|**Endpoint Protection engine unavailable**|The Intune endpoint protection engine was corrupted or deleted.|If the Intune endpoint protection engine is corrupted, you can try updating or reinstalling the software.<br /><br />To force an immediate update, choose **Update** in the  endpoint protection client software (found in the taskbar on managed computers.<br /><br />If the engine cannot be updated, you must reinstall the  endpoint protection engine.<br /><br />In the list of installed programs in Control Panel on the managed computer, locate **Microsoft Intune Endpoint Protection Agent**, and then uninstall the application.<br /><br />During the next update synchronization, the Microsoft Online Management Update Manager detects the missing program and reinstalls it at the scheduled installation time.|
|**Endpoint Protection disabled**|Intune endpoint protection was disabled by an administrator using a configuration profile, or by a user on a managed computer.|Enable endpoint protection. See [add endpoint protection settings](endpoint-protection-configure.md) in Intune, or [turn on Windows Defender to access company resources](/intune-user-help/turn-on-defender-windows).|
|**Real-time protection disabled**|Real-time protection was disabled by an administrator using a profile, or by a user on a managed computer.|Enable endpoint protection. See [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus) in Intune, or [turn on real-time protection to access company resources](/intune-user-help/turn-on-defender-windows). |
|**Download scanning disabled**|Download scanning was disabled by an administrator using profile, or by a user on a managed computer.|Enable scanning. See [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus) in Intune, or [turn on real-time protection to access company resources](/intune-user-help/turn-on-defender-windows). |
|**File and program activity monitoring disabled**|File and program activity monitoring was disabled by an administrator using a profile, or by a user on a managed computer.|Enable file and program activity. See [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus) in Intune, or [turn on real-time protection to access company resources](/intune-user-help/turn-on-defender-windows). |
|**Behavior monitoring disabled**|Behavior monitoring was disabled by an administrator using a profile, or by a user on a managed computer.|Enable behavior monitoring. See [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus) in Intune, or [turn on real-time protection to access company resources](/intune-user-help/turn-on-defender-windows). |
|**Script scanning disabled**|Script scanning was disabled by an administrator using a profile, or by a user on a managed computer.|Enable script scanning. See [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus) in Intune, or [turn on real-time protection to access company resources](/intune-user-help/turn-on-defender-windows). |
|**Network Inspection System disabled**|The Network Inspection System was disabled by an administrator using a profile, or by a user on a managed computer.|Enable Network Inspection System (NIS). See [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus) in Intune, or [turn on real-time protection to access company resources](/intune-user-help/turn-on-defender-windows). |
|**Malware definitions out of date**|The computer might have been disconnected from the Internet for an extended period of time, and its malware definitions might not yet have been updated. This status appears when the malware definitions on the computer are out of date by 14 days or more.|If malware definitions are out of date, you can update the definitions using [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus).|
|**Full scan overdue**|A full scan has not been completed for 14 days. This can be caused by a computer restart during a full scan.|If a full scan is overdue, you can run a one-time full scan or schedule recurring full scans. See [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus). |
|**Quick scan overdue**|A quick scan has not been completed for 14 days. This can be caused by a restart during a quick scan.|If a quick scan is overdue, you can run a one-time quick scan or schedule recurring quick scans. See [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus).|
|**Another endpoint protection application running**|Another endpoint protection application is running, and the computer is healthy.|By default, if another endpoint protection application is installed and Intune detects that application, the device may become unstable.|

### Next steps
If this information doesn't help, you can also [get support for Microsoft Intune](get-support.md).
