---
# required metadata

title: Getting Started With the Microsoft Intune App SDK | Microsoft Intune
description:
keywords:
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Getting Started With the Microsoft Intune App SDK

This Getting Started guide will help you quickly enable your mobile app for Mobile Application Management with Microsoft Intune. You may find it useful to first understand the benefits of the Intune App SDK as enumerated in the [Intune App SDK overview](intune-app-sdk.md).

This guide walks through the major steps needed to enable mobile app management in your app with Microsoft Intune. The Intune App SDK supports similar scenarios across platforms, and is intended to create a consistent experience across the platforms for IT administrators. However, there are small differences in the support of certain features due to platform limitations.

# Getting Started

## Register your store app with Microsoft

* **If your app is internal to your company and will not be made available to a public app store**:
You **do not need** to register your app. For internal line-of-business apps, the IT administrator will deploy the app internally using Microsoft Intune. Intune will detect the app has been built with the SDK, and will allow the IT administrator to apply MAM policy settings to it. You can skip to the section [Enable your iOS or Android mobile app for MAM with the SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk).

* **If your app will be released to a public app store, such as the Apple App Store or Google Play**: 
You **must** first register your app with Microsoft Intune and agree to the registration terms. After registering, IT administrators can apply Intune MAM policy settings to the enlightened app, which will be listed as an Intune app partner. Until registration has been complete and confirmed by the Microsoft Intune team, Intune administrators will not have the option to apply MAM policy to your app's deep link. Microsoft will also add your app to its [Microsoft Intune Partners page](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners), where the app's icon will be displayed to show that it supports Microsoft Intune MAM policy.

	To begin the registration process, **review and sign** the [Microsoft Intune Partner Agreement](https://connect.microsoft.com/ConfigurationManagervnext/Survey/Survey.aspx?SurveyID=17806). This agreement describes the terms your company must accept before becoming a Microsoft Intune app partner. You will need to sign in before you can view this document. You can find the agreement in the Intune App SDK Microsoft Connect site under the Surveys tab or located here. We will also ask you to provide the name of the app, your company’s name, as well as the Google or iTunes store deep link to your app.

	![Microsoft Connect](../media/microsoft-connect.png)

	We will use your registration email address to confirm and complete receipt of the registration process. Additionally, we use your registration email address to contact you should we have any concerns.

* **What to expect in the registration process**: After you have submitted the form you will be contacted by Microsoft via your registration email address, to either confirm successful receipt or request additional information to complete the registration. You will also be contacted when your app is successfully registered with the Microsoft Intune and when your app is featured on the Microsoft Intune partners’ site. After receipt of the information has been confirmed, your app deep link will be included in the next monthly Intune Service update. For example, if the registration information is completed in July, the app deep link will be supported in mid-August. If your store app deep link changes in the future, you will need to re-register you app. Also, inform us if you update your app with a new version of the Intune App SDK.

	**Note**: All information collected in the form above and through e-mail correspondence with the Intune team will honor the [Microsoft Privacy Statement](https://www.microsoft.com/en-us/privacystatement/default.aspx).

## Download the SDK files

The Intune App SDKs for iOS and Android are hosted on a Microsoft GitHub account. The public repositories below contain the SDK files for iOS and Android, respectively:

* [Intune App SDK for iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Intune App SDK for Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

We recommend signing up for a GitHub account you can use to fork and pull from our repositories. GitHub allows developers to communicate with our product team, open issues and receive quick responses, view release notes, and provide feedback to Microsoft. For questions on the GitHub account and repositories, contact msintuneappsdk@microsoft.com.

## Enable your iOS or Android mobile app for MAM with the SDK

To integrate the Intune App SDK into your iOS app, you will need the following: 

* **[Intune App SDK for iOS Developer Guide](intune-app-sdk-ios.md)**: this document will walk you step-by-step through enabling your mobile iOS app with the Intune App SDK. 


To integrate the Intune App SDK into your Android app, you will need the following:

* **[Intune App SDK for Android Developer Guide](intune-app-sdk-android.md)**: This document will walk you step-by-step through enabling your mobile android app with Intune App SDK. 



## Configuring Telemetry for your app

Microsoft Intune collects data on usage statistics for your app.

* **Intune App SDK for iOS**: The SDK logs SDK telemetry data on usage events by default. This data is sent to Microsoft Intune.

	* If you choose not to send SDK telemetry data to Microsoft Intune from your app, you **must disable** SDK telemetry transmission by setting the property `MAMTelemetryDisabled` to "YES" in the `IntuneMAMSettings`.

* **Intune App SDK for Android**: SDK telemetry data is not logged through the SDK.

## Test your MAM enabled app with Microsoft Intune

Once you’ve completed the necessary steps to integrate your iOS or Android app with the Intune App SDK, you will need to ensure that all the app management policies are enabled and functioning for the end user and the IT administrator. To test your integrated app, you will need the following:

<!--TODO-->

1. **Testing your MAM enabled app with Microsoft Intune**: This document will walk you through step-by-step how to test your MAM-enabled iOS or Android apps with Microsoft Intune. You can find this document in the GitHub repositories of the SDKs.

2. **Microsoft Intune Account**: To test your MAM enabled apps with Microsoft Intune, you will need a Microsoft Intune account. 
	* If you are an ISV enabling your iOS or Android store apps for Intune MAM, you will receive a promo code once you complete the registration with Microsoft Intune as outlined in the registration step. The promo code will allow you to sign up for a Microsoft Intune trial for 1 year of extended use. 
	* If you are developing a line of business app that will not be shipped to the store, you are expected to have access for Microsoft Intune through your organization. You can also sign up for 1-month free trial in with [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).

