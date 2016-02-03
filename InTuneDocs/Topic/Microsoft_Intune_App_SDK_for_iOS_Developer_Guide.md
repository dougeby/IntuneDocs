---
title: Microsoft Intune App SDK for iOS Developer Guide
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
author: Msmbaldwin
---
# Microsoft Intune App SDK for iOS Developer Guide
***Note**:  You may wish to first read the [Get Started with Intune App SDK Guide](Getting_Started_and_FAQ.md), which explains how to prepare for integration on each supported platform.* 

The Microsoft Intune App SDK for iOS allows you to incorporate Intune Mobile App Management (MAM) into your iOS app. A MAM-enabled application is one integrated with the Intune App SDK, and allows IT administrators to deploy policies to your mobile app when the app is actively managed.

# What’s in the SDK

The Intune App SDK for iOS includes a static library, resource files, API headers, a Debug settings plist and a configurator tool. Mobile apps may simply include the resource files and statically link to the libraries for most policy enforcement. Advanced Intune MAM features are enforced through APIs.
This guide will cover the using the following when integrating the Intune App SDK for iOS:

* **`libIntuneMAM.a`**: The Intune App SDK library. Link this library to your project to make your mobile app MAM-enabled. Instructions are found in the “Building your app with Intune App SDK” section here.

* **`IntuneMAMResources.Bundle`**: A resource bundle that contains resources the SDK relies on. 

* **Headers**: Exposes the Intune App SDK APIs. If you use an API, you will need to include the header file that contains the API. 

# How the Intune App SDK works

The objective of the Intune App SDK for iOS is to add management capabilities to iOS applications with minimal code changes. Reducing the amount of code changes decreases the time to market, while increasing the consistency and stability of your mobile application. 

The application needs to be linked to the static library and include the resource bundle. The MAMDebugSettings.plist file is optional and can be included in the package to simulate MAM policies being applied to the application without needing to deploy the application via Microsoft Intune. Additionally in debug builds, the policies in the MAMDebugSettings.plist file can be applied by transferring the MAMDebugSettings.plist file to the application’s Documents directory via iTunes file sharing.

# Building your app with Intune App SDK 

Complete the steps below to enable the Intune App SDK:

1. Link to the `libIntuneMAM.a` library by doing the following:

    Drag and drop the libIntuneMAM.a library to the “Linked Frameworks and Libraries” list of the project target.  

    ![Intune App SDK iOS - linked frameworks and libraries](/Image/Intune_App_SDK_iOS_-_linked_frameworks_and_libraries.png)
 
    **Note**: When releasing to the app store, please use the version of libIntuneMAM.a that is built for release and not the debug version. The release version will be in the “release” folder. The debug version has verbose output which is good for debugging issues with the Intune App SDK.

2. Add the following iOS frameworks to the project (if missing).
    * `MessageUI.framework`
    * `Security.framework`
    * `MobileCoreServices.framework`
    * `SystemConfiguration.framework`
    * `libsqlite3.dylib`
    * `libc++.dylib`
    * `ImageIO.framework`
    * `LocalAuthentication.Framework`
    * `AudioToolbox.framework`<br>

    **Note**: If the application is targeted for iOS7, set the ‘Status’ attribute of `LocalAuthentication.Framework` to "Optional". 

    If ‘Status’ is not set, the application will fail to launch on iOS7.

    **Note**: Xcode 7 has switched `.dylib` extensions to `.tbd`.

3. Add the `IntuneMAMResources.bundle` resource bundle to the project by dragging the resource bundle under “Copy Bundle Resources” within “Build Phases”. 

    ![Intune App SDK iOS - copy bundle resources](/Image/Intune_App_SDK_iOS_-_copy_bundle_resources.png)

4. Add `-force_load {PATH_TO_LIB}/libIntuneMAM.a` to either of the following, replacing `{PATH_TO_LIB}` with the Intune App SDK location:
    * the project’s OTHER_LDFLAGS build configuration setting 
    * the UI’s “Other Linker Flags”<br>

    **Note**: To find the `PATH_TO_LIB`, select the file `libIntuneMAM.a` and choose ‘Get Info’ from the ‘File’ menu. Copy and paste the ‘Where’ information (the path) from the ‘General’ section of the ‘Info’ window.

5. If your mobile app defines a main Nib or Storyboard in its `info.plist`, remove the Main Storyboard or Main Nib file fields. Add the Storyboard or Nib values you removed previously under a new dictionary named `IntuneMAMSettings` with the following key names, as applicable:
    * `MainStoryboardFile`
    * `MainStoryboardFile~ipad`
    * `MainNibFile`
    * `MainNibFile~ipad `
    
    If your mobile app doesn’t define a main Nib or Storyboard in its `info.plist`, these settings are **not required**. 

    **Note**: You can view the `info.plist` in raw format (in order to see the key names) by right-clicking anywhere in the document body and changing the view type to “Show Raw Keys/Values”.

