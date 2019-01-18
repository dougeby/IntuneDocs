---
# required metadata

title: Microsoft Intune App SDK Xamarin Bindings 
description: The Intune App SDK Xamarin Bindings enable Intune app protection policy in iOS and Android apps built with Xamarin. 
keywords: sdk, Xamarin, intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/16/2018
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
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune

---

# Microsoft Intune App SDK Xamarin Bindings

> [!NOTE]
> You may wish to first read the [Get Started with Intune App SDK](app-sdk-get-started.md) article, which explains how to prepare for integration on each supported platform.

## Overview
The [Intune App SDK Xamarin Bindings](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) enable [Intune app protection policy](app-protection-policy.md) in iOS and Android apps built with Xamarin. The bindings allow developers to easily build in Intune app protection features into their Xamarin-based app.

The Microsoft Intune App SDK Xamarin Bindings let you incorporate Intune app protection policies (also known as APP or MAM policies) into your apps developed with Xamarin. A MAM-enabled application is one that is integrated with the Intune App SDK. IT administrators can deploy app protection policies to your mobile app when Intune actively manages the app.

## What's supported?

### Developer machines
* Windows (Visual Studio version 15.7+)
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

The SDK relies on [Active Directory Authentication Library (ADAL)](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) for its [authentication](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) and conditional launch scenarios, which require apps to be configured with [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). 

If your application is already configured to use ADAL or MSAL, and has its own custom client ID used to authenticate with Azure Active Directory, ensure the steps to give your Xamarin app permissions to the Intune Mobile Application Management (MAM) service are followed. Use the instructions in the "[Give your app access to the Intune app protection service](app-sdk-get-started.md#give-your-app-access-to-the-intune-app-protection-service-optional)" section of the [getting started with the Intune SDK guide](app-sdk-get-started.md).

## Enabling Intune app protection polices in your iOS mobile app
1. Add the [Microsoft.Intune.MAM.Xamarin.iOS NuGet package](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS) to your Xamarin.iOS project.
2.	Follow the general steps required for integrating the Intune App SDK into an iOS mobile app. You can begin with step 3 of the integration instructions from the [Intune App SDK for iOS Developer Guide](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). You can skip the final step in that section of running the IntuneMAMConfigurator, as this tool is included in the Microsoft.Intune.MAM.Xamarin.iOS package and will be run automatically at build time.
    **Important**: Enabling keychain sharing for an app is slightly different in Visual Studio from Xcode. Open the app's Entitlements plist and make sure the "Enable Keychain" option is enabled and the appropriate keychain sharing groups are added in that section. Then, ensure the Entitlements plist is specified in the "Custom Entitlements" field of the project's "iOS Bundle Signing" options for all the appropriate Configuration/Platform combinations.
