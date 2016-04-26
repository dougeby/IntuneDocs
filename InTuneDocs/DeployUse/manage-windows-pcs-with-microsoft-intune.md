---
# required metadata

title: Manage Windows PCs with Intune | Microsoft Intune
description:
keywords:
author: nathbarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Manage Windows PCs with Microsoft Intune
In addition to enrolling devices, you can also use Intune to manage Windows PCs running supported operating systems using the Intune Windows PC client software. The hardware and software requirements to run the computer client are minimal -- basically any system capable of running Windows 7 or later is supported.  The client software can also be easily installed on either domain-joined computers (in any domain) or non-domain-joined computers.

Intune manages Windows PCs using policies similar to the way Windows Server Active Directory Domain Services (AD DS) Group Policy Objects (GPOs) do. If you will be managing Active Directory domain-joined computers with Intune, you should [be sure that Intune policies do not conflict with any GPOs](resolve-gpo-and-microsoft-intune-policy-conflicts.md) that are in place for your organization.

> [!NOTE]
> Microsoft Intune as a standalone service offers these features for managing computers. Devices that run Windows 8.1 can be managed using the Intune client or they can be enrolled as mobile devices. The information below applies to computers that run the Intune client.

## Requirements for Intune PC management

**Hardware**:
The following are minimum hardware requirements for installing the Intune client:

|Requirement|More information|
|---------------|--------------------|
|Network|The client requires the PC to have Internet connectivity.|
|Processor and Memory|Refer to the processor and RAM requirements for the PC's operating system.|
|Disk space|200 MB available disk space before the client software is installed.|

**Software**:
The following are software requirements for installing the client:

|Requirement|More information|
|---------------|--------------------|
|Administrative permissions|The account that installs the client software must have local administrator permissions to that PC.|
|Windows Installer 3.1|The PC must have, at a minimum, Windows Installer 3.1.<br /><br />To view the version of Windows Installer on a PC:<br /><br />-   On the PC, right-click **%windir%\System32\msiexec.exe**, and then click **Properties**.<br /><br />You can download the latest version of Windows Installer from [Windows Installer Redistributables](http://go.microsoft.com/fwlink/?LinkID=234258) on the Microsoft Developer Network website.|
|Remove incompatible client software|Before you install the Intune client software, you must uninstall the any Configuration Manager or System Management Server client software from that PC.|

## Install the Intune computer client
The first step in managing Windows PCs with Intune is to install the client. The client software can be installed when a PC is enrolled into management by the Intune service in one of the following ways:

-   You can [manually deploy the Microsoft Intune client software](install-the-windows-pc-client-with-microsoft-intune.md#to-manually-deploy-the-client-software). In this type of deployment, an administrator downloads the  Intune client software and manually installs it on each PC.

    To download the  Intune client software, open the  Intune administration console and, in the Client Software Download area, download the client software package. After the client software is installed,  Intune automatically installs additional software as necessary to manage the computer.

-   You can use the same files you download to manually install the  Intune client to [deploy the client to domain-joined computers using Active Directory GPOs](install-the-windows-pc-client-with-microsoft-intune.md#to-automatically-deploy-the-client-software-by-using-group-policy).

-   [End-users can self-enroll each of their computers](install-the-windows-pc-client-with-microsoft-intune.md#how-users-can-self-enroll-their-computers) through the  Intune Company Portal. Each enrolled computer is then automatically linked to the user account that was used to install the  Intune client software.

-   Finally, you can also deploy the  Intune client software to computers as part of an [operating system deployment](install-the-windows-pc-client-with-microsoft-intune.md#install-the-microsoft-intune-client-software-as-part-of-an-image).

## Computer management with the Intune computer client
After the Intune client is installed, the client software enables several computer management capabilities including: [application management](deploy-apps-in-microsoft-intune.md), Endpoint Protection, hardware and software inventory, remote control (through remote assistance requests), software updates, and compliance settings reporting.

Several computer management tasks enabled by the computer client are managed using Intune policies such as:

-   Configuring the [Windows Firewall settings](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) on managed computers.

-   Configuring [software update settings](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) for managed computers to check for, and download, required software updates.

-   Helping to secure managed computers from potential threats and malicious software through [real-time monitoring and Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) management.

In addition to the Intune client agent actions taken locally on individual computers, you can also use the Intune admin console to perform other [common computer management tasks](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) on Windows PCs with the client installed to:

-   View hardware and software inventory information about managed computers

-   Remotely restart a computer

-   Retire a computer to uninstall the client software and remove it from management with Intune

-   Link users to specific managed computers

-   Respond to remote assistance requests

The Intune client agent usually runs quietly in the background without the need for much user interaction or troubleshooting. However, should you need help in resolving computer management issues, there are several [resources available to help you solve them](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune.md).
