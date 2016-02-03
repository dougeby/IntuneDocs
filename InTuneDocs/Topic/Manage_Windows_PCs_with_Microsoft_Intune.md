---
title: Manage Windows PCs with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
author: robstackmsft
---
# Manage Windows PCs with Microsoft Intune
In addition to managing mobile devices, you can also use [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] to manage computers running supported operating systems using the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] computer client software. The [hardware and software requirements](https://technet.microsoft.com/library/dn646975.aspx) to run the computer client are  minimal --basically any system capable of running Windows Vista or later is supported.  The client software can also be easily installed on either domain-joined computers (in any domain) or non-domain-joined computers.

[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] manages computers using policies similar to the way Windows Server Active Directory Domain Services (AD DS) Group Policy Objects (GPOs) do. If you will be managing Active Directory domain-joined computers with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], you should [be sure that Intune policies do not conflict with any GPOs](https://technet.microsoft.com/library/dn646986.aspx) that are in place for your organization.

> [!NOTE]
> Microsoft Intune as a standalone service offers these features for managing computers. Devices that run Windows 8.1 can be managed using the Intune client or they can be enrolled as mobile devices. The information below applies to computers that run the Intune client. For information about mobile device management capabilities, see [Mobile device management capabilities in Microsoft Intune](https://technet.microsoft.com/library/dn600287(TechNet.10).aspx).

## Install the Intune computer client
The first step in managing computers with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] is to install the client. The client software can be installed when a computer is enrolled into management by the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service in one of the following ways:

-   You can [manually deploy the Microsoft Intune client software](https://technet.microsoft.com/library/dn646969.aspx#BKMK_Manual). In this type of deployment, an administrator downloads the  Intune client software and manually installs it on each PC.

    To download the  Intune client software, open the  Intune administration console and, in the Client Software Download area, download the client software package. After the client software is installed,  Intune automatically installs additional software as necessary to manage the computer.

-   You can use the same files you download to manually install the  Intune client to [deploy the client to domain-joined computers using Active Directory GPOs](https://technet.microsoft.com/library/dn646969.aspx).

-   [End-users can self-enroll each of their computers](https://technet.microsoft.com/library/dn646969.aspx) through the  Intune Company Portal. Each enrolled computer is then automatically linked to the user account that was used to install the  Intune client software.

-   Finally, you can also deploy the  Intune client software to computers as part of an [operating system deployment](https://technet.microsoft.com/library/dn646969.aspx).

## Computer management with the Intune computer client
After the Intune client is installed, the client software enables several computer management capabilities including: [application management](https://technet.microsoft.com/library/dn646961.aspx), Endpoint Protection, hardware and software inventory, remote control (through remote assistance requests), software updates, and compliance settings reporting.

Several computer management tasks enabled by the computer client are managed using Intune policies such as:

-   Configuring the [Windows Firewall settings](https://technet.microsoft.com/library/mt346040.aspx) on managed computers.

-   Configuring [software update settings](https://technet.microsoft.com/library/dn646968.aspx) for managed computers to check for, and download, required software updates.

-   Helping to secure managed computers from potential threats and malicious software through [real-time monitoring and Endpoint Protection](https://technet.microsoft.com/library/dn646970.aspx) management.

In addition to the Intune client agent actions taken locally on individual computers, you can also use the Intune admin console to perform other [common computer management tasks](https://technet.microsoft.com/library/dn646989.aspx) on computers with the client installed to:

-   View hardware and software inventory information about managed computers

-   Remotely restart a computer

-   Retire a computer to uninstall the client software and remove it from management with Intune

-   Link users to specific managed computers

-   Respond to remote assistance requests

The Intune client agent usually runs quietly in the background without the need for much user interaction or troubleshooting. However, should you need help in resolving computer management issues, there are several [resources available to help you solve them](https://technet.microsoft.com/library/dn646987.aspx).

## See Also
[Configure and manage devices with Microsoft Intune](../Topic/Configure_and_manage_devices_with_Microsoft_Intune.md)

