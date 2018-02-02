---
# required metadata

title: Microsoft Intune App SDK Cordova Plugin 
description:
keywords: sdk, Cordova, intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/02/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: aanavath
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---
# Microsoft Intune App SDK Cordova Plugin

> [!IMPORTANT]
> Intune is ending support for the Microsoft Intune App SDK Cordova Plugin on May 1, 2018. We recommend that you use the Intune App Wrapping Tool instead. For more information about the App Wrapping Tool, see [App Wrapping Tool for iOS](app-wrapper-prepare-ios.md) and [App Wrapping Tool for Android](app-wrapper-prepare-android.md). For more information about this change, see the [Notices](whats-new.md#notices) section of [What's new in Microsoft Intune](whats-new.md).

## Overview

The [Intune App SDK Cordova Plugin](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) in iOS and Android apps built with Cordova. The plugin allows developers to integrate Intune app and data protection features into their Cordova-based app.

> [!NOTE]
> You may wish to first read the [Get Started with Intune App SDK](app-sdk-get-started.md) article, which explains how to prepare for integration on each supported platform.

You will find that you can enable SDK features without changing your app's behavior. Once you have built the plugin into your iOS or Android app, the Microsoft Intune administrator will be able to deploy Intune app protection policy, which consists of a variety of data protection features. The plugin is built so that most of the steps are automatically performed in the Cordova build process. As a result, you should be able to get your app enabled for Intune app protection quickly. To get started, follow the steps below based on your target platform.

## Supported Platforms

* The plugin works on Windows, Mac and Linux OS
* The plugin works for Android apps with `minSdkVersion` >= 14 and `targetSdkVersion` <= 24
* The plugin works for iOS apps targeted for iOS 9.0 and above.

## Intune Mobile Application Management scenarios

* Intune MDM-enrolled devices
* Third-party EMM-enrolled devices
* Unmanaged devices (not enrolled with any MDM)

Cordova apps built with the Intune App SDK Cordova Plugin can now receive Intune app protection policies on both Intune mobile device management (MDM) enrolled devices and unenrolled devices.

## Prerequisites

### Android

* The latest Microsoft Intune Company Portal app must always be installed on the device.
* Java 7 at minimum must be on the path where you will execute Cordova build when using the plugin.

### iOS

* The latest Microsoft Intune Company Portal app must be installed on the device for MDM features. It is *not* needed for Intune app protection policy without device enrollment features.

### Both platforms

* Version 0.8.0+ of the [Azure Active Directory Authentication Libraries (ADAL) plugin for Cordova](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) is required.

> [!NOTE]
> Due to an Apache Cordova bug the filed [here](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22), apps that already have the plugin dependency will not automatically upgrade the plugin to the requested version.



## Quick start

1. Update your version of ADAL:

  ```shell
  cordova plugin remove cordova-plugin-ms-adal
  cordova plugin add cordova-plugin-ms-adal@0.8.x
  ```

2. Add the Intune App SDK for Cordova plugin:

  ```shell
  cordova plugin add cordova-plugin-ms-intune-mam
  ```

## Build the plugin into your iOS app

You'll need to complete some steps for your app to be enabled for Intune app protection policy. For convenience, these steps are performed automatically in the Cordova build process as a pre-build hook. As a result, the automated steps will modify your `*.pbxproj` , `*-Info.plist`, and `*.entitlements` files that are associated with a project configuration. If your project doesn't contain an entitlements file, the plugin will create one automatically.

This setup only supports a single target and will perform the configuration on the first target found if there are multiple targets. If the process fails, check that:

1. Your app's Xcode project is `[name].xcodeproj` where `[name]` is the value defined in `config.xml`
2. Your project uses the [standard Cordova app directory structure](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure).

## Build the plugin into your Android app

1. Import this plugin with the latest Cordova tools. The plugin will be automatically invoked as an `after_compile` step.

2. The plugin will create a Intune-enabled version of a built apk (Android API 14+) at the end of the build process. The build output will contain a `[Project]-intunewrapped-[Build_Configuration].apk` (e.g. `helloWorld-intunewrapped-debug.apk`).

> [!NOTE]
> The plugin only supports gradle builds.

Due to a Cordova bug filed [here](https://issues.apache.org/jira/browse/CB-9434) that causes certain Cordova hooks to be ignored on `cordova run`, to run the wrapped app from the command line, you must do the following:

```shell
$ cordova build
$ cordova run --nobuild
```

## Sign your Android app

The plugin automatically recognizes signing information you have provided to Cordova at the following locations:

* platforms/android/debug-signing.properties
* platforms/android/release-signing.properties
* res/native/android/ant.properties

See [the Cordova gradle signing information](https://cordova.apache.org/docs/en/latest/guide/platforms/android/#using-gradle) for more information about the expected format.

We currently don't support the ability to provide signing information in `build.json` or arbitrary locations provided via parameters to Cordova build.

## Debugging from Visual Studio

After launching the app for the first time you should see a dialog notifying you that the app is managed by Intune. Hit "Don't show again" and click the debug/run button again from VS for breakpoints to be hit.

## Known Limitations

### Android

* MultiDex support is incomplete.
* App must have `minSdkVersion` of 14 and `targetSdkVersion` of 24 or below. We currently don't support apps targeting API 25
* We cannot re-sign apps that were signed with the V2 Signature Scheme. When V2-signed apps are wrapped by the plugin, the wrapped output .apk will be unsigned.
*
  * You can disable Cordova's default V2 Signing by adding the following to your `build-extras.gradle` file:

  ```gradle
  android {
      signingConfigs {
          release {
              v2SigningEnabled false
          }
          debug {
              v2SigningEnabled false
          }
      }
      buildTypes {
          release {
              signingConfig signingConfigs.release
          }
          debug {
              signingConfig signingConfigs.debug
          }
      }
  }
  ```

### iOS

* Whenever you modify the list of UTI's under the **CFBundleDocumentTypes** node of the **Info.plist** file, you must clear the Intune UTI's in the Imported UTI's section of the same plist file (**UTImportedTypeDeclarations** node) before building again. All of the Intune UTI's will start with the prefix `com.microsoft.intune.mam`.

* If you want to remove the Intune App SDK for Cordova plugin from your Cordova project, you must also remove the iOS platform and re-add it, in order to undo some of the Intune configuration in the .xcodeproj and .plist files.
