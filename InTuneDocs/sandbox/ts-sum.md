---
title: Software Update Management Troubleshooting in Configuration Manager
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: tempfile
author: jeffgilb
---
# Software Update Management Troubleshooting in Configuration Manager

## About this troubleshooting guide
This is a proof of concept for publishing troubleshooting guides using GitHub for docs.microsoft.com. It is based on this content: [Software Update Management Troubleshooting in Configuration Manager](https://support.microsoft.com/en-us/help/10680/software-update-management-troubleshooting-in-configuration-manager).

### What does this guide do
This guide helps you troubleshoot the software update management process in Microsoft System Center Configuration Manager, including client software update scanning, synchronization issues and detection problems with specific updates.

The information in this guide applies to System Center 2012 Configuration Manager (ConfigMgr 2012), System Center 2012 R2 Configuration Manager (ConfigMgr 2012 R2) and all versions of Configuration Manager in the current branch (e.g. Configuration Manager 1511 and Configuration Manager 1602).

### Who is it for?
This guide is for IT professionals who need to understand, diagnose and troubleshoot the Software Update Management process in Microsoft System Center Configuration Manager.

### How does it work?
 It is divided into three main sections:
- Client Software Update Scanning
- WSUS to Microsoft Update synchronization
- Installation, supersedence, or detection issues with specific updates

This guide assumes that a Software Update Point has already been installed and configured. For more information on configuring Software Updates in Configuration Manager, see [Configuring Software Updates in Configuration Manager](https://technet.microsoft.com/en-us/library/gg712312.aspx).

#### Estimated time of completion:

30-45 minutes.

## Scope your issue
Before getting into actual troubleshooting steps, it’s important to emphasize that while it may seem obvious, the better you understand the problem you’re experiencing, the quicker and easier it will be for you to fix it. Whether you’re tasked with fixing a problem that you are experiencing yourself, or a problem reported to you by someone in your organization, it is recommended that you take a moment and answer the following questions:

1. What specifically isn’t working and/or what is your goal?
2. What is the frequency or pattern for the issue? Is the problem still happening?
3. How did you become aware that the problem exists?
4. Has this ever worked? If so, when did it stop? Was anything changed in the environment right before it stopped working?
5. What percentage of clients are affected?
6. What has been done already (if anything) to try to fix it?
7. Know the exact version of the client and the version of the server. Are these systems up to date?
8. What do affected clients have in common (e.g. same subnet, AD site, domain, physical location, site, site system, etc.)?

Knowing and understanding the answers to these questions will put you on the best path for a quick and easy resolution to whatever problem you’re experiencing.

## Next steps
If you know the specific area within the Software Update Management process that you’d like to troubleshoot, select it below. If unsure, start with Client Software Update Scanning and we’ll walk through the entire process from beginning to end.

>[!div class="step-by-step"]

>[Client Software Update Scanning](.\ts-sum-client-scanning.md)

>[WSUS to Microsoft Update synchronization](.\ts-sum.md)  

>[Installation, supersedence, or detection issues with specific updates](.\ts-sum.md)
