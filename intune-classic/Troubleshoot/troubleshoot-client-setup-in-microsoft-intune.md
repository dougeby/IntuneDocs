---
# required metadata

title: Troubleshoot client setup 
description: Troubleshoot common client setup problems.
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/22/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e46d292b-1d16-46db-a87f-d53eefa4d22a
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: tscott
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Troubleshoot client setup in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use the following information to help you troubleshoot common client setup problems. If this information does not solve your problem, see [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) to find more ways to get help.

## Client installation fails

-   If no client software deployment alerts for the computer are displayed in the [Microsoft Intune administration console](https://manage.microsoft.com/) check the computer’s Internet connectivity and proxy configuration and make sure that the computer can communicate with the service URL, [https://manage.microsoft.com](https://manage.microsoft.com/). Then retry the client software installation.

-   You can have an email sent to selected recipients when a client software deployment failure alert occurs by configuring a notification rule in the **Admin** workspace. For more information, see [Get notified by Microsoft Intune alerts](/intune-classic/deploy-use/get-notified-by-alerts).

-   Intune displays the critical alert **Client Software Deployment Failure** if the client software fails to deploy. This will display in the **System Overview** page and **Alerts** pages of the [Microsoft Intune administration console](https://manage.microsoft.com/). Here's how to check for alerts:

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Alerts** &gt; **Overview**.

2.  On the **Alerts overview** page, you can review the following information:

    -   The top three alerts, which can be sorted by date, category, or severity

    -   The total number of active alerts

3.  Choose **All Alerts** to display the following information on the **Alerts** page. Critical alerts are displayed first:

    -   **Name** – The name of the alert type that generated the alert.

    -   **Source** – A link to the source of the alert.  If the display threshold of the alert type is set to **All**, then this link will display a single affected device.  If the display threshold of the alert type is set to a value, then this link will display a list of all the devices that are affected by this alert.

    -   **Last Updated** – This indicates the time when the alert was last modified. If an alert is closed, the time when the alert was closed is displayed.

    -   **Severity** – This indicates the severity of the alert

## Computer enrollment package doesn't download
**Issue:** While trying to enroll a computer you experience the following:
-  The enrollment package fails to download
-  The download dialog appears but times out

**Resolution:** On the browser you're using for the download, for the period when the download takes place, ensure that downloads are enabled, and that encrypted files can be saved to your local disc.

## Client installation hangs with error code 0x80040154
**Issue:**

-  Client installation during enrollment hangs

-  Unable to enroll device

-  Error 0x80040154 in WindowsUpdate.log

This may be caused by the absence of critical software updates on the PC.

**Resolution:**
Ensure that your software update policy enables installation of critical updates, as described in [Keep Windows PCs up to date with software updates in Microsoft Intune](/intune-classic/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)


## Microsoft Intune policy-related errors in policyplatform.log
For non-MDM Windows devices, policy errors in the policyplatform.log file may be the result of non-default settings in the Windows User Account Control (UAC) on the device. Some non-default UAC settings can affect Microsoft Intune client installations and policy execution.

### To resolve UAC issues

1.  Retire the computer, as described in [Retire data and devices from Microsoft Intune management](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management).

2.  Wait 20 minutes for the client software to be removed.

    > [!NOTE]
    > Do not attempt to remove the client from Programs and Features.

3.  On the start menu type **UAC** to open the User Account Control settings.

4.  Move  the notification slider to the default setting.

## What to do if the client will not uninstall from the Microsoft Intune administrator console

### To remove the client software by using the Microsoft Intune command line tool

1.  Open a command prompt in administrator mode.

2.  Go to the folder *%programfiles%\Microsoft\OnlineManagement\Common*

3.  Run the following command ``ProvisioningUtil.exe /UninstallAgents /MicrosoftIntune``

## Client installation error codes
The following table describes error codes that are displayed in **Alerts** if client software installation fails. It includes suggestions for resolving the problem that is represented by each error code.

|Error code|Possible problem|Suggested resolution|
|--------------|--------------------|------------------------|
|**0x80CF0437**|The clock on the client computer is not set to the correct time.|Make sure that the clock and the time zone on the client computer are set to the correct time and time zone.|
|**0x80240438**, **0x80CF0438**, **0x80CF401B**|Cannot connect to the Intune service. Check the client proxy settings.|Verify that the proxy configuration on the client computer is supported by Intune, and that the client computer has Internet access. For more information about supported proxy configurations, see [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).|
|**0x80CF402C**|Cannot connect to the Intune service. Check network connectivity.|Verify the computer has network connectivity. Ensure the network cable is connected or wireless network is on.|
|**0x80240438, 0x80CF0438**|Proxy settings in Internet Explorer and Local System are not configured.|Check the client proxy settings and confirm that the proxy configuration on the client computer is supported by Intune, and that the client computer has Internet access. For more information about supported proxy configurations, see [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).|
|**0x80043001**|Enrollment package is out of date.|Download and install the current client software package from the **Admin** workspace. For instructions, see the [Install the Windows PC client with Microsoft Intune](/intune-classic/deploy-use/install-the-windows-pc-client-with-microsoft-intune) topic.|
|**0x80043004**|Subscription does not exist, or is disabled.|Verify that your account and subscription to Intune is still active. To view your account settings, sign in to your account in the [Office 365 admin center](http://go.microsoft.com/fwlink/?LinkId=698854%20).|
|**0x80043002**|Account is in maintenance mode.|You cannot enroll new client computers when the account is in maintenance mode. To view your account settings, sign in to your account in the [Office 365 admin center](http://go.microsoft.com/fwlink/?LinkId=698854%20).|
|**0x80043003**|Account is deleted.|Verify that your account and subscription to Intune is still active. To view your account settings, sign in to your account.|
|**0x80043005**|The client computer is retired.|Wait a few hours, remove any older versions of the client software from the computer, and then retry the client software installation. For instructions, see **What to do if the client will not uninstall from the Microsoft Intune administrator console**, above.|
|**0x80043006**|The maximum number of seats allowed for the account is reached.|Your organization must purchase additional seats before you can enroll more client computers in the service.|
|**0x80043007**|Could not find the certificate file in the same folder as the installer program.|Extract all files before you start the installation. Do not rename or relocate any of the extracted files: all files must exist in the same folder or the installation will fail. For more information, see [Install the Windows PC client with Microsoft Intune](/intune-classic/deploy-use/install-the-windows-pc-client-with-microsoft-intune).|
|**0x8024D015**, **0x00240005**, **0x80070BC2**, **0x80070BC9**, **0x80CFD015**|The software cannot be installed because a restart of the client computer is pending.|Restart the computer and then retry the client software installation.|
|**0x80070032**|One or more prerequisites for installing the client software were not found on the client computer.|Make sure that all required updates are installed on the client computer and then retry the client software installation. For more information about prerequisites for installing the client software, see [Network infrastructure requirements for Microsoft Intune](/intune-classic/get-started/network-infrastructure-requirements-for-microsoft-intune).|
|**0x80043008**|Could not start the Microsoft Online Management Updates service.|Contact Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).|
|**0x80043009**|The client computer is already enrolled into the service.|You must retire the client computer before you can re-enroll it in the service. For instructions, see [Retire devices from Microsoft Intune management](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management).|
|**0x8004300A**|(Stage 21) Error occurs when the enrollment package is deployed to the GPO to be installed at user scope and not machine scope. |Make sure the GPO is targeted correctly via GPSI at machine scope. To see forum postings on this subject, see this [TechNet Forum](https://social.technet.microsoft.com/Forums/en-US/bb9fa71c-c132-4954-abb0-70be8acbd925/failed-to-install-windows-intune?forum=microsoftintuneprod).|
|**0x8004300B**|The client software installation package cannot run because the version of Windows that is running on the client is not supported.|Intune does not support the version of Windows that is running on the client computer. For a list of supported operating systems, see [Network infrastructure requirements for Microsoft Intune](/intune-classic/get-started/network-infrastructure-requirements-for-microsoft-intune).|
|**0xAB2**|The Windows Installer could not access VBScript run time for a custom action.|This error is caused by a custom action that is based on Dynamic-Link Libraries (DLLs). When troubleshooting the DLL, you might have to use the tools that are described in [Microsoft Support KB198038: Useful Tools for Package and Deployment Issues](http://go.microsoft.com/fwlink/?LinkID=234255).|
|**0x8004300f**|The software cannot be installed because the System Center Configuration Manager client is already installed.|Remove the Configuration Manager client and then retry the client software installation.|
|**0x80043010**|The software cannot be installed because the Open Mobile Alliance Device Management (OMADM) client is already installed.|Un-enroll the OMADM client and then retry the client software installation.|
If installation problems persist, contact Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md). Have the client computer enrollment log (located in %*programfiles*%\Microsoft\OnlineManagement\Logs\Enrollment.log and %*userprofile*%\AppData\Local\Microsoft\OnlineManagement\Logs\Enrollement.log) and Windows Update log (%*windir*%\windowsupdate.log) available to show to support engineers.

## What to do if Endpoint Protection is not uninstalled when you uninstall the client

Sometimes the Host Protection (Endpoint Protection) agent may be left after you run the above commands. If that happens, run this command from an elevated prompt:

    ```
    "C:\Program Files\Managed Defender\Setup.exe" /x /q /s
    ```


### Next steps
If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
