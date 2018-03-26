---
# required metadata

title: Microsoft Intune App SDK Xamarin Bindings 
description: The Intune App SDK Xamarin Bindings enables Intune app protection policy in iOS and Android apps built with Xamarin. 
keywords: sdk, Xamarin, intune
author: Erikre
manager: dougeby
ms.author: erikre
ms.date: 03/19/2018
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
The [Intune App SDK Xamarin Bindings](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) enables [Intune app protection policy](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) in iOS and Android apps built with Xamarin. The component allows developers to easily build in Intune app protection features into their Xamarin-based app.

The Microsoft Intune App SDK Xamarin Bindings let you incorporate Intune app protection policies (also known as APP or MAM policies) into your apps developed with Xamarin. A MAM-enabled application is one that is integrated with the Intune App SDK. IT administrators can deploy app protection policies to your mobile app when Intune actively manages the app.

## What's supported?

### Developer machines
* Windows
* macOS


### Mobile app platforms
* Android
* iOS


### Intune Mobile Application Management scenarios

* Intune APP-WE (without enrollment)
* Intune MDM-enrolled devices
* Third-party EMM-enrolled devices
* Unmanaged devices (not enrolled with any MDM)

Xamarin apps built with the Intune App SDK Xamarin Bindings can now receive Intune app protection policies on both Intune mobile device management (MDM) enrolled devices and unenrolled devices.

## Get started

1. Read the [license terms](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf) for the Microsoft Intune MAM Xamarin Bindings.

2.	Download the Intune App SDK Xamarin Bindings NuGet packages from [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin). These packages will be available on Nuget.org soon.  

## Enabling Intune app protection polices in your iOS mobile app
1. Add the `Microsoft.Intune.MAM.Xamarin.iOS` NuGet package to your Xamarin.iOS project.
2.	Follow the general steps required for integrating the Intune App SDK into an iOS mobile app. You can begin with step 3 of the integration instructions from the [Intune App SDK for iOS Developer Guide](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). You can skip the final step in that section of running the IntuneMAMConfigurator, as this tool is included in the Microsoft.Intune.MAM.Xamarin.iOS package and will be run automatically at build time.
    **Important**: Enabling keychain sharing for an app is slightly different in Visual Studio from Xcode. Open the app's Entitlements plist and make sure the "Enable Keychain" option is enabled and the appropriate keychain sharing groups are added in that section. Then, ensure the Entitlements plist is specified in the "Custom Entitlements" field of the project's "iOS Bundle Signing" options for all the appropriate Configuration/Platform combinations.
3.	Once the component is added and the app is properly configured, your app can begin using the Intune SDK's APIs. To do so, you must include the following namespace:

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

## Enabling app protection policies in your Android mobile app
Add the [Microsoft.Intune.MAM.Xamarin.Android](**TODO: GET LINK**) NuGet package to your Xamarin.Android project.

For Xamarin.Android apps, you need to read and follow the [Intune App SDK for Android Developer Guide](app-sdk-android.md) fully, including replacing class, methods, and activities with their MAM equivalent based on the [table](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) included in the guide. 

> [!NOTE]
> If your app doesn’t define an `android.app.Application` class, you need to create one and ensure that you inherit from `MAMApplication`.

> [!NOTE]
> When attempting to find equivalent APIs from the [Intune App SDK for Android Developer Guide](app-sdk-android.md) in the `Microsoft.Intune.MAM.Xamarin.Android` Bindings or converting code snippets from the guide, be aware that Xamarin's bindings generator modifies the Android APIs in the following notable ways:
> * All identifiers are converted to Pascale case (com.microsoft.foo -> Com.Microsoft.Foo)
> * All get/set opreations are converted to property operations (e.g. Foo.getBar() -> Foo.Bar, Foo.setBar("zap") -> Foo.Bar = "zap")
> * All interfaces have the character 'I' prepended on the name (FooInterface -> IFooInterface)

For apps utilizing Xamarin.Forms or other UI frameworks, we have provided a tool called `Microsoft.Intune.MAM.Remapper`. The tool accomplishes the class replacement for you. To use it, do the following:

1.  Add the [Microsoft.Intune.MAM.Remapper.Tasks](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks/) NuGet package to your project.

2.  Set the build action of the `remapping-config.json` file that's included with the Nuget package to **RemappingConfigFile**. The included `remapping-config.json` only works with Xamarin.Forms. For other UI frameworks, refer to the Readme included with the Remapper NuGet package.

3.  Perform the rest of the steps in [Intune App SDK for Android Developer Guide](app-sdk-android.md) that are applicable to your app.

> [!NOTE]
> The build action of remapping-config.json can sometimes be reset when updating the Microsoft.Intune.MAM.Remapper.Tasks package which would cause your builds to fail.

## Next steps

You have completed the basic steps of setting your app up for Intune management. Now you can follow the steps included in the integration guides for each of platforms listed above. We have provided three sample applications, one for Xamarin.Forms with Android and iOS sub projects, another for iOS and another for Android. You can find them here: **TODO**
