---
# required metadata

title: Intune evaluation guide | Microsoft Intune
description: Introduction and prerequisites on how to set up a free, 30-day evaluation of Intune
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Intune evaluation guide
Setting up a free 30-day evaluation of Intune to manage your mobile devices and computers is quick and easy. With just a few simple steps in the evaluation, you can add up to 100 users and devices, set up groups, configure compliance policies, and enroll and manage mobile devices and computers.

In this topic, you'll learn the basics  to get an Intune evaluation up and running and get an overview of the service so you can evaluate Intune's features and capabilities.

Watch the following five-minute demo video to learn how easy it is to get started with a free evaluation of Microsoft Intune and to manage your devices. The first part of the video mentions a portal that has been "retired" so, although you'll use a different portal, the steps will be essentially the same. You can read more about the portal [here](https://docs.microsoft.com/intune/deploy-use/account-portal-merged-with-Office-365).

<iframe width="675" height="480" src="https://www.youtube.com/embed/ltcZvm4VOFU" frameborder="0" allowfullscreen></iframe>

## Before you begin
Before you get started with Intune, you'll need the following:

-   A device with a Silverlight-enabled web browser that you can use to access the websites where you'll  create Intune user accounts (the **Office 365 admin center**) and where you manage devices, groups, and policies  (the **Intune administration console**).

-   A second device with a web browser that you'll use  to test how Intune users will enroll and manage their devices using the Company Portal. You'll also test how users find and install apps and request help from administrators. If you don't have a second device, you can use the “privacy mode” setting on the same browser that you use for Intune administration (for example: in Internet Explorer, you can choose **Tools** &gt; **InPrivate Browsing**).

-   If you have an existing Microsoft Online Services account, you'll need the  administrator credentials for that account. If you don’t have such an account, or if you want to use this Intune tenant for evaluation purposes only, you don't need these administrator credentials.

-   If you'll manage iOS or Windows Phone devices with the Intune evaluation, you'll need certificates (or keys) and accounts to retrieve those certificates (see the following table). Android devices don't need any additional certificates.

    |Platform|Certificate Requirements|More information|
    |------------|----------------------------|--------------------|
    |Windows Phone 8.1 and Windows Phone 8 |No certificate is required for Windows Phone 8.1 users who install the Company Portal app from the Store. A Symantec certificate is required for Windows Phone 8.0 or to use Intune to deploy the Company Portal app to Windows Phone 8.1 devices.|This guidance assumes your users get the Company Portal app from the Store on a Windows Phone 8.1 or later device. For information about Windows Phone 8.0 support, see [Set up Windows Phone management with Microsoft Intune](/Intune/Deploy-Use/set-up-windows-phone-management-with-microsoft-intune).|
    |Windows 10, Windows RT 8.1, Windows RT, or Windows 8.1 devices|There are no certificate requirements for enrolling Windows RT and Windows devices.|[Install the Windows PC client with Microsoft Intune](/Intune/Deploy-Use/install-the-windows-pc-client-with-microsoft-intune).|
    |iOS 7.1 or later|Get an Apple Push Notification service certificate.|Request an Apple Push Notification service certificate from Apple, as described here: [Set up iOS and Mac management with Microsoft Intune](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune).|

## Steps to complete a 30-day evaluation of Intune
- [Step 1: Sign in or sign up for a 30-day evaluation](get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md). Before  you sign up or sign in to Intune,  you should consider whether to sign in using an existing account or create a temporary account to be used only for the 30-day evaluation of Microsoft Intune.
- [Step 2: Add users](get-started-with-a-30-day-trial-of-microsoft-intune-step-2.md). Now that you have set up your account, you'll either the add individual user accounts to Intune or add users in bulk (see the instructions in this section). Before you get started, it's important that you understand how Intune handles administrator accounts.
- [Step 3: Create groups to organize users and devices](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md). Groups in Intune give you great flexibility for managing your devices and users. You can set up groups to suit your organizational needs (for example, by geographic location, department, or hardware characteristics) and use them to perform a variety of administrative tasks at scale, from setting policies for a set of users to deploying applications to a set of devices.
- [Step 4: Create policies and publish an app](get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md). Intune policies provide settings that help you control the security settings on mobile devices, maintain Windows Firewall and Endpoint Protection settings for computers, and deploy applications.
- [Step 5: Enroll mobile devices and install an app](get-started-with-a-30-day-trial-of-microsoft-intune-step-5.md). To set up mobile device management with Intune, you must set the mobile device management authority, enable management for specific device platforms, and enroll your devices using the Company Portal app. You can then deploy the Microsoft Skype application that you published.
- [Step 6: Other options and extras](get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md). Choose how to use alerts, reports, and other Intune capabilities to meet your business needs.
- [Step 7: Next steps](get-started-with-a-30-day-trial-of-microsoft-intune-step-7.md). Prepare to move to an Intune paid subscription and take advantage of the Intune "FastTrack Center Benefit.


### Next steps
It's time to get started with your 30-day evaluation subscription!

>[!div class="step-by-step"]
[**Sign up for Intune** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)

### See also
[Intune quick start guide](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune)
