---
# required metadata

title: Microsoft Intune App SDK Xamarin Component 
description:
keywords: sdk, Xamarin, intune
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 11/15/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: oydang
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Microsoft Intune App SDK Xamarin Component

> [!NOTE]
> You may wish to first read the [Get Started with Intune App SDK](app-sdk-get-started.md) article, which explains how to prepare for integration on each supported platform.



## Overview
The [Intune App SDK Xamarin component](https://components.xamarin.com/view/microsoft.intune.mam) enables [Intune app protection policy](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) in iOS and Android apps built with Xamarin. The component allows developers to easily build in Intune app protection features into their Xamarin-based app.

The Microsoft Intune App SDK Xamarin Component lets you incorporate Intune app protection policies (also known as APP or MAM policies) into your apps developed with Xamarin. A MAM-enabled application is one that is integrated with the Intune App SDK. IT administrators can deploy app protection policies to your mobile app when Intune actively manages the app.

## What's supported?

### Developer machines
* macOS


### Mobile app platforms
* Android
* iOS


### Intune Mobile Application Management scenarios

* Intune MDM-enrolled devices
* Third-party EMM-enrolled devices
* Unmanaged devices (not enrolled with any MDM)

Xamarin apps built with the Intune App SDK Xamarin Component can now receive Intune app protection policies on both Intune mobile device management (MDM) enrolled devices and unenrolled devices.

## Prerequisites

* **[Android only]** The latest Microsoft Intune Company Portal app must be installed on the device.

## Get started

1.	Download **Xamarin-component.exe** from [here](https://components.xamarin.com/submit/xpkg) and extract it.

2. Read the [license terms](https://components.xamarin.com/license/microsoft.intune.mam) for the Microsoft Intune MAM Xamarin Component.

3.	Download the Intune App SDK Xamarin Component folder from [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) or [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam) and extract it. Both files downloaded from step 1 and step 3 should be in the same directory level.

4.	In the command line as an administrator, run `Xamarin.Component.exe install <.xam> file`.

5.	In Visual Studio, right-click **components** in your previously created Xamarin project.

6.	Select **Edit Components** and add the Intune App SDK component you’ve downloaded locally to your computer.



## Enabling Intune app protection polices in your iOS mobile app
1.	In order to initialize the Intune App SDK, you need to make a call for any API in the `AppDelegate.cs` class. For example:

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.	Now that the component is added and initialized, you can follow the general steps required for building the App SDK into an iOS mobile app. You can find the full documentation for enabling native iOS apps in the [Intune App SDK for iOS Developer Guide](app-sdk-ios.md).
3. **Important**: There are several modifications specific to Xamarin-based iOS apps. For instance, when enabling keychain groups, you need to add the following to include the Xamarin sample app we included in the component. Below is an example of the groups you would need to have in your Keychain Access groups:

      ```xml
      <?xml version="1.0" encoding="UTF-8"?>
      <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
      <plist version="1.0">
            <dict>
                  <key>keychain-access-groups</key>
                  <array>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample</string>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample.intunemam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.intune.mam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.adalcache</string>
                  </array>
            </dict>
      </plist>
      ```

You have completed the steps necessary to build the component into your Xamarin-based iOS app. If you are utilizing Xcode for building your project, you can use the `Intune App SDK Settings.bundle`. This allows you to toggle Intune policy settings on and off as you build your project to test and debug. To take advantage of this bundle, follow the steps in the [Intune App SDK for iOS Developer Guide](app-sdk-ios.md) and read the section on [debugging in Xcode](app-sdk-ios.md#status-result-and-debug-notifications).

## Enabling app protection policies in your Android mobile app
For Xamarin-based Android apps not using a UI framework, you need to read and follow the [Intune App SDK for Android Developer Guide](app-sdk-android.md). For your Xamarin-based Android app, you need to replace class, methods, and activities with their MAM equivalent based on the [table](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) included in the guide. If your app doesn’t define an `android.app.Application` class, you need to create one and ensure that you inherit from `MAMApplication`.

For Xamarin Forms and other UI frameworks, we have provided a tool called `MAM.Remapper`. The tool accomplishes the class replacement for you. However, you need to do the following steps:

1.  Add a reference to the `Microsoft.Intune.MAM.Remapper.Tasks` NuGet package version 0.1.0.0 or greater.

2.  Add the following line to your Android csproj:
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Set the build action of the added `remapping-config.json` file to **RemappingConfigFile**. The included `remapping-config.json` only works with Xamarin.Forms. For other UI frameworks, refer to the Readme included with the Remapper NuGet package.

## Next steps

You have completed the basic steps of building the component into your app. Now you can follow the steps included in the Xamarin Android sample app. We have provided two samples, one for Xamarin.Forms and another for Android.