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

For Xamarin-based Android apps not using a UI framework, you need to read and follow the [Intune App SDK for Android Developer Guide](app-sdk-android.md). For your Xamarin-based Android app, you need to replace class, methods, and activities with their MAM equivalent based on the [class and method replacements table](app-sdk-android.md#class-and-method-replacements) included in the guide. If your app doesn’t define an `android.app.Application` class, you need to create one and ensure that you inherit from `MAMApplication`. The ADAL configuration values are communicated to the SDK via AndroidManifest metadata. Read our documentation on [configuring ADAL for your app](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal).

### Xamarin.Android integration

1. Add the latest version of the [Microsoft.Intune.MAM.Xamarin.Android NuGet package](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) to your Xamarin.Android project. This will provide you with the necessary references to Intune enable your application.

2. Read and follow the [Intune App SDK for Android Developers Guide](app-sdk-android.md) fully, paying special attention to:

    1. The [entire class and method replacements section](app-sdk-android.md#class-and-method-replacements). 
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

2.  Add a call to `Xamarin.Forms.Forms.Init(Context, Bundle)` in the `OnMAMActivity` function of the `MAMApplication` class you created in step 2.2 above. This is needed because with Intune management your application can be started while in the background.

> [!NOTE]
> Because this operation re-writes a dependency that Visual Studio uses for Intellisense auto-completion, you may need to restart Visual Studio after the first time the remapper runs to get Intellisense to correctly recognize the changes. 

## Requiring Intune app protection policies in order to use your Xamarin-based Android LOB app (optional) 

The following is guidance for ensuring Xamarin-based Android LOB apps can be used only by Intune protected users on their device. 

### General Requirements
* Ensure the steps to give your Xamarin app permissions to the app protection policy (APP) service are followed. Use the instructions in the [getting started with the Intune SDK guide](app-sdk-get-started.md#next-steps-after-integration) under "Give your app access to the Intune app protection service (optional)". 
	
### Working with the Intune SDK
These instructions are specific to all Android and Xamarin apps who wish to require Intune app protection policies for use on a end user device.

1. Configure ADAL using the steps defined in the [Intune SDK for Android guide](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal).
> [!NOTE] 
> The term "client id" is the same as the term "application id" from the Azure Portal tied to your app. 
* To enable SSO, "Common ADAL configuration" #2 is what is needed.

2. Enable default enrollment by putting the following value in the manifest:
```xml <meta-data android:name="com.microsoft.intune.mam.DefaultMAMServiceEnrollment" android:value="true" />```
> [!NOTE] 
> This must be the only MAM-WE integration in the app. If there are any other attempts to call MAMEnrollmentManager APIs, conflicts can arise.

3. Enable MAM policy required by putting the following value in the manifest:
```xml <meta-data android:name="com.microsoft.intune.mam.MAMPolicyRequired" android:value="true" />```
> [!NOTE] 
> This forces apps to download the Company Portal on the device and complete the default enrollment flow before use.

### Working with ADAL
These instructions are a requirement for .NET/Xamarin apps who wish to require Intune app protection policies for use on a end user device.

1. Follow all the steps defined in the ADAL documentation under [Brokered Authentication for Android](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet/tree/dev/adal#brokered-authentication-for-android).

## Potential Compilation Errors
These are some of the most commonly seen compilation errors when developing a Xamarin based application.

* [Compiler Error CS0239](https://docs.microsoft.com/en-us/dotnet/csharp/misc/cs0239): ``'member' : cannot override inherited member 'inherited member' because it is sealed``
* [Compiler Error CS0507](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/compiler-messages/cs0507): ``'function1' : cannot change access modifiers when overriding 'access' inherited member 'function2'``

## Support
If your organization is an existing Intune customer, please work with your Microsoft support representative to open a support ticket and create an issue [on the Github issues page](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues) and we will help as soon as we can. 
