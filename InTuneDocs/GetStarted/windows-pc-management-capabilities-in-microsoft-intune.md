---
# required metadata

title: Windows PC management capabilities | Microsoft Intune
description: Learn about the capabilities of Intune when you manage Windows PCs with the Intune client software.
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 07/13/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: owenyen
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows PC management capabilities (with the Microsoft Intune PC client)
In most scenarios, you will enroll your devices with Microsoft Intune, which provides a greater set of capabilities than the Intune PC client. However, you can also manage PCs by using the Intune PC client which provides the following features:

-   **Manage software updates** - You can keep PCs up-to-date, and manage when updates are applied.

-   **Windows Firewall policy** - This helps to ensure that no PC used by your company has an inactive or improperly-configured Windows Firewall.

-   **Anti-malware protection** - Intune includes Endpoint Protection, which helps protect your PCs from malware.

-   **Remote assistance** - Intune lets users contact IT support staff, who can then provide assistance using a remote desktop feature that is included with Intune <!--- (requires TeamViewer software)--->.

-   **Software license management** - Track how many software licenses are available, and how many available licenses are being used.
-   **App deployment** - Deploy software to PCs that you manage. Some app management features are not available when you manage PCs with the client software.


Intune supports installing the PC client software on up to 7,000 Windows devices.

## Operating system requirements
Intune can manage PCs running the following Windows versions (both x86 and x64):


-   **Windows Vista** - Business, Enterprise and Ultimate versions.

-   **Windows 7** - Pro, Enterprise, and Ultimate versions (with no service pack, or with SP1).

-   **Windows 8** - Pro and Enterprise versions.

-   **Windows 8.1** - Pro and Enterprise versions.

- **Windows 10** - Home, Pro, Education, and Enterprise versions.


## Minimum hardware requirements
The following are minimum hardware requirements for installing the Intune PC client:

|Requirement|Details|
|---------------|--------------------|
|Network|The client requires the PC to have Internet connectivity.|
|Processor and Memory|Refer to the processor and RAM requirements for the PC's operating system.|
|Disk space|200 MB available disk space before the client software is installed.|

## Further requirements
The following are software requirements for installing the Intune PC client:

|Requirement|Details|
|---------------|--------------------|
|Administrative permissions|The account that installs the client software must have local administrator permissions to that PC.|
|Windows Installer 3.1|The PC must have, at a minimum, Windows Installer 3.1 installed.|
|Remove incompatible client software|Before you install the Intune PC client software, you must uninstall the following client software from that PC:<br /><br />-   Any version of Configuration Manager<br />-   Any version of Microsoft Systems Management Server (SMS)|

### See also
[Mobile device management capabilities in Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)