3.	Once the bindings are added and the app is properly configured, your app can begin using the Intune SDK's APIs. To do so, you must include the following namespace:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
4. To begin receiving app protection policies, your app must enroll in the Intune MAM service. If your app does not use the [Azure Active Directory Authentication Library](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory) (ADAL) or the [Microsoft Authentication Library](https://www.nuget.org/packages/Microsoft.Identity.Client) (MSAL) to authenticate users, and you'd like the Intune SDK to handle authentication, your app should provide the user's UPN to the IntuneMAMEnrollmentManager's LoginAndEnrollAccount method:
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```
      Apps may pass in null if the user's UPN is unknown at the time of the call. In this case, users will be prompted to enter both their email address and password.
      
      If your app already uses ADAL or MSAL to authenticate users, you can configure a single-sign-on (SSO) experience between your app and the Intune SDK. First, you'll need to configure ADAL/MSAL to store tokens in the same keychain access group used by the Intune Xamarin Bindings for iOS (com.microsoft.adalcache). For ADAL, you can do this by [setting the KeychainSecurityGroup property of AuthenticationContext](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet/wiki/Token-cache-serialization#enable-token-cache-sharing-across-ios-applications). For MSAL, you'll need to [set the KeychainSecurityGroup property of PublicClientApplication](https://github.com/AzureAD/microsoft-authentication-library-for-dotnet/wiki/msal-net-2-released#you-can-now-enable-sso-between-adal-and-msal-apps-on-xamarinios). Next, you'll need to override the default AAD settings used by the Intune SDK with those of your app. You can do so via the IntuneMAMSettings dictionary in the app's Info.plist, as mentioned in the [Intune App SDK for iOS Developer Guide](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk), or you can use the AAD override properties of the IntuneMAMPolicyManager instance. The Info.plist approach is recommended for applications whose ADAL settings are static while the override properties are recommended for applications that determine those values at runtime. Once all of the SSO settings have been configured, your app should provide the user's UPN to the IntuneMAMEnrollmentManager's RegisterAndEnrollAccount method after it has successfully authenticated:
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      Apps can determine the result of an enrollment attempt by implementing the EnrollmentRequestWithStatus method in a subclass of IntuneMAMEnrollmentDelegate and setting the IntuneMAMEnrollmentManager's Delegate property to an instance of that class. Please refer to our [sample Xamarin.iOS application](https://github.com/msintuneappsdk/sample-intune-xamarin-ios) for an example.

      Upon a successful enrollment, apps can determine the UPN of the enrolled account (if previously unknown) by querying the following property: 
      ```csharp
       string enrolledAccount = IntuneMAMEnrollmentManager.Instance.EnrolledAccount;
      ```      
> [!NOTE] 
> There is no remapper for iOS. Integrating into a Xamarin.Forms app should be the same as for a regular Xamarin.iOS project. 

## Enabling Intune app protection policies in your Android mobile app

1. Add the [Microsoft.Intune.MAM.Xamarin.Android NuGet package](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) to your Xamarin.Android project.
2. Follow the general steps required for integrating the Intune App SDK into an Android mobile app while referring to this document for additional details.

### Xamarin.Android integration

A complete overview for integrating the Intune App SDK can be found in the [Microsoft Intune App SDK for Android developer guide](app-sdk-android.md). As you read through the guide and integrate the Intune App SDK with your Xamarin.Android app the following sections are intended to highlight differences between the implementation for a native Android app developed in Java and a Xamarin.Android app developed in C#. These sections should be treated as supplemental and cannot act as a substitute for reading the guide in its entirety.

#### Renamed Methods
In many cases, a method available in the Android class has been marked as final in the MAM replacement class. In this case, the MAM replacement class provides a similarly named method (suffixed with `MAM`) that you should override instead. For example, when deriving from `MAMActivity`, instead of overriding `OnCreate()` and calling `base.OnCreate()`, `Activity` must override `OnMAMCreate()` and call `base.OnMAMCreate()`.

#### MAM Application
Your app must define an `Android.App.Application` class that inherits from `MAMApplication`. Be sure that your subclass is properly decorated with the `[Application]` attribute and overrides the `(IntPtr, JniHandleOwnership)` constructor.
```csharp
    [Application]
    class TaskrApp : MAMApplication
    {
    public TaskrApp(IntPtr handle, JniHandleOwnership transfer)
        : base(handle, transfer) { }
```

### Xamarin.Forms integration

For `Xamarin.Forms` applications we have provided the `Microsoft.Intune.MAM.Remapper` package to perform MAM class replacement automatically by injecting `MAM` classes into the class hierarchy of commonly used `Xamarin.Forms` classes. 

For example, `FormsAppCompatActivity` and `FormsApplicationActivity` can continue to be used in your application provided overrides to `OnCreate` and `OnResume` are replaced with the MAM equivalents `OnMAMCreate` and `OnMAMResume` respectively.

```csharp
    public class MainActivity : global::Xamarin.Forms.Platform.Android.FormsAppCompatActivity
    {
        protected override void OnMAMCreate(Bundle savedInstanceState)
        {
            base.OnMAMCreate(savedInstanceState);
            global::Xamarin.Forms.Forms.Init(this, savedInstanceState);
            LoadApplication(new App());
        }
```

1.  Add the [Microsoft.Intune.MAM.Remapper.Tasks](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) NuGet package to your project. This will automatically add the Intune APP SDK Xamarin bindings if you have not already included them.

> [!NOTE]
> The Remapper re-writes a dependency that Visual Studio uses for IntelliSense auto-completion. Therefore, you may need to restart Visual Studio when the Remapper is added to the project for IntelliSense to correctly recognize the changes.

## Potential Compilation Errors
These are some of the most commonly seen compilation errors when developing a Xamarin based application.

* [Compiler Error CS0239](https://docs.microsoft.com/en-us/dotnet/csharp/misc/cs0239): This error is commonly seen in this form
``'MainActivity.OnCreate(Bundle)': cannot override inherited member 'MAMAppCompatActivityBase.OnCreate(Bundle)' because it is sealed``.
When the remapper modifies the inheritance of Xamarin classes, some functions will be made `sealed` and a new MAM variant is added to override instead. Simply rename you overrides as described [here](https://docs.microsoft.com/en-us/intune/app-sdk-android#renamed-methods). For instance `MainActivity.OnCreate()` would be renamed to `MainActivity.OnMAMCreate()`

* [Compiler Error CS0507](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/compiler-messages/cs0507): This error is commonly seen in this form ``'MyActivity.OnRequestPermissionsResult()' cannot change access modifiers when overriding 'public' inherited member ...``. As the remapper tool changes the inheritance of some of the Xamarin classes, some of the member functions will be changed to `public`. If you override any of these functions, you may need to change those overrides to be `public` as well.

## Support
If your organization is an existing Intune customer, please work with your Microsoft support representative to open a support ticket and create an issue [on the Github issues page](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues) and we will help as soon as we can. 
