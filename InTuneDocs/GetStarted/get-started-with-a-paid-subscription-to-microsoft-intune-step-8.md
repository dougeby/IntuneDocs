---
title: Enroll computers in Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid:
author: Staciebarker
---

# 8. Enroll computers in Intune

You can install the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] client software on computers in the following ways:

-   Users can use an installer provided by the administrator to manually enroll

-   [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] software can be included in an OS image or deployed using Group Policy

-   End users can also self-enroll their devices through the [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] company portal

Each enrolled computer is linked to the user account that was used to install the client software. Microsoft Intune Endpoint Protection is also installed by default during Intune client installation on computers. Endpoint Protection helps to secure the computers in your organization by providing real-time protection against potential threats, keeping malicious software definitions up to date, and automatically running scheduled scans. For added security, you can also use Intune policies to manage Windows Firewall settings on managed computers.

## What to know before you start

-   The user must be an administrator on the computer to install the client software.

-   Self-enrolling requires that Internet Explorer is installed on the client computer.

-   Each time a user self-enrolls a computer, it uses a [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] license.

-   You must use a Microsoft Online Services work or school account to self-enroll a computer. This is the account that you used to sign in, or the administrator account that was created when you signed up for the free trial.

For this example, you'll use the self-enrollment approach:

1.  In the [Intune administration console](https://manage.microsoft.com/), choose **Admin** > **Company Portal**, and then scroll to the bottom of the screen. Copy the URL shown under **Intune company portal**.

2.  Use Internet Explorer to browse to the company portal URL that you acquired in the previous step, and log in with your administrator credentials.

3.  Choose **Add Device**.

4.  Choose **Download Software** > **Run**.

5.  Choose **Next** to start the [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] Setup wizard.

6.  When the Setup wizard has completed, choose **Finish**.

To learn more about computer management using [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], see [Install the Windows PC client with Microsoft Intune](/Intune/deployuse/install-the-windows-pc-client-with-microsoft-intune.html).

To learn more about software management using [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], see [Deploy and configure apps with Microsoft Intune](/Intune/deployuse/deploy-and-configure-apps-with-microsoft-intune.html).

## Next steps
Congratulations! You have just completed step 8 of the *Get started with a paid subscription to Microsoft Intune* guide.
>[!div class="step-by-step"]
>[Next](.\get-started-with-a-paid-subscription-to-microsoft-intune-step-9.md)  **Enroll mobile devices and install an app**
>
>[Previous](.\get-started-with-a-paid-subscription-to-microsoft-intune-step-7.md)  **Customize the company portal**
