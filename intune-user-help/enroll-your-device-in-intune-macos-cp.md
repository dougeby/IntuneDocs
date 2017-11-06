---
# required metadata

title: Enroll your macOS device in Intune with Company Portal | Microsoft Docs
description: Describes how to enroll a macOS device in Intune with Company Portal app
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope:
 - User help

# optional metadata

ROBOTS:  
#audience:
#ms.devlang:
ms.reviewer: elocholi
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-enduser

---

# Enroll your macOS device in Intune with the Company Portal app

Getting access to your organization’s apps, data, and resources makes it easier for you to do your job. Your organization is using Intune to [manage access to those resources](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md), which requires you to download the Company Portal app for macOS. These instructions will work for macOS devices on OS X El Capitan 10.11+. You can find instructions for enrolling macOS devices on previous versions of macOS [here](enroll-your-device-in-intune-macos-legacy.md).

1. On your __Dock__, find __Safari__ and open a new window, then open the [Company Portal website](https://portal.manage.microsoft.com).

2. Log into the Company Portal website with your work or school account.

    [!INCLUDE[wit_nextref](includes/end-user-password-guidance.md)]

3. After logging in, click on the **Menu** in the top left corner of the page and select **My Devices**.

   ![A screenshot of the landing page for the web portal with the web portal showing that no apps can be installed yet, with a My Devices button underneath.](./media/macOS_enroll_001_landing_page.png)

4. On the __My Devices__ page, you will either see a list of enrolled devices or simply a banner. This depends on if you already have a device enrolled, macOS or otherwise. To enroll a device that is not listed, select the banner that says __If your device is listed, tap here to identify it. You can also tap here to enroll your device if it is not listed__. If you don't have any enrolled devices, the banner will read **You don't have any devices enrolled. Enroll this one by tapping here.**

    ![A screenshot of the My Device page, with a couple of unidentified devices above the banner prompt to enroll unlisted devices or identify unidentified ones.](./media/macOS_enroll_002_tap_here_banner.png)

5. Download the Company Portal app to your macOS device to continue enrolling.

    ![The notice that prompts a user to download the macOS Company Portal app. This notice has the text listed in the step above a button that says "Download" in the bottom right corner.](./media/macOS_enroll_IWP_CP_app_notice.png)

6. Your Mac will check to make sure that the download of **CompanyPortal.pkg** is safe to open. Open the installer and go through the install process.

7. When the installer has finished, open your **Applications** folder or the **Launchpad**, then open **Company Portal**.

8. Your Mac will show you a message that says, **"CompanyPortal" is an application downloaded from the Internet. Are you sure you want to open it?** Click **Open**.

  > [!NOTE]
  > Intune needs access to your computer to make sure that your device is secure enough to access your organization's resources. If your computer refuses to open the Company Portal app, try [turning off Gatekeeper](https://support.apple.com/HT202491) and then opening the app.

9. The first screen you see in the Company Portal app prompts you to **Sign In** with the same work or school account you used to log in to the Company Portal website.

10. The Company Portal confirms your account information, then shows you your **Device Enrollment** and **Device Compliance** statuses. There will be yellow triangles letting you know that you have actions you'll need to take to make sure your Mac is safe for use at work. Click **Begin** to start [enrolling your device into management](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).

11. Your Mac will begin enrolling into management. You might be prompted to provide your computer's login information during this time. This may take a few minutes to enroll. During this time, you can do other things on your computer. A message appears once you've completed Company Access Setup to let you know you're done.

Still need help? Check in with your company support. You can find their contact information on the [Company Portal website](https://portal.manage.microsoft.com).
