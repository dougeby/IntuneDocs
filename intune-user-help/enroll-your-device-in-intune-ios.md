---
# required metadata

title: Set up iOS device access to your company resources | Microsoft Docs
description: Describes how to get your iOS device managed by Intune
keywords:
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/05/2018
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
ms.reviewer: esmich
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
---


# Set up iOS device access to your company resources

Enroll your iOS device with the Intune Company Portal app to gain secure access to your organization's email, files, and apps.

Before you're allowed to access proprietary data from a coporate or personal device, you're required to get your device managed. After your device becomes managed, your organization will assign policies and apps to the device through their mobile device management (MDM) provider. 

To maintain access to work or school information from your device, you must configure your device to match your organization's preferred settings. This article describes how Company Portal helps you enroll, configure, and maintain your device to meet these requirements.

> [!NOTE]
> If you tried to access company email in the Mail app, and received a prompt to get your device managed, you're in the right place. Follow the instructions below to get access to your email and other company resources on your iOS device.

## What to expect from the Company Portal app

### Security
During initial setup, the app requires that you authenticate yourself with your organization. It then informs you of any device settings you must update. For example, organizations often set minimum or maximum character password requirements that you'll be required to meet.    

### Protection
After your device is enrolled, the Company Portal app will continue to make sure that your device is protected. If you install an app from an untrusted source, for example, the app will alert you and sometimes revoke access to company data. App protection policies like this one are common in organizations. They often require you to uninstall the untrusted app before you can regain access.

### Setting notifications
If after enrollment your organization enforces a new security requirement, such as multi-factor authentication, the Company Portal app will notify you. You'll have the chance to adjust your settings so that you can continue to work from your device.  

To learn more about enrollment, see [What happens when I install the Company Portal app and enroll my device?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios). 

## Before you start

- Once you begin enrollment, make sure that you finish the entire process. If you pause for more than a few minutes, setup may end and require you to start over.  
- If this process should fail, return to the Company Portal app and try again.  
- Check that your Wi-Fi is working, and that Safari works on your device.
- Download and install the [Intune Company Portal app](install-and-sign-in-to-the-intune-company-portal-app-ios.md).  


## Using the Company Portal app to set up access to company resources

|What you see|Explanation|
|---|---|
|![Company Portal sign-in screen, with "Sign in" button on bottom.](./media/ios-01-cp-enroll-1802.PNG)|Open the Company Portal app and tap **Sign In**.|
|![Azure AD sign-in prompt.](./media/ios-02-cp-enroll-1802.PNG)|Enter your company email address, then tap **Next**.|
|![Azure AD password prompt.](./media/ios-03-cp-enroll-1802.PNG)|Enter your password, then tap **Sign in**.|
|![Loading company resources splash screen.](./media/ios-04-cp-enroll-1802.PNG)|Wait for this screen to load.|
|![Terms and conditions page.](./media/ios-05-cp-enroll-1802.PNG)|Read and **Accept All** of the Terms and Conditions.|
|![Set up company access screen. Both management and settings are currently in need of resolution.](./media/ios-06-cp-enroll-1802.PNG)|Tap on **Begin** to begin the process of making your device able to access company resources. If you can't do this right now, you can **Postpone** the process, but it means you won't be able to get email, documents, and more.|
|![What can my company see screen.](./media/ios-07-cp-enroll-1802.PNG)|You can **Learn more** about what your company can see by tapping the link at the bottom. Otherwise, tap **Continue**.|
|![What's next screen.](./media/ios-08-cp-enroll-1802.PNG)|This screen walks you through what's happening in the setup. You'll spend time in Safari, the Settings app, and the Company Portal app. Tap **Continue**.|
|![Loading screen after tapping Next on What's next.](./media/ios-09-cp-enroll-1802.PNG)|Wait for this screen to load.|
|![Switched out to Safari for enrolling.](./media/ios-cp-sent-to-safari-1808.png)|You're sent to Safari to get management information for your device.|
|![System prompt to ask for Settings app to be opened.](./media/ios-8-cp-enroll-1711.PNG)|Tap **Allow** to open the Settings app to download the configuration profile. You install this to let your company manage corporate information on your device.|
|![Scressnhot of the Install Profile screen in device settings.](./media/ios-9-cp-enroll-1711.PNG)|Tap **Install**.|
|![Installing profile modal dialog from bottom of screen.](./media/ios-10-cp-enroll-1711.PNG)|Tap **Install**.|
|![Profile is installing loading screen.](./media/ios-11-cp-enroll-1711.PNG)|Wait for this screen to load.|
|![Profile management warning screen.](./media/ios-12-cp-enroll-1711.PNG)|This warning, written by Apple, lets you know more about what types of actions could be taken on a device under management. Find out more about [what information your company can see](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).|
|![System prompt asking about trust on remote management.](./media/ios-13-cp-enroll-1711.PNG)|Tap **Trust** to allow your company to manage corporate information and settings on your device.|
|![Profile finishing installing load screen.](./media/ios-14-cp-enroll-1711.PNG)|Wait for this screen to load.|
|![Profile installed screen.](./media/ios-15-cp-enroll-1711.PNG)|Your profile is installed and your device's corporate information and settings are much closer to being managed.|
|![Switched out to Safari for enrolling.](./media/ios-16-cp-enroll-1711.PNG)|You're sent back to Safari to finish getting management information for your device. |
|![System prompt to open company portal.](./media/ios-17-cp-enroll-1711.PNG)|Tap **Open**.|
|![Loading company resources screen.](./media/ios-21-cp-enroll-1802.PNG)|Wait for this screen to load.|
|![Select device category in company portal app.](./media/ios-22-cp-enroll-1802.PNG)|Select the best category for your device. This usually has to do with who owns the device, or where it's located most of the time.|
|![Category selected.](./media/ios-23-cp-enroll-1802.PNG)||
|![Device management successful; now need to update settings.](./media/ios-24-cp-enroll-1802.PNG)|You've successfully gotten your device managed. There are likely still settings, like the length of your password, that your company may need you to update. Tap **Continue** to proceed.|
|![Confirming device settings.](./media/ios-25-cp-enroll-1802.PNG)|Company Portal will check to see if any of your settings need to be updated.|
|![Settings check finished, with an incorrect OS version](./media/ios-26-cp-enroll-1802.PNG)|Company Portal will provide instructions on how you can fix any issues with your settings. Once you finish fixing the issues, tap **Check Settings**.|
|![Confirming device settings loading screen](./media/ios-27-cp-enroll-1802.PNG)|Your device will check to see if your settings are secure enough to access company resources.|
|![Successfully enrolled and updated settings](./media/ios-28-cp-enroll-1802.PNG)|Congratulations! Your device is now enrolled in Intune.|

> [!Note]
> You may have a few more steps to complete before your device is fully managed. Find out more about [enrolling your device using telecom expense management](enroll-your-device-with-telecom-expense-management-ios.md). If your organization is using Apple's Device Enrollment Program, find out more [here](enroll-your-device-dep-ios.md).

Still need help? Check in with your company support. You can find their contact information on the [Company Portal website](https://go.microsoft.com/fwlink/?linkid=2010980).  