6. Enable keychain sharing (if not already enabled) by clicking ‘Capabilities’ in each project target and enabling the Keychain Sharing switch. Keychain sharing is required to proceed to the next step.

    **Note**: Your provisioning profile needs to support new keychain sharing values. The keychain access groups should support a wildcard character. You can verify this by opening the `.mobileprovision` file in a text editor, searching for 'keychain-access-groups' and ensuring  you have a wild card, e.g.: 

       <key>keychain-access-groups</key>
       <array>
       <string>YOURBUNDLESEEDID.*</string>
       </array>

7. After enabling keychain sharing, follow these steps to create a separate access group in which the Intune App SDK data will be stored. You can create a keychain access group by using the UI or by using the entitlements file:

    Using the UI to create a keychain access group: 
    
    * If your mobile app does not have any keychain access groups defined, add the app’s bundle id as the first group.
    * Add the shared keychain group com.microsoft.intune.mam. This access group is used by the Intune App SDK to store data.  
    * Add the `com.microsoft.adalcache` to your existing access groups. 
 
    ![Intune App SDK iOS - keychain sharing](/Image/Intune_App_SDK_iOS_-_keychain_sharing.png)

    If you are using the entitlement file to create the keychain access group, rather than the regular UI, you will need to prepend the key chain access group with `$(AppIdentifierPrefix)` in the entitlement file. For example: `$(AppIdentifierPrefix)com.microsoft.intune.mam` and `$(AppIdentifierPrefix)com.microsoft.adalcache`.

    **Note**: An entitlements file is an XML file unique to your mobile application that is used to specify special permissions and capabilities within your iOS app.

8. For mobile apps being developed for iOS 9+, you are required to include each protocol your mobile app passes to `UIApplication canOpenURL` in the `LSApplicationQueriesSchemes` array of your mobile app's `info.plist` file. Additionally, for each protocol listed, a new protocol needs to be added and appended with `-intunemam`. You must also include `http-intunemam`, `https-intunemam`, and `ms-outlook-intunemam` in the array. 

9. If the app defines URL schemes in its `info.plist file`, add another scheme, with a `-intunemam` suffix, for each URL scheme.

10. If the app has app groups defined in its entitlements, add these groups to the `IntuneMAMSettings` dictionary under the `AppGroupIdentitifiers` key as an array of strings.

