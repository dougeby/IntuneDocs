---
# required metadata

title: Troubleshoot Endpoint Protection 
description: Solve problems while using Microsoft Intune endpoint protection.
keywords:
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 01/31/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e31df2d2-bb1b-491b-9a71-04e0b18829c1
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: tscott
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Troubleshoot Endpoint Protection in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use the information in this section to help you solve problems while using Microsoft Intune endpoint protection. You can also review information about [troubleshooting Windows Defender](https://technet.microsoft.com/itpro/windows/keep-secure/troubleshoot-windows-defender-in-windows-10).

If this information does not solve your problem, see [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) to find more ways to get help.

### Endpoint Protection error messages
This section describes potential causes and solutions for the following errors and warnings, which appear in the **Endpoint Protection Status** pane in the  [Intune admin console](https://manage.microsoft.com).

|Status item|Potential causes|Potential solutions|
|---------------|--------------------|-----------------------|
|**Endpoint Protection engine unavailable**|The Intune endpoint protection engine was corrupted or deleted.|If the Intune endpoint protection engine is corrupted, you can try updating or reinstalling the software.<br /><br />To force an immediate update, choose **Update** in the  endpoint protection client software (found in the taskbar on managed computers.<br /><br />If the engine cannot be updated, you must reinstall the  endpoint protection engine.<br /><br />In the list of installed programs in Control Panel on the managed computer, locate **Microsoft Intune Endpoint Protection Agent**, and then uninstall the application.<br /><br />During the next update synchronization, the Microsoft Online Management Update Manager detects the missing program and reinstalls it at the scheduled installation time.|
|**Endpoint Protection disabled**|Intune endpoint protection was disabled by an administrator using a policy or by a user on a managed computer.|If  endpoint protection is disabled, you can enable it from the  [Intune admin console](https://manage.microsoft.com) or from a managed computer. Do one of the following:<br /><br />To enable  endpoint protection from the  [Intune admin console](https://manage.microsoft.com), open the **Policy** workspace, and then change the **Enable Endpoint Protection** setting in the policies that apply to the computer.<br /><br />Or,<br /><br />to enable  endpoint protection from a managed computer, start the Intune endpoint protection client from the notification area and you will be prompted to enable  endpoint protection.|
|**Real-time protection disabled**|Real-time protection was disabled by an administrator (using a policy) or by a user on a managed computer.|If real-time protection is disabled, you can enable it from the  [Intune admin console](https://manage.microsoft.com) or from a managed computer. Do one of the following:<br /><br />To enable real-time protection from the  [Intune admin console](https://manage.microsoft.com), open the **Policy** workspace, and then change the **Enable real-time protection** setting to **Yes** in the policies that apply to the computer.<br /><br />Or,<br /><br />to enable real-time protection from a managed computer, start the  endpoint protection client software from the notification area. You are prompted to enable real-time protection at that time.|
|**Download scanning disabled**|Download scanning was disabled by an administrator by using policy or by a user on a managed computer.|If download scanning is disabled, you can enable it from the  [Intune admin console](https://manage.microsoft.com) or from a managed computer. Do one of the following:<br /><br />To enable download scanning from the  [Intune admin console](https://manage.microsoft.com), open the **Policy** workspace, and then change the **Scan all Downloads** setting to **Yes** in the policies that apply to the computer.<br /><br />Or,<br /><br />to enable download scanning from a managed computer, start the  endpoint protection client software from the notification area. Choose the **Settings** tab, choose **Real-time protection**, select the **Scan all downloads** check box, and then choose **Save changes**.|
|**File and program activity monitoring disabled**|File and program activity monitoring was disabled by an administrator who used Policy or by a user on a managed computer.|If file and program activity monitoring is disabled, you can enable it from the  [Intune admin console](https://manage.microsoft.com) or from a managed computer. Do one of the following:<br /><br />To enable file and program activity monitoring from the  [Intune admin console](https://manage.microsoft.com), open the **Policy** workspace, and then change the **Monitor file and program activity on computers** setting to **Yes** in the policies that apply to the computer.<br /><br />Or,<br /><br />to enable file and program activity monitoring from a managed computer, start the  endpoint protection client software from the notification area. Choose the **Settings** tab, choose **Real-time protection**, select the **Monitor file and program activity on your computer** check box, and then choose **Save changes**.|
|**Behavior monitoring disabled**|Behavior monitoring was disabled by an administrator (using a policy) or by a user on a managed computer.|If behavior monitoring is disabled, you can enable it from the  [Intune admin console](https://manage.microsoft.com) or from a managed computer. Do one of the following:<br /><br />To enable behavior monitoring from the  [Intune admin console](https://manage.microsoft.com), open the **Policy** workspace, change the **Enable behavior monitoring** setting to **Yes** in the policies that apply to the computer, and then restart the managed computer.<br /><br />Or,<br /><br />to enable behavior monitoring from a managed computer, start the  endpoint protection client software from the notification area. Choose the **Settings** tab, choose **Real-time protection**, select the **Enable behavior monitoring** check box, and then choose **Save changes**. Then, restart the computer.|
|**Script scanning disabled**|Script scanning was disabled by an administrator (using a policy) or by a user on a managed computer.|If script scanning is disabled, you can enable it from the  [Intune admin console](https://manage.microsoft.com) or from a managed computer. Do one of the following:<br /><br />To enable script scanning from the  [Intune admin console](https://manage.microsoft.com), open the **Policy** workspace and change the **Enable script scanning** setting to **Yes** in the policies that apply to the computer.<br /><br />Or,<br /><br />to enable script scanning from a managed computer, start the  endpoint protection client software from the notification area. Choose the **Settings** tab, choose **Real-time protection**, select the **Enable script scanning** check box, and then choose **Save changes**.|
|**Network Inspection System disabled**|The Network Inspection System was disabled by an administrator using policy or by a user on a managed computer.|If Network Inspection System is disabled, you can enable it from the  [Intune admin console](https://manage.microsoft.com) or from a managed computer. Do one of the following:<br /><br />To enable Network Inspection System from the  [Intune admin console](https://manage.microsoft.com), open the **Policy** workspace, change the **Enable Network Inspection System** setting to **Yes** in the policies that apply to the computer, and then restart the managed computer.<br /><br />Or,<br /><br />to enable Network Inspection System from a managed computer, start the  endpoint protection client software from the notification area. Choose the **Settings** tab, choose **Real-time protection**, select the **Enable Network Inspection System** check box, and then choose **Save changes**. Restart the computer.|
|**Malware definitions out of date**|The computer might have been disconnected from the Internet for an extended period of time, and its malware definitions might not yet have been updated. This status appears when the malware definitions on the computer are out of date by 14 days or more.|If malware definitions are out of date, you can update the definitions from the  [Intune admin console](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune) topic.|
|**Full scan overdue**|A full scan has not been completed for 14 days. This can be caused by a computer restart during a full scan.|If a full scan is overdue, you can run a one-time full scan or schedule recurring full scans from the  [Intune admin console](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).|
|**Quick scan overdue**|A quick scan has not been completed for 14 days. This can be caused by a restart during a quick scan.|If a quick scan is overdue, you can run a one-time quick scan or schedule recurring quick scans from the  [Intune admin console](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).|
|**Another endpoint protection application running**|Another endpoint protection application is running, and the computer is healthy.|By default, if another endpoint protection application is installed and Intune detects that application,  endpoint protection automatically disables itself. If Intune does not detect the other endpoint application,  endpoint protection will remain enabled. For more information, see [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).|

### Next steps
If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
