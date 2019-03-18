---
# required metadata
title: Encryption report and BitLocker keys in Microsoft Intune | Microsoft Intune
description: View a report on your device encryption status, and access BitLocker recovery keys from within the Microsoft Intune portal.
keywords:
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid:  

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Monitor BitLocker and device encryption  
Intune provides a centralized location to identify the encryption status of your Windows 10 devices, and helps you access important information for BitLocker from your devices, as found in Azure Active Directory (Azure AD).  

- The [Encryption report](#encryption-report) provides details about a device’s encryption status and readiness. The report details can help you identify problems that prevent successful encryption of devices you want to protect.  
- [View BitLocker details](#bitlocker-recovery-keys) like the Key ID and recovery keys for your devices from within the Intune portal.  

## Encryption report
You can use the Encryption report (in Pubic Preview) to view details about the Encryption status of your Windows 10 devices.  

To find the report, Sign in to the [Intune](https://aka.ms/intuneportal) and go to **Device Configuration**, and then under *Monitor*, select **Encryption report (Preview)**.  

### Prerequisites:
To appear in the Encryption report, a device must:  
- Run Windows version 1607 or later  
- Have a Trusted Platform Module (TPM)  

### Report details
The report displays the **Device name** for your Windows 10 devices and high-level details about each, including:  
- **OS version** – Current version of Windows 10.  
- **TPM version** – The version of the Trusted Protection Module (TPM) chip on the device.  
- **Encryption readiness** – An evaluation of the devices readiness to support BitLocker encryption. A device could have an Encryption status of *Encrypted* even though its Encryption readiness is *Not ready*, because it lacks a TPM.  
- **Encryption status** – Whether the OS drive is encrypted.  


### Device encryption status
When you select a device that runs the *Windows 10 April 019 Update* or later, Intune displays the **Device encryption status** pane.  

This pane provides the following details:  
- **Device name** – The name of the device you're viewing.  
- **Encryption readiness** - An evaluation of the devices readiness to support BitLocker encryption. A device could have an Encryption status of *Encrypted* even though its Encryption readiness is *Not ready*, because it lacks a TPM.  
- **Encryption status** - Whether the OS drive is encrypted.  
- **Profiles** – A list of the *Device configuration* profiles that apply to this device and include the following Profile type and settings:  
    - Profile type = *Endpoint protection*  
    - Settings > Windows Encryption > Encrypt devices = *Required*  

  This list can be of use in locating individual policies for review should the Profile state summary indicate problems.  

- **Profile state summary** – A summary of the profiles that apply to this device. The summary represents the least favorable condition across all applicable profiles. For example, if one profile results in an Error, the Profile state summary will display *Error*.  
- **Status details** – Advanced details about the device’s encryption state. This field displays information for each applicable error that can be detected. You can use this information to understand why a device might not be encryption ready.  

   The following are examples of the status details Intune can report:  

   - The BitLocker policy requires user consent to launch the BitLocker Drive Encryption Wizard to start encryption of the OS volume but the user didn't consent.  
   - The encryption method of the OS volume doesn't match the BitLocker policy.  
   - The policy BitLocker requires a TPM protector to protect the OS volume, but a TPM isn't used.  
   - The BitLocker policy requires a TPM-only protector for the OS volume, but TPM protection isn't used.  
   - The BitLocker policy requires TPM+PIN protection for the OS volume, but a TPM+PIN protector isn't used.  
   - The BitLocker policy requires TPM+startup key protection for the OS volume, but a TPM+startup key protector isn't used.  
   - The BitLocker policy requires TPM+PIN+startup key protection for the OS volume, but a TPM+PIN+startup key protector isn't used.  
   - The OS volume is unprotected.  
   - Recovery key backup failed.  
   - A fixed drive is unprotected.  
   - The encryption method of the fixed drive doesn't match the BitLocker policy.  
   - To encrypt drives, the BitLocker policy requires either the user to sign in as an Administrator or, if the device is joined to Azure AD, the AllowStandardUserEncryption policy must be set to 1.  
   - Windows Recovery Environment (WinRE) isn't configured.  
   - A TPM isn't available for BitLocker, either because it isn't present, it has been made unavailable in the Registry, or the OS is on a removeable  drive.  
   - The TPM isn't ready for BitLocker.  
   - The network isn't available, which is required for recovery key backup.  


## BitLocker recovery keys
As a Public Preview, Intune provides access the Azure AD blade for BitLocker so you can view BitLocker Key IDs and recovery keys for your Windows 10 devices, from within the Intune portal.  To be accessible, the device must have its keys escrowed to Azure AD. 
1. Sign in to [Intune](https://aka.ms/intuneportal), go to **Devices** and then under *Manage*, select **All devices**.
2. Select a device from the list, and then under *Monitor*, select **Recovery keys – Preview**.  
  
When keys are available in Azure AD, the following information is available:
- BitLocker Key ID
- BitLocker Recovery Key
- Drive Type  

When keys aren't in Azure AD, Intune will display *No BitLocker key found for this device*.  

Information for BitLocker is obtained using the [BitLocker configuration service provider](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) (CSP). BitLocker CSP is supported on Windows 10 version 1703 and later, and for Windows 10 Pro version 1809 and later. 

### Next steps
Create a [device compliance](compliance-policy-create-windows.md#windows-10-and-later-policy-settings) policy for Windows 10 devices to configure BitLocker and encryption.
