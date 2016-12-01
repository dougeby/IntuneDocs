---
# required metadata

title: Evaluate mobile device management in Microsoft Intune | Microsoft Docs
description: Evaluate MDM in your Intune free trial.
keywords:
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Evaluate mobile device management in Microsoft Intune
This evaluation guide will show you how mobile device management works in Intune. You will:
- Enroll a device to be managed by Intune.
- Create groups to organize users and devices.
- Create and deploy some device management policies to your groups.
- Publish an app so that users with enrolled devices can install it on their device.
<!--- - Monitor the device? View a report of compliant devices?--->
<!--- - Remove the device from management--->

## Assumptions
This guide assumes you are using the trial for evaluation purposes only and intend to start with a clean environment when you subscribe.

To make it easy for you to get started with the trial, we are setting up a very simple environment that uses Intune only and assumes it will be your mobile device management authority. However, throughout the guide we will point you to deeper technical content if you want to explore farther.

You can do everything in the trial version that you can do in a subscription version; the only difference is you are limited to 100 user accounts in the trial.

## What's not covered
|If you're interested in |Read this |
|------------------------|----------|
|MDM in a non-test environment | [Getting started](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune) |
|MDM with Intune and System Center Configuration Manager | [Hybrid mobile device management](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management) |

Because the above guides help you set up Intune in production environments, they are longer, with many more decision points you need to work through than in the evaluation guide.

To familiarize yourself quickly with Intune, we suggest starting with the evaluation guide and then moving on to the other guides.

## Prerequisites for this evaluation
- Internet Explorer 10 or later
- A device that you’ll use to test how Intune users will enroll and manage their devices using the Company Portal. We’re using an iPad and an Android phone for this guide.
- To manage the iPad or other iOS device, you’ll need an [Apple Push Notification service certificate](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).
- An [Intune trial subscription](sign-up-for-30-day-trial-microsoft-intune.md)

## Set your MDM authority
The first step you need to take to manage mobile devices with Intune is to set your **mobile device management (MDM) authority**.

If you are using Intune standalone, as this trial assumes you are, or if you are using Intune as part of an Enterprise Mobility + Security (EMS) subscription, you need to set Intune to be your mobile device management authority. That is, you designate Intune to be the service you use to manage mobile devices in your organization.

Customers who want to use Intune with System Center Configuration Manager to manage mobile devices need to decide whether to use Intune or Configuration Manager as their mobile device management authority. This is an important decision to make in a production environment because it is currently very difficult to change the setting once you make it, but is beyond the scope of this evaluation guide. To learn more about the implications of setting either Intune or Configuration Manager as your MDM authority, see [Choose between standalone Intune and hybrid mobile device management](https://docs.microsoft.com/en-us/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).

We will set Intune as the MDM authority for the trial; this will not affect your production environment unless you decide to use your trial for your production environment.

1. In the [Intune administration console](https://manage.microsoft.com/), choose **Admin** &gt; **Mobile Device Management**.
2. In the **Tasks** list, choose **Set MDM Authority**. The **Set MDM Authority** dialog box opens. <!---screen shot--->
3. Intune requests confirmation that you want Intune as your MDM authority. Select the checkbox and then choose **Yes** to use Intune to manage mobile devices.

## Enroll your test devices into Intune

For this guide, we'll be enrolling an Android phone and an Apple iPad, but provide links to [learn more about device enrollment in Intune](#Learn-more-about-device-enrollment) at the end of this section.
### Android
Install the **Intune Company Portal** app from Microsoft Corporation, available on [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612), and sign in with the Intune [user credentials you created](sign-up-for-30-day-trial-microsoft-intune.md#add-users) when you signed up for the free trial.

### iOS
Before users can enroll their iOS devices, you need to set up Intune to manage these devices.

1. **Get a certificate signing request**<br/>
Log on to Intune with your admin account and go to **Administration** > **Mobile Device Management** > **iOS and Mac OS X** > **Upload an APNs Certificate**, and then choose **Download the APNs certificate request**. Save the certificate signing request (.csr) file locally. The .csr file is used to request a trust relationship certificate from the Apple Push Certificates Portal. <!--- screen shot--->
2.	**Get an Apple Push Notification service certificate**<BR/>
Go to the [Apple Push Certificates Portal](https://idmsa.apple.com/IDMSWebAuth/login?appIdKey=3fbfc9ad8dfedeb78be1d37f6458e72adc3160d1ad5b323a9e5c5eb2f8e7e3e2&rv=2), and sign in with your company Apple ID to create the APNs certificate by using the .csr file. After choosing **Upload on Apple's Push Certificate Portal**, you will receive a .json file that cannot be used for APNs. Complete the download, return to the Apple Push Certificates Portal for Certificates for Third-Party Servers, and then choose **Download**.

 Download the APNs (.pem) certificate, and save the file locally. This Apple ID must be used later to renew your APNs certificate.
3.	**Add the APNs certificate to Intune**<BR/>
In the Microsoft Intune administration console, go to **Administration** > **Mobile Device Management** > **iOS and Mac OS X** > **Upload an APNs Certificate**, and then choose **Upload the APNs certificate**. Go to the certificate (.pem) file, choose **Open**, and then enter your Apple ID. With the APNs certificate. Intune can enroll and manage iOS devices by pushing policy to enrolled mobile devices.
4.	**Tell your users how to enroll their devices to get access to company resources.**<br/>
For end-user enrollment instructions, see [Enroll your iOS device in Intune](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-ios) and [Enroll your Mac OS X device in Intune](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-mac-os-x). The enrollment process tells users what they can expect, and what IT administrators can and can't see on their devices.


### Learn more about device enrollment

Intune supports the following device platforms:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

The requirements to enable device managemenet depend on the platforms you want to manage.
- **Android** mobile devices allow users to [enroll using the Company Portal app](/intune/deploy-use/set-up-android-management-with-microsoft-intune) available from Google Play. No additional configuration in Intune is required.
- [Set-up requirements for **iOS and Mac OS X**](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [Set-up requirements for **Windows Phone**](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

<!--- ## Verify enrollment--->
<!--- START HERE

### iOS and Mac OS X
Install the **Microsoft Intune Company Portal** app from Microsoft Corporation available in the App Store and sign in with Intune user credentials added above. View **Enrolled devices** to add your device.



### Windows Phone 8.1
Users install the **Company Portal** app from Microsoft Corporation, available in the Windows Phone store, and sign in with the Intune user credentials added above.  View **Enrolled devices** to add your device.

## Install the previously deployed app
Open the Company Portal on the mobile device, choose **Apps**, and then install **Microsoft Skype**.--->



## Next steps
[Create groups to organize users and devices](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)
