---
# required metadata

title: Set up iOS device access to your company resources | Microsoft Docs
description: Describes how to get your iOS device managed by Intune
keywords:
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 02/27/2019
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
 - User help

# optional metadata

ROBOTS:  
#audience: 
#ms.devlang:
ms.reviewer: tisilv
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
---


# Set up iOS device access to your company resources  

> [!IMPORTANT]
> Apple has recently made some changes that affect Company Portal enrollment for devices running iOS 12.1.1 beta.  If you're an IT pro or administrator, and want to learn how you can prepare device users for these changes, go to [Microsoft Tech Community](https://go.microsoft.com/fwlink/?linkid=2078666&clcid=0x409).   

Enroll your iOS device with the Intune Company Portal app to gain secure access to your organization's email, files, and apps.

Before you can access proprietary data from a corporate or personal device, you're required to get your device managed. After your device becomes managed, your organization will assign policies and apps to the device through a mobile device management (MDM) provider, such as Intune. 

To maintain access to work or school information from your device, you must configure your device to match your organization's preferred settings. This article describes how to use Company Portal to enroll you device and maintain your organization's setting requirements. 

> [!NOTE]
> If you tried to access company email in the Mail app, and received a prompt to get your device managed, you're in the right place. Follow the instructions below to get access to your email and other company resources on your iOS device.  

## What to expect from the Company Portal app  

### Security  
During initial setup, the app requires that you authenticate yourself with your organization. It then informs you of any device settings you must update. For example, organizations often set minimum or maximum character password requirements that you'll be required to meet.     

### Protection  
After your device is enrolled, the Company Portal app will continue to make sure that your device is protected. If you install an app from an untrusted source, for example, the app will alert you and sometimes revoke access to company data. A policy like this is common in organizations, and often requires you to uninstall the untrusted app before you can regain access.  

### Setting notifications  
If after enrollment your organization enforces a new security requirement, such as multi-factor authentication, the Company Portal app will notify you. You'll have the chance to adjust your settings so that you can continue to work from your device.  

To learn more about enrollment, see [What happens when I install the Company Portal app and enroll my device?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios).  

## Enroll your iOS device:
Go to the App store to download and install the [Intune Company Portal app](install-and-sign-in-to-the-intune-company-portal-app-ios.md) to your device. During enrollment, you'll also need a Wi-Fi connection and access to Safari. 

If you pause for more than a few minutes during enrollment, the app might close or end setup. If this happens, open the Company Portal app and try again.  

1. Open Company Portal and sign in with your work or school account. 

    ![Example screenshot of Company Portal app, Sign in.](./media/ios-01-cp-enroll-1903.PNG)  

2. When prompted to receive Company Portal notifications, tap **Allow.** Company Portal uses notifications to alert you if, for example, your device settings need to be updated. 

    ![Example screenshot of Company Portal home page, "Notifications" prompt.](./media/ios-04-cp-enroll-1903.PNG)  

3. On the **Set up access** screen, select **Begin.**  

 ![Example screenshot of Company Portal, "Set up access" screen.](./media/ios-05-cp-enroll-1903.PNG)  

4. Read through the list of device information your organization can and can't see. [Additional details about this topic](what-info-can-your-company-see-when-you-enroll-your-device-in-Intune.md) can be found via the **Learn more** link. When you're done, tap **Continue**.  

    ![Example screenshot of Company Portal app, "What can my organization see", with Continue button.](./media/ios-06-cp-enroll-1903.PNG)  
 
5. Read through the information on the **What's next?** screen. Because of recent changes from Apple, this screen might not accurately describe the next steps for your device. If you're on an iOS device that runs:
    * **Version 12.1 and earlier**: This screen accurately describes your next-step experience. 
    * **Version 12.1.1 and later**: This screen might not accurately describe your next-step experience. In the next few steps, use any instructions specific to iOS 12.1.1 and later.  

    ![Example screenshot of Company Portal app, "What's next", with Continue button.](./media/ios-07-cp-enroll-1903.PNG)  

6. Safari opens the Company Portal website and prompts you to download the management profile. Tap **Allow**. 

    ![Example screenshot of Safari prompt to Ignore or Allow configuration profile download.](./media/ios-09-cp-enroll-1903.PNG)  

7. After you receive confirmation that the profile downloaded, tap **Close**. 

    > [!IMPORTANT]
    > You must install this profile within 8 minutes of downloading it. If you don't, the profile will be removed and you'll have to restart enrollment. 
  
    If you're on an iOS device that runs:  

    * **Version 12.1 and earlier**: You'll be automatically redirected to the **Settings** app on your device.  
    * **Version 12.1.1 and later**: If you aren't automatically redirected to the **Settings** app, close Safari and manually open the **Settings** app.  

    ![Example screenshot of Safari, Profile Downloaded confirmation, with Close button.](./media/ios-08-cp-enroll-1903.PNG)  


8. In the **Settings** app, tap **Install Downloaded Profile** > **Install**.   

    ![Example screenshot of the Settings app, Install Downloaded Profile setting, with a red badge that indicates a recently downloaded profile.](./media/ios-10-cp-enroll-1903.PNG)  

    If prompted, enter your device password. Then tap **Install**.  

      ![Example screenshot of the Settings app, Management Profile setting, showing the Install button in top-right corner.](./media/ios-11-cp-enroll-1903.PNG)  

9. The next screen is a standard system warning for device management. To learn more about what your organization can and can't see on your device, see the relevant [Intune docs article](what-info-can-your-company-see-when-you-enroll-your-device-in-Intune.md). To continue with installation, tap **Install**. If you're prompted to trust remote management, tap **Trust**.  

    ![Example screenshot of Settings app, standard system warning screen for root certificate and mobile device management.](./media/ios-15-cp-enroll-1903.PNG)  

10. After installation is complete, tap **Done**. To verify that the profile was installed, go to the **Profiles & Device Management** settings. Check that the profile is listed under **Mobile Device Management**.   

    ![Example screenshot of Settings app, Profiles & Device Management settings, showing the management profile.](./media/ios-00-cp-enroll-1903.PNG)  


11. Return to the **Company Portal** app > **What's next?** screen. Tap **Continue**.  

12. Company Portal will begin to sync and set up your device. A yellow triangle appears if your device still needs to sync or if you need to adjust device settings. 

    ![Example screenshot of Company Portal, "Set up access" screen, with yellow triangle next to setting requirement.](./media/ios-12-cp-enroll-1903.PNG)  

You'll know that setup is complete when all items in the list show a green circle.  

   ![Example screenshot of Company Portal, "You're all set!" screen, showing all green circles.](./media/ios-13-cp-enroll-1903.PNG)  

> [!Note]
> If your organization monitors voice and data limits, or provides you with a company-owned device, you might have a few more steps to complete. If you're prompted to install the **Datalert** app, see [enrolling your device in telecom expense management](enroll-your-device-with-telecom-expense-management-ios.md). If your organization is part of Apple's Device Enrollment Program, find out [how to enroll your company-owned device](enroll-your-device-dep-ios.md).  

## Next steps  
Find apps that will help you at work or school. Learn [how apps are made available](use-managed-apps-on-your-device-ios.md) to you through Company Portal.  

Still need help? Check in with your company support. You can find their contact information on the [Company Portal website](https://go.microsoft.com/fwlink/?linkid=2010980).  