11. Link your mobile application to the ADAL library. The ADAL library for Objective C is [available on Github]( https://github.com/AzureAD/azure-activedirectory-library-for-objc).

    **Note**: The Intune App SDK has been tested against the ADAL broker branch code from 6/19/2015. Please ensure that you are linking with the latest/working version of the ADAL library.

12. Include the `ADALiOSBundle.bundle resource` bundle in the project by dragging the resource bundle under “Copy Bundle Resources” within “Build Phases”.

13. Use the `-force_load PATH_TO_ADAL_LIBRARY` linker option when linking to the library.

    Add `-force_load {PATH_TO_LIB}/libADALiOS.a` to the project’s OTHER_LDFLAGS build configuration setting or “Other Linker Flags” in the UI. “PATH_TO_LIB” should be replaced with the ADAL binaries location. 

If your mobile application uses ADAL for its own authentication, please review the section on “Configuring Azure Directory Authentication Library Settings” located here.

## Telemetry 

The Intune App SDK for iOS logs telemetry data on usage events by default which is sent to Microsoft Intune.

Data is logged on the following usage events: 

1. App launch to help Microsoft Intune learn about MAM-enabled app usage by management type.

2. EnrollApplication API call to help Microsoft Intune learn about success rate and various other performance metrics of enrollApplication call from the client side.

**Note**: If you choose not to send Intune App SDK telemetry data to Microsoft Intune from your mobile application, you **must disable** Intune App SDK telemetry capture by setting the property `MAMTelemetryDisabled` to ‘YES’ in the `IntuneMAMSettings`.

## Configuring Azure Directory Authentication Library (ADAL) Settings (optional)

The Intune App SDK uses ADAL for its authentication and conditional launch scenario. Typically, ADAL requires apps to register and obtain a unique ID, known as `ClientID`, and other identifiers, to guarantee the security of the tokens granted to the app. The Intune App SDK uses default registration values when contacting Azure Active Directory.  If the app itself uses ADAL for its authentication scenario, the app must use its existing registration values and override the Intune App SDK default to ensure that end users are not prompted for authentication twice (once by the Intune App SDK and once by the app). 

The following steps below are required if the app itself utilizes ADAL for authentication. If your mobile app does not rely on ADAL, no further action is needed. 

1. In the project’s `Info.plist`, under an `IntuneMAMSettings` dictionary with the key name `ADALClientId`, specify the `ClientID` to be used for ADAL calls. 

2. In the project’s `Info.plist`, under the `IntuneMAMSettings` dictionary with the key name `ADALRedirectUri`, specify the Redirect URI to be used for ADAL calls. You may also need to specify the `ADALRedirectScheme` depending on the format of your app’s Redirect URI.

## Building Your Extensions (optional) 

When building extensions, follow the same instructions to build your mobile app as outlined in the section on “Building Your App with Intune App SDK” located here. In addition, update each extension’s info.plist file to add a ContainingAppBundleId key under the IntuneMAMSettings dictionary with the value of the containing application’s bundle id.

## Building Your Frameworks (optional)

With the latest changes to the Intune App SDK, you do not have to compile your mobile app with any specific linker flags if your mobile app contains embedded application frameworks. 

## Image Files on Startup (optional)

When an MAM-enabled app is actively managed by Microsoft Intune, the Intune App SDK will display a startup screen on app launch to indicate to the user that the app is managed. You can optionally add image file(s) to display on the “Managed by your company” startup page. Use the following guidelines for images:

* Add the file names under the `IntuneMAMSettings` dictionary in the app’s info.plist with the key names `SplashIconFile` and `SplashIconFile~ipad`. 

* Image size and requirements:

    * 180 x 180 for the iPhone 6s Plus and iPhone 6 Plus, 120x120 for other iPhone models and 152x152 for the iPad. 
    
    * Remove the `.png` extension from file names 
    
    * Use the `@2x` suffix for 2x scale versions and the `@3x` suffix for the 3x scale versions of the image files. If the images are not the correct size, they will be scaled to fit. If the SplashIconFile values are not specified, the Intune App SDK selects one of the app’s icons (60x60 for all iPhones, 76x76 for iPad).

**Note**: This screen is triggered by launch but can be permanently dismissed by the user.

# Configure the Intune App SDK Settings

The `IntuneMAMSettings` dictionary contained within the application’s `info.plist` is used to configure the Intune App SDK. The following is a list of all supported settings. 

Some of these settings may have been covered in previous sections, and some do not apply to all applications. 

Setting  | Type  | Definition | Required?
--|--|--|--
ADALClientId  | String  | Application’s AAD client identifier. | Required if the application used ADAL.
ADALRedirectUri  | String  | Application’s AAD redirect URI. | Required if the application used ADAL. 
AppGroupIdentifier | Array of String  | Array of app groups from the app’s entitlements com.apple.security.application-groups section. | Required if the app uses application groups.
ContainingAppBundleId  | String | Specifies the bundle id of the extension’s containing application. | Required for iOS extensions.
MainNibFile<br>MainNibFile~ipad  | String  | This setting should contain the application’s main nib file name.  | Required if the application defines MainNibFile in its info.plist.
MainStoryboardFile<br>MainStoryboardFile~ipad  | String  | This setting should contain the application’s main storyboard file name. | Required if the application defines UIMainStoryboardFile in its info.plist
SplashIconFile <br>SplashIconFile~ipad  | String  | Specifies the Intune splash icon file. See the section on “Image Files on Startup” here for more details. | Optional.
SplashDuration | Number | Minimum amount of time in seconds the Intune Splash screen will be displayed at application launch. Defaults to 1.5. | Optional.
ADALLogOverrideDisabled | Boolean  | Specifies whether the SDK will route all ADAL logs (including ADAL calls from the app if any) to its own log file. Defaults to NO. Set to YES if the app would like to set its own ADAL log callback. | Optional.

# Headers for the Intune App SDK 

The following Headers include the API function calls required to enable the functionality of the Intune App SDK. 

    IntuneMAMAsyncResult.h
    IntuneMAMDataProtectionInfo.h
    IntuneMAMDataProtectionManager.h
    IntuneMAMFileProtectionInfo.h
    IntuneMAMFileProtectionManager.h
    IntuneMAMPolicyDelegate.h
    IntuneMAMLogger.h

# Debugging the Intune App SDK in Xcode

Before testing your MAM-enabled app with Microsoft Intune, you can use `Settings.bundle` while in Xcode. This will allow you to set test policies without requiring a connection to Intune. To enable it:

* Add a `Settings.bundle` by right-clicking on the top level folder in your project. Select "Add -> New File" from the menu. Select the “Settings Bundle” template found under "Resources" to add.

* On debug builds only, copy the `MAMDebugSettings.plist` into `Settings.bundle`.

* In `Root.plist` (in Settings.bundle), add a preference of "Type" Child Pane, "FileName" `MAMDebugSettings`.

* In "Settings -> Your-App-Name", toggle “Enable Test Policies”.

* Launch the app (either inside or outside of Xcode). 

* In "Settings -> Your-App-Name -> Enable Test Policies", toggle a policy, e.g. 'PIN'.

* Launch the app (either inside or outside of Xcode). Verify that PIN works as expected.

**Note**: You can now use "Settings -> Your-App-Name -> Enable Test Policies" to enable and toggle settings.

# Recommended iOS Best Practices

The following are some recommended best practices for when developing for iOS:

The iOS file system is case sensitive. Ensure the case is correct for filenames such as `libIntuneMAM.a` and `IntuneMAMResources.bundle`.

If Xcode has trouble finding `libIntuneMAM.a`, you can fix the issue by adding the path to this library into the linker search paths.

