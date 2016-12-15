---
# required metadata

title: Get started with the Microsoft Intune App SDK | Microsoft Docs
description: Quickly enable your mobile app for mobile application management (MAM) with Microsoft Intune.
keywords:
author: mtillman
manager: angrobe
ms.author: oydang
ms.date: 12/15/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: oydang
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Get started with the Microsoft Intune App SDK

This guide will help you quickly enable your mobile app for mobile application management (MAM) with Microsoft Intune. You may find it useful to first understand the benefits of the Intune App SDK, as explained in the [Intune App SDK overview](intune-app-sdk.md).

This guide walks through the major steps to enable MAM in your app with Microsoft Intune. The Intune App SDK supports similar scenarios across platforms, and is intended to create a consistent experience across the platforms for IT admins. But there are small differences in the support of certain features, because of platform limitations.

## Register your store app with Microsoft

**If your app is internal to your company and will not be made available to a public app store**:

You *do not need* to register your app. For internal line-of-business apps, the IT admin will deploy the app internally. Intune will detect that the app has been built with the SDK, and will let the IT admin apply MAM policy settings to it. You can skip to the section [Enable your iOS or Android mobile app for MAM with the SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk).

**If your app will be released to a public app store, like the Apple App Store or Google Play**:

You *must* first register your app with Microsoft Intune and agree to the registration terms. IT admins can then apply Intune MAM policy settings to the enlightened app, which will be listed as an Intune app partner. Until registration has been finished and confirmed by the Microsoft Intune team, Intune admins will not have the option to apply the MAM policy to your app's deep link. Microsoft will also add your app to its [Microsoft Intune Partners page](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps). There, the app's icon will be displayed to show that it supports the Microsoft Intune MAM policy.

To begin the registration process, fill out the [Microsoft Intune App Partner Questionnaire](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u).

We will use the email addresses listed in your questionnaire responses to reach out and continue the registration process. Additionally, we use your registration email address to contact you if we have any concerns.

> [!NOTE]
> All information collected in the questionnaire and through email correspondence with the Microsoft Intune team will honor the [Microsoft Privacy Statement](https://www.microsoft.com/en-us/privacystatement/default.aspx).

**What to expect in the registration process**:

1. After you have submitted the questionnaire, we will contact you via your registration email address, to either confirm successful receipt or request additional information to finish the registration.
2. After we receive all necessary information from you, we will send you the Microsoft Intune App Partner Agreement to sign. This agreement describes the terms that your company must accept before it becomes a Microsoft Intune app partner.
3. You will be notified when your app is successfully registered with the Microsoft Intune service and when your app is featured on the [Microsoft Intune partners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) site.
4. Finally, your app's deep link will be added to the next monthly Intune Service update. For example, if the registration information is finished in July, the deep link will be supported in mid-August.

If your app's deep link changes in the future, you will need to re-register your app. Additionally, please inform us if you update your app with a new version of the Intune App SDK.



## Download the SDK files

The Intune App SDKs for native iOS and Android are hosted on a Microsoft GitHub account. These public repositories have the SDK files for iOS and Android, respectively:

* [Intune App SDK for iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Intune App SDK for Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

If your app is a Xamarin or Cordova app, please use these developer tools:

* [Intune App SDK Xamarin Component](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [Intune App SDK Cordova Plugin](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

It's a good idea to sign up for a GitHub account that you can use to fork and pull from our repositories. GitHub lets developers communicate with our product team, open issues and receive quick responses, view release notes, and provide feedback to Microsoft. For questions on the GitHub account and repositories, contact msintuneappsdk@microsoft.com.





## Enable your iOS or Android mobile app for MAM with the SDK

To integrate the Intune App SDK into your native iOS app, you will need the following:

* **[Intune App SDK for iOS Developer Guide](intune-app-sdk-ios.md)**: This document will walk you step-by-step through enabling your mobile iOS app with the Intune App SDK.


To integrate the Intune App SDK into your native Android app, you will need the following:

* **[Intune App SDK for Android Developer Guide](intune-app-sdk-android.md)**: This document will walk you step-by-step through enabling your mobile Android app with the Intune App SDK.

To build Cordova apps with the Intune App SDK Cordova Plugin, you will need the following:

* **[Intune App SDK Cordova Plugin guide](intune-app-sdk-cordova.md)**: This document will help you build iOS and Android apps using Cordova for Intune mobile application management.

To build Xamarin apps with the Intune App SDK Xamarin Component, you will need the following:

* **[Intune App SDK Xamarin Component guide](intune-app-sdk-xamarin.md)**: This document will help you build iOS and Android apps using Cordova for Intune mobile application management.




## Configure Telemetry for your app

Microsoft Intune collects data on usage statistics for your app.

* **Intune App SDK for iOS**: The SDK logs SDK telemetry data on usage events by default. This data is sent to Microsoft Intune.

    * If you choose not to send SDK telemetry data to Microsoft Intune from your app, you must disable telemetry transmission by setting the property `MAMTelemetryDisabled` to "YES" in the IntuneMAMSettings dictionary.

* **Intune App SDK for Android**: Telemetry data is not logged through the SDK.

## Test your MAM-enabled app with Microsoft Intune

After you finish the necessary steps to integrate your iOS or Android app with the Intune App SDK, you will need to ensure that all the app management policies are enabled and functioning for the user and the IT admin. To test your integrated app, you will need the following:

<!--TODO-->

* **Testing your MAM enabled app with Microsoft Intune**: This document will walk you step-by-step through how to test your MAM-enabled iOS or Android apps with Microsoft Intune. You can find this document in the GitHub repositories of the SDKs.

* **Microsoft Intune account**: To test your MAM-enabled apps with Microsoft Intune, you will need a Microsoft Intune account.
	* If you are an ISV enabling your iOS or Android store apps for Intune MAM, you will receive a promo code after you finish the registration with Microsoft Intune, as outlined in the registration step. The promo code will let you sign up for a Microsoft Intune trial for one year of extended use.
	* If you are developing a line-of-business app that will not be shipped to the store, you are expected to have access to Microsoft Intune through your organization. You can also sign up for a one-month free trial in [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).
