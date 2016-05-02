---
title: Enroll trial Windows PCs in Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid:
author: Staciebarker
---
# Step 5: Enroll trial PCs in Intune
You can install the Intune client software on PCs in the following ways:

-   Users can use an installer provided by the administrator to manually enroll

-   Intune software can be included in an OS image, or deployed using Group Policy

-   End users can self-enroll their device through the Intune Company Portal

Each enrolled PC is linked to the user account that was used to install the client software. Microsoft Intune Endpoint Protection is also installed by default during Intune client installation on PCs. Endpoint Protection helps to secure PCs in your organization by providing real-time protection against potential threats, keeping malicious software definitions up to date, and automatically running scheduled scans. For added security, you can also use Intune policies to manage Windows Firewall settings on managed PCs.

What to know before you start:

-   The user must be an administrator on the PC to install the client software.

-   Self-enrolling requires that Internet Explorer is installed on the client PC.

-   Each time a user self-enrolls a PC, an Intune license is used

-   You must use a Microsoft Online Services work or school account to self-enroll a PC. This is the account that you used to sign in, or the administrator account that was created when you signed up for the free trial.

## Self-enroll a Windows PC
For this trial, follow these steps, which use the self-enrollment approach:

1.  In the [Intune administration console](https://manage.microsoft.com/), click **Admin** &gt; **Company Portal**, and then scroll to the bottom of the screen. Copy the URL shown under **Intune company portal**.

2.  Use Internet Explorer to browse to the Company Portal URL that you acquired in the previous step, and log in with your administrator credentials.

3.  Click **Add Device**.

4.  Click **Download Software** and then click **Run**.

5.  Click **Next** to start the Intune Setup wizard.

6.  When the Setup wizard has completed, click **Finish**.

To learn more about PC management using Intune, see [Install the Windows PC client with Microsoft Intune](/Intune/DeployUse/install-the-windows-pc-client-with-microsoft-intune).

To learn more about software management using Intune, see [Deploy and configure apps with Microsoft Intune](/Intune/DeployUse/deploy-and-configure-apps-with-microsoft-intune).

## Next steps
Congratulations! You have just completed step 5 of the *Get started with a 30-day trial of Microsoft Intune* walkthrough.

>[!div class="step-by-step"]

>[<< **Create policies**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step4.md)     [**Enroll devices** >>](.\get-started-with-a-30-day-trial-of-microsoft-intune-step6.md)  


### See also
[Get started with a 30 day trial of Microsoft Intune](get-started-with-a-30-day-trial-of-microsoft-intune.md)
