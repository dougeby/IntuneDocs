---
title: Getting Started With the Microsoft Intune App SDK
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
author: Msmbaldwin
---
# Getting Started With the Microsoft Intune App SDK
This Getting Started guide will help you quickly enable your mobile app for Mobile Application Management with Microsoft Intune. You may find it useful to first understand the benefits of the Intune App SDK as enumerated in the [Overview](Overview_of_the_Microsoft_Intune_App_SDK.md).

This guide walks through the major steps needed to enable mobile app management in your app with Microsoft Intune. The Intune App SDK supports similar scenarios across platforms, and is intended to create a consistent experience across the platforms for IT administrators. However, there are small differences in the support of certain features due to platform limitations.

# Getting Started

## Register for Microsoft Connect

The Intune App SDK is currently accessible via Microsoft Connect and requires sign up. To do so, register for a [Microsoft Account](https://connect.microsoft.com/ConfigurationManagervnext/InvitationUse.aspx?ProgramID=8967&InvitationID=8967-YJYJ-8G6X) using your corporate e-mail.

Your registration will be in pending status until the Intune team reviews your request. The typical response time is within 2 - 3 business days. Once approved, you will receive an email notification with the link(s) to download the Intune App SDK for your platform(s) and all related guides. You may also access these guides on the MSDN site.

## Register your store app with Microsoft Intune

**If your enabled app is internal to your company and will not be made available in the Apple or Google app store**: You do not need to register your app. For such internal apps, the IT administrator will load them directly into the Microsoft Intune console for deployment, Intune will detect that the app has been built with the SDK, and will present the IT administrator with the option of applying MAM policy to it. You can skip to the section titled [Enable your iOS or Android mobile app for MAM with the SDK](#enableapp).

**If you are an ISV developing an app that will be made available to customers through either Apple or Google app stores**: You must first register your app with Microsoft Intune and agree to the registration terms. You can supply the app’s deep link at this time. Afterward an IT administrator can apply Intune MAM policy to the app. Until registration has been complete and confirmed by the Microsoft Intune team, your app deep link will not be given the option to apply MAM policy in the admin console. Microsoft also maintains a Microsoft Intune Partners web site where the app will be registered so that customers will know that it supports Microsoft Intune MAM policy.

To begin the registration process, **review and sign** the [Microsoft Intune Partner Agreement](https://connect.microsoft.com/ConfigurationManagervnext/Survey/Survey.aspx?SurveyID=17806). This agreement describes the terms your company must accept before becoming a Microsoft Intune app partner. You will need to sign in before you can view this document. You can find the agreement in the Intune App SDK Microsoft Connect site under the Surveys tab or located here. We will also ask you to provide the name of the app, your company’s name, as well as the Google or iTunes store deep link to your app.

![Microsoft Connect](/Image/Microsoft_Connect.png)

We will use your registration email address to confirm and complete receipt of the registration process. Additionally, we use your registration email address to contact you should we have any concerns.

**What to expect in the registration process**: After you have submitted the form you will be contacted by Microsoft via your registration email address, to either confirm successful receipt or request additional information to complete the registration. You will also be contacted when your app is successfully registered with the Microsoft Intune and when your app is featured on the Microsoft Intune partners’ site. After receipt of the information has been confirmed, your app deep link will be included in the next monthly Intune Service update. For example, if the registration information is completed in July, the app deep link will be supported in mid-August. If your store app deep link changes in the future, you will need to re-register you app. Also, inform us if you update your app with a new version of the Intune App SDK.

**Note**: All information collected in the form above and through e-mail correspondence with the Intune team will honor the [Microsoft Privacy Statement](https://www.microsoft.com/en-us/privacystatement/default.aspx).

## <a name="enableapp"></a> Enable your iOS or Android mobile app for MAM with the SDK

To enable your iOS mobile app, you will need the following:

1. **[Intune App SDK for iOS Developer Guide](Microsoft_Intune_App_SDK_for_iOS_Developer_Guide.md)**: this document will walk you step-by-step through enabling your mobile iOS app with the Intune App SDK. You can find this document in the documentation folder that you have downloaded as part of the Intune App SDK package.
2. **Intune App SDK for iOS**: as part of the Intune App SDK package downloaded from Microsoft Intune, you will find a signed folder “Intune App SDK for iOS.” This folder has all the Intune App SDK for iOS content.

To enable your android mobile app with Intune App SDK, you will need the following:

1. **[Intune App SDK for Android Developer Guide](Microsoft_Intune_App_SDK_for_Android_Developer_Guide.md)**: This document will walk you step-by-step through enabling your mobile android app with Intune App SDK. You can find this document in the documentation folder that you have downloaded as part of the Intune App SDK package.
2. **Intune App SDK for Android**: As part of the Intune App SDK package downloaded from Microsoft Intune, you will find a signed folder “Intune App SDK for Android.” This folder has all the Intune App SDK for android content.

## Turning off Telemetry for your app

**Intune App SDK for iOS**: The SDK logs SDK telemetry data on usage events by default. This data is sent to Microsoft Intune.

If you choose not to send SDK telemetry data to Microsoft Intune from your application, you **must disable** SDK telemetry transmission by setting the property `MAMTelemetryDisabled` to ‘YES’ in the `IntuneMAMSettings`.

**Intune App SDK for Android**: SDK telemetry data is not logged through the SDK.

## Test your MAM enabled app with Microsoft Intune

Once you’ve completed the necessary steps to enlighten (integrate the Intune App SDK) your iOS or Android Intune App SDK, you will need to ensure that all the app management policies are enabled and functioning for the end user and the IT administrator. To test your enlightened app, you will need the following:

1. **Testing your MAM enabled app with Microsoft Intune**: This document will walk you through step-by-step how to test your MAM-enabled iOS or android apps with Microsoft Intune. You can find this document in the documentation folder that you have downloaded as part of the Intune App SDK package.
2. **Microsoft Intune Account**: To test your MAM enabled apps with Microsoft Intune, you will need a Microsoft Intune account. If you are an ISV enabling your iOS or android store apps for MAM, you will receive a promo code once you complete the registration with Microsoft Intune as outlined in the registration step. The promo code will allow you to sign up for a Microsoft Intune trial for 1 year of extended use. If you are developing a line of business app that will not be shipped to the store, you are expected to have access for Microsoft Intune through your organization. You can also sign up for 1-month free trial in with [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).

