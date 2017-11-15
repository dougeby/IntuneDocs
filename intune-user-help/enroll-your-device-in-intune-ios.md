---
# required metadata

title: Set up access to your company resources | Microsoft Docs
description: Describes how to get your iOS device managed by Intune
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
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

---


# Set up access to your company resources

Your company has lots of proprietary information, from email, to files, networks, and more. Your company is using Microsoft Intune to help protect that information when you access it from your iOS device. This lets them manage those resources, keep them more secure, and give you the freedom to use your preferred device to get your work done.

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment/player]

> [!NOTE]
> If you're trying to access company email in the Mail app, it's likely that you were prompted to manage your device to keep it secure. Follow the instructions below to get access to your email and other company resources on your iOS device.

## Before you start

- Make sure that you finish the entire process once you start. Pausing for more than a few minutes usually stops your progress and requires you to start over.
- If this process should fail, you need to return to the Company Portal app to try again.
- Make sure that your Wi-Fi is working, and that Safari works on your device.
- Download the [Install and sign in to the Intune Company Portal app](install-and-sign-in-to-the-intune-company-portal-app-ios.md).


## Using the Company Portal app to set up access to company resources

|What you see|Explanation|
|---|---|
|![Company Portal sign in screen, with "Sign in" button on bottom.](./media/ios-0-cp-enroll-1711.png)|Open the Company Portal app and tap **Sign in**.|
|![Azure AD sign in prompt.](./media/ios-0a-cp-enroll-1711.png)|Enter your company email address, then tap **Next**.|
|![Azure AD password prompt.](./media/ios-0b-cp-enroll-1711.png)|Enter your password, then tap **Sign in**.|
|![Loading company resources splash screen.](./media/ios-1-cp-enroll-1711.png)|Wait for this to load.|
|![Terms and conditions.](./media/ios-2-cp-enroll-1711.png)|Read and **Accept All** of the Terms and Conditions.|
|![Set up company access screen. Both management and settings are currently in need of resolution.](./media/ios-3-cp-enroll-1711.png)|Tap on **Get your device managed** to begin the process of making your device able to access company resources. If you can't do this right now, you can **Postpone** the process, but it means you won't be able to get email, documents, and more.|
|![What can my company see screen.](./media/ios-4-cp-enroll-1711.png)|You can **Learn more** about what your company can see by tapping the link at the bottom. Otherwise, tap **Continue**.|
|![What's next screen.](./media/ios-5-cp-enroll-1711.png)|This screen walks you through what's happening in the setup. You'll spend time in Safari, the Settings app and the Company Portal app to complete this process. Tap **Next**.|
|![Loading screen after tapping Next on What's next.](./media/ios-6-cp-enroll-1711.png)||
|![Switched out to Safari for enrolling.](./media/ios-7-cp-enroll-1711.png)|You're sent to Safari to get management information for your device.|
|![System prompt to ask for Settings app to be opened.](./media/ios-8-cp-enroll-1711.png)|Tap **Allow** to open the Settings app to download the configuration profile. You install this to let your company manage corporate information on your device.|
|![Profile open in settings.](./media/ios-9-cp-enroll-1711.png)|Tap **Install**.|
|![Installing profile modal dialog from bottom of screen.](./media/ios-10-cp-enroll-1711.png)|Tap **Install**.|
|![Profile is installing loading screen.](./media/ios-11-cp-enroll-1711.png)|Wait for this to load.|
|![Profile management warning screen.](./media/ios-12-cp-enroll-1711.png)|This warning, written by Apple, lets you know more about what types of actions could be taken on a device under management. Find out more about [what information your company can see](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md)|
|![System prompt asking about trust on remote management.](./media/ios-13-cp-enroll-1711.png)|Tap **Trust** to allow your company to manage corporate information and settings on your device.|
|![Profile finishing installing load screen.](./media/ios-14-cp-enroll-1711.png)|Wait for this to load.|
|![Profile installed screen.](./media/ios-15-cp-enroll-1711.png)|Your profile is installed and your device's corporate information and settings are much closer to being managed.|
|![Switched out to Safari for enrolling.](./media/ios-16-cp-enroll-1711.png)|You're sent back to Safari to finish getting management information for your device. |
|![System prompt to open company portal.](./media/ios-17-cp-enroll-1711.png)|Tap **Open**.|
|![Loading company resources screen.](./media/ios-18-cp-enroll-1711.png)|Wait for this to load.|
|![Select device category in company portal app.](./media/ios-19-cp-enroll-1711.png)|Select the best category for your device. This usually has to do with who owns the device, or where it's located most of the time.|
|![Category selected.](./media/ios-20-cp-enroll-1711.png)||
|![Device management successful; now need to update settings.](./media/ios-21-cp-enroll-1711.png)|You've successfully gotten your device managed. There are likely still settings, like the length of your password, that your company may need you to update. Tap **Update device settings** to proceed.|
|![Confirming device settings.](./media/ios-22-cp-enroll-1711.png)|Company Portal will check to see if any of your settings need to be updated.|
|![Settings check finished, with an incorrect OS version](./media/ios-23-cp-enroll-1711.png)|Company Portal will provide instructions on how you can fix any issues with your settings. Once you finish fixing the issues, tap **Check Settings**.|
|![Confirming device settings loading screen](./media/ios-24-cp-enroll-1711.png)|Your device will check to see if your settings are secure enough to access company resources.|
|![Successfully enrolled and updated settings](./media/ios-25-cp-enroll-1711.png)|Congratulations! Your device is now enrolled in Intune.|

> [!Note]
> You may have a few more steps to complete before your device is fully managed. Find out more about [enrolling your device using telecom expense management](enroll-your-device-with-telecom-expense-management-ios.md). If your organization is using Apple's Device Enrollment Program, find out more [here](enroll-your-device-dep-ios.md).

Still need help? Contact your company support. For contact information, check the [Company Portal website](https://portal.manage.microsoft.com).
