---
title: Your computer is already enrolled
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 8d3a40f5-99e9-48dc-9706-f7a3a23e5704
author: staciebarker
---

# Your computer is already enrolled
You are seeing this page because you ran Setup for the Intune client software. However, the software is already installed on your computer and Setup cannot continue.

This could be because:

-   The client software was installed earlier, and Setup ran again.

-   Setup was run on the computer after an IT admin retired your device from Intune. After your device is retired, it might take several hours before the client software is removed from your computer.

-   Setup has detected a recently failed install or failed removal of the client software.

## <a name="bkmk_install"></a>What Setup installs on your computer
Setup installs the Intune client. After Setup finishes, the client software continues to run in the background where it configures your computer for use with Intune. This process can take some time to complete, and includes:

-   Enrolling your computer with Intune

-   Submitting inventory about the computer hardware and installed software

-   Configuring Intune policy, including installation of Endpoint Protection (if configured)

-   Installing Intune Center

After Intune Center installs you can use it to access the company portal where you can link your computer to your work account.

## <a name="bkmk_center"></a>Microsoft Intune Center
The Intune Center installs as an app on your computer after the computer successfully installs the client software and enrolls your computer with Intune. You can use the Intune center to:

-   **Get applications from the company portal** - Find and install apps that are deployed by your IT admin. When you first sign in to the company portal on a newly enrolled computer you get the option to link your work account with that computer.

-   **Check for software updates** – Find software updates that are deployed by your Intune administrator.

-   **Start an Endpoint Protection scan of your computer** – You can start a scan for malicious software on your computer.

-   **Ask for remote assistance** – This option is available only when remote assistance is supported by your computers operating system.

## <a name="bkmk_validate"></a>Validate that the client software is installed or has been removed
**Validate the client is installed:**
The Intune client installation is complete when the following apps are available on the computer:

-   **Intune Center**

-   **Intune Endpoint Protection** (if Endpoint Protection is enabled by your IT admin)

If you are comfortable with using Task Manager, you can search for the Intune client service, which should be running:

-   **OmcSvc**

**Validate the client has been removed:**
After the Intune client uninstalls from a computer, the apps that were installed when the client was installed are removed, including the Intune Center.

The Intune client service **OmcSvc** is removed.

## <a name="bkmk_remove"></a>How to remove the client software from the computer
By default, several hours after your IT admin retires your computer from the Intune admin console, the Intune client software will uninstall.

To manually uninstall the Intune client software from a computer, you can use the following steps to force the uninstall:

1.  On the computer, open a command prompt in administrator mode.

2.  Go to the folder **%programfiles%\Microsoft\OnlineManagement\Common**

3.  Run the following command: **ProvisioningUtil.exe /UninstallAgents /MicrosoftIntune**

This will schedule the removal of the client software.

