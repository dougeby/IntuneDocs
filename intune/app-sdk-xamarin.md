---
# required metadata

title: Microsoft Intune App SDK Xamarin Bindings 
description: The Intune App SDK Xamarin Bindings enable Intune app protection policy in iOS and Android apps built with Xamarin. 
keywords: sdk, Xamarin, intune
author: Erikre
manager: dougeby
ms.author: erikre
ms.date: 06/08/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: aanavath
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Microsoft Intune App SDK Xamarin Bindings

> [!NOTE]
> You may wish to first read the [Get Started with Intune App SDK](app-sdk-get-started.md) article, which explains how to prepare for integration on each supported platform.

## Overview
The [Intune App SDK Xamarin Bindings](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) enable [Intune app protection policy](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) in iOS and Android apps built with Xamarin. The bindings allow developers to easily build in Intune app protection features into their Xamarin-based app.

The Microsoft Intune App SDK Xamarin Bindings let you incorporate Intune app protection policies (also known as APP or MAM policies) into your apps developed with Xamarin. A MAM-enabled application is one that is integrated with the Intune App SDK. IT administrators can deploy app protection policies to your mobile app when Intune actively manages the app.

## What's supported?

### Developer machines
* Windows
* macOS


### Mobile app platforms
* Android
* iOS


### Intune Mobile Application Management scenarios

* Intune APP-WE (without device enrollment)
* Intune MDM-enrolled devices
* Third-party EMM-enrolled devices

Xamarin apps built with the Intune App SDK Xamarin Bindings can now receive Intune app protection policies on both Intune mobile device management (MDM) enrolled devices and unenrolled devices.

## Prerequisites

Review the [license terms](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf). Print and retain a copy of the license terms for your records. By downloading and using the Intune App SDK Xamarin Bindings, you agree to such license terms. If you do not accept them, do not use the software.

## Enabling Intune app protection polices in your iOS mobile app
1. Add the [Microsoft.Intune.MAM.Xamarin.iOS NuGet package](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS) to your Xamarin.iOS project.
2.	Follow the general steps required for integrating the Intune App SDK into an iOS mobile app. You can begin with step 3 of the integration instructions from the [Intune App SDK for iOS Developer Guide](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). You can skip the final step in that section of running the IntuneMAMConfigurator, as this tool is included in the Microsoft.Intune.MAM.Xamarin.iOS package and will be run automatically at build time.
    **Important**: Enabling keychain sharing for an app is slightly different in Visual Studio from Xcode. Open the app's Entitlements plist and make sure the "Enable Keychain" option is enabled and the appropriate keychain sharing groups are added in that section. Then, ensure the Entitlements plist is specified in the "Custom Entitlements" field of the project's "iOS Bundle Signing" options for all the appropriate Configuration/Platform combinations.
3.	Once the bindings are added and the app is properly configured, your app can begin using the Intune SDK's APIs. To do so, you must include the following namespace:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
4. To begin receiving app protection policies, your app must enroll in the Intune MAM service. If your app already uses the Azure Active Directory Authentication Library (ADAL) to authenticate users, your app should provide the user's UPN to the IntuneMAMEnrollmentManager's registerAndEnrollAccount method after it has successfully authenticated:
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      **Important**: Be sure to override the Intune App SDK's default ADAL settings with those of your app. You can do so via the IntuneMAMSettings dictionary in the app's Info.plist, as mentioned in the [Intune App SDK for iOS Developer Guide](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk), or you can use the AAD override properties of the IntuneMAMPolicyManager instance. The Info.plist approach is recommended for applications whose ADAL settings are static while the override properties are recommended for applications that determine those values at runtime. 
      
      If your app does not use ADAL, and you'd like the Intune SDK to handle authentication, your app should call the IntuneMAMEnrollmentManager's loginAndEnrollAccount method:
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```
      
> [!NOTE] 
> There is no remapper for iOS. Integrating into a Xamarin.Forms app should be the same as for a regular Xamarin.iOS project. 

## Enabling Intune app protection policies in your Android mobile app

### Xamarin.Android integration

1. Add the latest version of the [Microsoft.Intune.MAM.Xamarin.Android NuGet package](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) to your Xamarin.Android project. This will provide you with the necessary references to Intune enable your application.

2. Read and follow the [Intune App SDK for Android Developers Guide](app-sdk-android.md) fully, paying special attention to:
    1. The [entire class and method replacements section](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent). 
    2. The [MAMApplication section](app-sdk-android.md#mamapplication). Be sure that your subclass is properly decorated with the `[Application]` attribute and overrides the `(IntPtr, JniHandleOwnership)` constructor.
    3. The [ADAL integration section](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal) if your app performs authentication against AAD.
    4. The [MAM-WE enrollment section](app-sdk-android.md#app-protection-policy-without-device-enrollment) if you plan on obtaining policy from the MAM service in your application.

> [!NOTE]
> When attempting to find equivalent APIs from the [Intune App SDK for Android Developers Guide](app-sdk-android.md) in the `Microsoft.Intune.MAM.Xamarin.Android` Bindings or when converting code snippets from the guide, be aware that Xamarin's bindings generator modifies the Android APIs in the following notable ways:
> * All identifiers are converted to Pascal case (com.foo.bar -> Com.Foo.Bar)
> * All get/set operations are converted to property operations (e.g. Foo.getBar() -> Foo.Bar, Foo.setBar("zap") -> Foo.Bar = "zap")
> * All interfaces have the character 'I' prepended on the name (FooInterface -> IFooInterface)

### Xamarin.Forms integration

**In addition to performing all of the steps above**, for `Xamarin.Forms` applications we have provided the `Microsoft.Intune.MAM.Remapper` package. This package accomplishes class replacement for you by injecting `MAM` classes into the class hierarchy of commonly used `Xamarin.Forms` classes like `FormsAppCompatActivity` and `FormsApplicationActivity` so you can continue to use those classes by providing overrides for the MAM equivalent functions like `OnMAMCreate` and `OnMAMResume`. To use it, do the following:

1.  Add the [Microsoft.Intune.MAM.Remapper.Tasks](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) NuGet package to your project. This will automatically add the Intune APP SDK Xamarin bindings if you have not already included them.

2.  Add a call to `Xamarin.Forms.Forms.Init(Context, Bundle)` in the `OnMAMCreate` function of the `MAMApplication` class you created in step 2.2 above. This is needed because with Intune management your application can be started while in the background.

> [!NOTE]
> Because this operation re-writes a dependency that Visual Studio uses for Intellisense auto-completion, you may need to restart Visual Studio after the first time the remapper runs to get Intellisense to correctly recognize the changes. 


## Support

If your organization is an existing Intune customer, please work with your Microsoft support representative to open a support ticket and create an issue [on the Github issues page](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues) and we will help as soon as we can. 
