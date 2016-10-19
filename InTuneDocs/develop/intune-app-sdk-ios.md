---
# required metadata

title: Microsoft Intune App SDK for iOS Developer Guide | Microsoft Intune
description:
keywords:
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune App SDK for iOS Developer Guide

> [!NOTE]
> You may wish to first read the [Get Started with Intune App SDK Guide](intune-app-sdk-get-started.md), which explains how to prepare for integration on each supported platform.* 

The Microsoft Intune App SDK for iOS allows you to incorporate Intune Mobile App Management (MAM) into your iOS app. A MAM-enabled application is one integrated with the Intune App SDK, and allows IT administrators to deploy policies to your mobile app when the app is actively managed by Intune.


# What’s in the SDK 

The Intune App SDK for iOS includes a static library, resource files, API headers, a Debug settings plist and a configurator tool. Mobile apps may simply include the resource files and statically link to the libraries for most policy enforcement. Advanced Intune MAM features are enforced through APIs.

This guide will cover the use of the following components of the Intune App SDK for iOS:

* **libIntuneMAM.a**: The Intune App SDK static library. If your app does not use extensions, link this library to your project to enable your app for Intune mobile application management. Instructions are found in the “Building your app with Intune App SDK” section.

* **IntuneMAM.framework**: The Intune App SDK framework. Link this framework to your project to enable your app for Intune mobile application management. Use the framework instead of the static library if your app uses extensions, so that your project does not create multiple copies of the static library.

* **IntuneMAMResources.bundle**: A resource bundle that contains resources the SDK relies on. 

* **Headers**: Exposes the Intune App SDK APIs. If you use an API, you will need to include the header file that contains the API. The following header files include the API function calls required to enable the functionality of the Intune App SDK. 
	
	* IntuneMAMAsyncResult.h
	* IntuneMAMDataProtectionInfo.h
	* IntuneMAMDataProtectionManager.h
	* IntuneMAMFileProtectionInfo.h
	* IntuneMAMFileProtectionManager.h
	* IntuneMAMPolicyDelegate.h
	* IntuneMAMLogger.h 


# How the Intune App SDK works

The objective of the Intune App SDK for iOS is to add management capabilities to iOS applications with minimal code changes. The fewer code changes, the less time to market, but still guaranteeing the consistency and stability of your mobile application. 

The application needs to be linked to the static library and must include the resource bundle. The MAMDebugSettings.plist file is optional and can be included in the package to simulate MAM policies being applied to the application without needing to deploy the application via Microsoft Intune. Additionally, in debug builds, the policies in the MAMDebugSettings.plist file can be applied by transferring the file to the app’s Documents directory via iTunes file sharing.

# Building the SDK into your mobile app 

Complete the steps below to enable the Intune App SDK:

1. **Option 1**: Link to the `libIntuneMAM.a` library by doing the following:

    Drag and drop the `libIntuneMAM.a` library to the “Linked Frameworks and Libraries” list of the project target.
    ![Intune App SDK iOS - linked frameworks and libraries](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png) 

    **Note**: If you plan to release your app to the App Store, please use the version of `libIntuneMAM.a` that is built for release and not the debug version. The release version will be in the “release” folder. The debug version has verbose output which helps troubleshoot issues with the Intune App SDK.
    
    **Option 2**: Link the `IntuneMAM.framework` to your project. Drag and drop `IntuneMAM.framework` to the "Linked Frameworks and Libraries" list of the project target.
    
    **Note**: If you use the framework, you must manually strip out the simulator architectures from the universal framework before submitting your app to the App Store. See the section called "Submitting your app to the App Store."

2. Add the following iOS frameworks to the project:
    * MessageUI.framework
    * Security.framework
    * MobileCoreServices.framework
    * SystemConfiguration.framework
    * libsqlite3.dylib
    * libc++.dylib
    * ImageIO.framework
    * LocalAuthentication.framework
    * AudioToolbox.framework

    **Note**: If the application is targeted for iOS 7, set the "Status" attribute of `LocalAuthentication.framework` to "Optional." If "Status" is not set, the application will fail to launch on iOS 7.

    **Note**: Xcode 7 has switched `.dylib` extensions to `.tbd`.

3. Add the `IntuneMAMResources.bundle` resource bundle to the project by dragging the resource bundle under “Copy Bundle Resources” within “Build Phases."
![Intune App SDK iOS - copy bundle resources](../media/intune-app-sdk-ios-copy-bundle-resources.png)
 
4. Add `-force_load {PATH_TO_LIB}/libIntuneMAM.a` to either of the following, replacing `{PATH_TO_LIB}` with the Intune App SDK location:
    * the project’s `OTHER_LDFLAGS` build configuration setting 
    * the UI’s “Other Linker Flags”<br>

    **Note**: To find the `PATH_TO_LIB`, select the file `libIntuneMAM.a` and choose "Get Info" from the "File" menu. Copy and paste the "Where" information (the path) from the "General" section of the "Info" window.

5. If your mobile app defines a main Nib or Storyboard in its Info.plist, remove the Main Storyboard or Main Nib file fields. Add the Storyboard or Nib values you removed previously under a new dictionary named IntuneMAMSettings with the following key names, as applicable:
    * MainStoryboardFile
    * MainStoryboardFile~ipad
    * MainNibFile
    * MainNibFile~ipad
    
   **Note**: If your mobile app doesn’t define a main Nib or Storyboard in its Info.plist, these settings are **not required**. 

    **Note**: You can view the Info.plist in raw format (in order to see the key names) by right-clicking anywhere in the document body and changing the view type to “Show Raw Keys/Values.”

6. Enable keychain sharing (if not already enabled) by clicking "Capabilities" in each project target and enabling the "Keychain Sharing" switch. Keychain sharing is required to proceed to the next step.

    **Note**: Your provisioning profile needs to support new keychain sharing values. The keychain access groups should support a wildcard character. You can verify this by opening the .mobileprovision file in a text editor, searching for 'keychain-access-groups' and ensuring  you have a wild card, e.g.: 
	```
	<key>keychain-access-groups</key>
	<array>
	<string>YOURBUNDLESEEDID.*</string>
	</array>
	```
7. After enabling keychain sharing, follow these steps to create a separate access group in which the Intune App SDK data will be stored. You can create a keychain access group by using the UI or by using the entitlements file:

    Using the UI to create a keychain access group: 
    
    * If your mobile app does not have any keychain access groups defined, add the app’s bundle id as the first group.
    * Add the shared keychain group `com.microsoft.intune.mam`. This access group is used by the Intune App SDK to store data.  
    * Add `com.microsoft.adalcache` to your existing access groups. 

	![Intune App SDK iOS - keychain sharing](../media/intune-app-sdk-ios-keychain-sharing.png) 

    If you are using the entitlement file to create the keychain access group, rather than the regular UI, you will need to prepend the key chain access group with `$(AppIdentifierPrefix)` in the entitlement file. For example:  
    * `$(AppIdentifierPrefix)com.microsoft.intune.mam` 
	* `$(AppIdentifierPrefix)com.microsoft.adalcache`

	**Note**: An entitlements file is an XML file unique to your mobile application that is used to specify special permissions and capabilities within your iOS app.

8. If the app defines URL schemes in its Info.plist file, add another scheme, with a `-intunemam` suffix, for each URL scheme.

9. For mobile apps developed for iOS 9+, you are required to include each protocol your app passes to `UIApplication canOpenURL` in the `LSApplicationQueriesSchemes` array of your app's Info.plist file. Additionally, for each protocol listed, a new protocol needs to be added and appended with `-intunemam`. You must also include `http-intunemam`, `https-intunemam`, and `ms-outlook-intunemam` in the array. 

10. If the app has app groups defined in its entitlements, add these groups to the IntuneMAMSettings dictionary under the `AppGroupIdentitifiers` key as an array of strings.

11. Link your mobile application to the Azure Directory Authentication Library (ADAL). The ADAL library for Objective C is [available on Github](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

    **Note**: The Intune App SDK has been tested against the ADAL broker branch code from 6/19/2015. Please ensure that you are linking with the latest/working version of the ADAL library.

12. Include the `ADALiOSBundle.bundle` resource bundle in the project by dragging the resource bundle under “Copy Bundle Resources” within “Build Phases."

13. Use the `-force_load PATH_TO_ADAL_LIBRARY` linker option when linking to the library.

    Add `-force_load {PATH_TO_LIB}/libADALiOS.a` to the project’s `OTHER_LDFLAGS` build configuration setting or “Other Linker Flags” in the UI. `PATH_TO_LIB` should be replaced with the ADAL binaries location. 

# Configuring Azure Directory Authentication Library (ADAL) settings in your  app 

The Intune App SDK uses ADAL for its authentication and conditional launch scenario. It also relies on ADAL to register the user identity with the MAM service for management without device enrollment scenarios. 

Typically, ADAL requires apps to register and obtain a unique ID, known as ClientID, and other identifiers, to guarantee the security of the tokens granted to the app. The Intune App SDK uses default registration values when contacting Azure Active Directory.  

If the app itself uses ADAL for its authentication scenario, the app must use its existing registration values and override the Intune App SDK default values to ensure that end users are not prompted for authentication twice (once by the Intune App SDK and once by the app). 

##ADAL FAQs

**What ADAL binaries should I use?** 

The Intune App SDK currently uses the broker branch of [ADAL on GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-objc) in order to support apps that require Conditional Access (apps that, therefore, depend on the Microsoft Authenticator app). However, the SDK is still compatible with the master branch of ADAL. Please use the branch that is appropriate for your app.

**How do I link to ADAL binaries?**

Add `-force_load {PATH_TO_LIB}/libADALiOS.a` to the project’s `OTHER_LDFLAGS` build configuration setting or “Other Linker Flags” in the UI. `PATH_TO_LIB` should be replaced with the ADAL binaries location. Also, make sure to copy the ADAL bundle to your app.  

For more detail, see the instructions from [ADAL on Github](https://github.com/AzureAD/azure-activedirectory-library-for-objc).


**How do I share ADAL cache with other apps signed with the same provisioning profile?**

If your app does not have any keychain access groups defined, add the app’s bundle id as the first group.
Enable ADAL SSO by adding `com.microsoft.adalcache` and `com.microsoft.workplacejoin` access groups in the keychain entitlements. 

In case you are explicitly setting the ADAL shared cache keychain group, make sure it is set to `<app_id_prefix>.com.microsoft.adalcache`. ADAL will set this for you unless you override it. If you want to specifiy a custom keychain group to replace `com.microsoft.adalcache`, please specify that in the Info.plist under "IntuneMAMSettings," using the key `ADALCacheKeychainGroupOverride`.

**How do I force the Intune App SDK to use ADAL settings that my app already uses?** 

If your app already uses ADAL, see the section on IntuneMAMSettings below for information on populating the settings below:  

* ADALClientId
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

**How do I switch between AAD production and internal test environments?**

The`AadAuthorityURI` setting in `MAMPolicies.plist` can be used to specify the AAD environment used for ADAL calls. It’s currently set to use AAD Pre-production Environment (PPE) by default unless overridden.
	
To test against PPE, you can use a compile-time or runtime switch. 

For a compile-time environment switch of MAM service URLs and AAD, set the `UsePPE` Boolean flag set  true in MAMEnvironment.plist (**Note**: there is no support for doing this via Info.plist). 

For a run-time environment switch, set `com.microsoft.intune.mam.useppe` in standard user defaults to “1” to use PPE. This replaces the existing `com.microsoft.intune.mam.AADAuthorityEnvironment` setting. 

**How do I override the AAD authority URL with a tenant-specific URL supplied at runtime?** 

Set the `aadAuthorityUriOverride` property on IntuneMAMPolicyManager instance.

**Note**: You would need this in the MAM without device enrollment scenario to allow the SDK to reuse the ADAL refresh token fetched by the app.

**Note:** The SDK will continue to use this authority URL for policy refresh and any subsequent enrollment requests unless the value is cleared or changed.  Therefore, it is important to clear the value when a corporate user signs out of the app and reset it when a new corporate user signs back in.


**What should I do if my app itself utilizes ADAL for authentication?**

The steps below are required if the app already utilizes ADAL for authentication. If your app does not rely on ADAL, you should review the section on how to register with Intune service if your app does not use ADAL.

* In the project’s Info.plist, under the IntuneMAMSettings dictionary with the key name `ADALClientId`, specify the ClientID to be used for ADAL calls. 

* In the project’s Info.plist, under the IntuneMAMSettings dictionary with the key name `ADALRedirectUri`, specify the Redirect URI to be used for ADAL calls. You may also need to specify the `ADALRedirectScheme` depending on the format of your app’s Redirect URI.



#Registering your app with MAM service 

## Using the APIs
The Intune App SDK now provides the ability for iOS apps to receive MAM policies from Intune without the need to be MDM-enrolled with Intune. To support this new functionality, the SDK provides new APIs that allow the app to receive MAM policies. In order to use the new APIs, complete the following steps:

1. Use the latest release of the Intune App SDK which supports management of apps with or without device enrollment. If your app has used an older version of the SDK without this feature, you will need to update the Intune MAM library, as well as update the Headers folder with the headers from the latest SDK.

2. Add IntuneMAMEnrollment.h to any files that will call the APIs 

3. To test against PPE, you can include use a compile-time or runtime switch. 

	For a compile-time environment switch of MAM service URLs and AAD, set the `UsePPE` Boolean flag set  true in MAMEnvironment.plist (**note**: there is no support for doing this via Info.plist). 

	For a run-time environment switch, set `com.microsoft.intune.mam.useppe` in standard user defaults to “1” to use PPE. This replaces the existing `com.microsoft.intune.mam.AADAuthorityEnvironment` setting. 


##Registering Accounts 

An app can receive MAM policies from the Intune service if the app is enrolled on behalf of a specified user account.  It is the responsibility of the app to register any newly signed-in user with the Intune App SDK.  After the new user account has been authenticated, the app should call the `registerAndEnrollAccount` method found in Headers/IntuneMAMEnrollment.h: 

```
/** 


 *  This method will add the account to the list of registered accounts. 
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK 
 */ 

(void)registerAndEnrollAccount:(NSString *)identity; 

```
By calling the method above, the SDK will register the user account and attempt to enroll the app on behalf of this account.  If the enrollment fails for any reason, the SDK will automatically re-try the enrollment 24 hours later.  For debugging purposes, the app can receive notifications, via a delegate, about the results of any enrollment requests (see details below).

Once this API has been invoked, the application can continue functioning as normal.  If the enrollment does succeed, the SDK will notify the user that an app restart is required.  At that time, the user can immediately restart the app.


##De-registering Accounts 


Before a user is signed out of an app, the app should de-register the user from the SDK.  This will ensure: 

1. Enrollment retries will no longer happen for the user’s account. 
2. If the user has successfully enrolled the application, the user and app will be un-enrolled from the Intune MAM Service and MAM policies will be removed.
3. Optionally, a selective wipe can be initiated to ensure any work or school related data is deleted. 

Before the user is signed out, the app should call the following API found in Headers/IntuneMAMEnrollment.h: 

```
/*
 *  This method will remove the provided account from the list of 
 *  registered accounts.  Once removed, if the account has enrolled 
 *  the application, the account will be un-enrolled. 
 *  @note In the case where an un-enroll is required, this method will block 
 *  until the Intune MAM AAD token is acquired, then return.  This method must be called before  
 *  the user is removed from the application (so that required AAD tokens are not purged 
 *  before this method is called). 
 *  @param identity The UPN of the account to be removed. 
 *  @param doWipe   If YES, a selective wipe if the account is un-enrolled 
 */ 

(void)deRegisterAndUnenrollAccount:(NSString *)identity withWipe:(BOOL)doWipe; 
```

This method must be called before the user account’s AAD tokens are deleted.  The SDK needs the user’s app token to make specific requests to the Intune MAM Service on behalf of the user. 

If the app will delete the user’s work or school related data on its own, then the `doWipe` flag can be set to false.  Otherwise, the app can have the SDK initiate a selective wipe, which will result in a call to the app's selective wipe delegate). 

```
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES]; 
```


##Enrolling Without Prior Sign-in 

An app which does not sign in the user with Azure Active Directory can still receive MAM policies from the Intune Service by calling the API below to have the SDK handle that authentication. Apps should use this when they have not authenticated a user with AAD but still need to retrieve MAM policies to protect data in their app -- for example: if another authentication service is being used for app log in, or if the app does not support signing in at all. To do this, the application should call the 
`loginAndEnrollAccount`  method found in Headers/IntuneMAMEnrollment.h:

```
/** 
 *  Creates an enrollment request which is started immediately. 
 *  If no token can be retrieved for the identity, the user will be prompted 
 *  to enter their credentials, after which enrollment will be retried. 
 *  @param identity The UPN of the account to be logged in and enrolled. 
 */ 
 (void)loginAndEnrollAccount: (NSString *)identity; 

```
By calling this method, the SDK will prompt the user for credentials if no existing token can be found and then will attempt to enroll the application on behalf of this account. The method can be called with "nil" as the identity, in which case the SDK will enroll with the existing MAM user on the device, or prompt the user for a username if no existing user is found. 

If the enrollment fails, the app should consider calling this API again at a future time, depending on the details of the failure. The app can receive notifications, via a delegate, about the results of any enrollment requests (see details). 

Once this API has been invoked, the app can continue functioning as normal.  If the enrollment does succeed, the SDK will notify the user that an app restart is required, as is shown in the above section on registering accounts. 

##Debug Information 

The app can receive debug notifications about the following requests to the Intune MAM Service: 

 - Enrollment Requests 
 - Policy Update Requests 
 - Un-enroll Requests 

The notifications are presented via delegate methods that can be found in Headers/IntuneMAMEnrollmentDelegate.h: 

```
/** 
 *  Called when an enrollment request operation is completed. 
 * @param status status object containing debug information 
 */ 
 
(void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status; 

/** 
 *  Called when a MAM policy request operation is completed.
 *  @param status status object containing debug information 
 */ 
(void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status; 

/**
 *  Called when a un-enroll request operation is completed. 
 *  @Note: when a user is un-enrolled, the user is also de-registered with the SDK 
 *  @param status status object containing debug information 
 */ 

(void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status; 

```

These delegate methods return an ```IntuneMAMEnrollmentStatus``` object that contains the following information: 

- The identity of the account associated with the request 
- Status Code indicating the result of the request 
- An error string with a description of the status code 
- An NSError object 

This object is defined in Headers/IntuneMAMEnrollmentStatus.h along with the specific status codes that can be returned. 

It is important to note that this information is for debug purposes, and no app's business logic should be based off these notifications.  The idea is that the app can send this information to a telemetry service for debugging or monitoring purposes. 


##Sample Code 

The following are example implementations of the delegate methods: 

```
- (void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status 


{ 


    NSLog(@"enrollment result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode); 


    NSLog(@"Debug Message: %@", status.errorString); 


} 


- (void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status 


{ 


    NSLog(@"policy check-in result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode); 


    NSLog(@"Debug Message: %@", status.errorString); 


} 


- (void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status 


{ 


    NSLog(@"un-enroll result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode); 



    NSLog(@"Debug Message: %@", status.errorString); 


} 

```


##App Restart 

When an app receives MAM policies for the first time, it will need to restart to apply the required hooks.  In order to notify the app that a restart needs to happen, the SDK provides a delegate method in Headers/IntuneMAMPolicyDelegate.h. 
```
 - (BOOL) restartApplication 
```
The return value of this method will tell the SDK if the application will handle the required restart.   

 - If true is returned, the application will be responsible for handling the restart.   
 - If false is returned, the SDK will restart the application after this method returns.  The SDK will immediately bring up a dialog telling the user the application must be restarted. 

#Implementing Save-as Controls

Intune allows IT administrators to select which storage locations a managed app can save data to. Apps can query the Intune App SDK for allowed storage locations using the **isSaveToAllowedForLocation** API.

Before saving managed data to a cloud-storage or local locations, apps must check with the **isSaveToAllowedForLocation** API to know if the IT administrator has allowed data to be saved there.

When using the **isSaveToAllowedForLocation** API, apps must pass in the UPN used for the storage location, if it is available.

##Supported Locations

The **isSaveToAllowedForLocation** API provides constants to check the following locations:

* IntuneMAMSaveLocationOther 
* IntuneMAMSaveLocationOneDriveForBusiness 
* IntuneMAMSaveLocationSharePoint 
* IntuneMAMSaveLocationBox 
* IntuneMAMSaveLocationDropbox 
* IntuneMAMSaveLocationGoogleDrive 
* IntuneMAMSaveLocationLocalDrive 

Apps should use the constants in the **isSaveToAllowedForLocation** API to check if data can be saved to locations considered "managed," such as OneDrive for Business, or "personal." Additionally, the API should be used when the app is unable to determine whether a location is "managed" or "personal." 

When a location is known to be "personal," apps should use the **IntuneMAMSaveLocationOther** value. 

The **IntuneMAMSaveLocationLocalDrive** constant should be used when the app is saving data to any location on the local device.



# Configure the Intune App SDK Settings

The IntuneMAMSettings dictionary contained within the application’s Info.plist is used to configure the Intune App SDK. The following is a list of all supported settings. 

Some of these settings may have been covered in previous sections, and some do not apply to all apps. 

Setting  | Type  | Definition | Required?
--       |  --   |   --       |  --
ADALClientId  | String  | The app’s AAD client identifier. | Required if the app uses ADAL.
ADALRedirectUri  | String  | The app’s AAD redirect URI. | ADALRedirectUri or ADALRedirectScheme is required if the app uses ADAL. 
ADALRedirectScheme  | String  | The app's AAD redirect scheme. This can be used in place of ADALRedirectUri if the application's redirect URI is in the format `scheme://bundle_id`. | ADALRedirectUri or ADALRedirectScheme is required if the app uses ADAL. 
ADALLogOverrideDisabled | Boolean  | Specifies whether the SDK will route all ADAL logs (including ADAL calls from the app if any) to its own log file. Defaults to NO. Set to YES if the app would like to set its own ADAL log callback. | Optional.
ADALCacheKeychainGroupOverride | String  | Specifies the keychain group to use for ADAL cache instead of “com.microsoft.adalcache." Note that this doesn’t contain the app-id prefix. That will be prefixed to the provided string at runtime. | Optional.
AppGroupIdentifiers | Array of String  | Array of app groups from the app’s entitlements com.apple.security.application-groups section. | Required if the app uses application groups.
ContainingAppBundleId | String | Specifies the bundle id of the extension’s containing application. | Required for iOS extensions.
DebugSettingsEnabled| Boolean | If set to YES, test policies within the Settings bundle can be applied. Applications should **not** be shipped with this setting enabled. | Optional.
MainNibFile<br>MainNibFile~ipad  | String  | This setting should contain the application’s main nib file name.  | Required if the application defines MainNibFile in its Info.plist.
MainStoryboardFile<br>MainStoryboardFile~ipad  | String  | This setting should contain the application’s main storyboard file name. | Required if the application defines UIMainStoryboardFile in its Info.plist
MAMPolicyRequired| Boolean| Specifies whther the app will be blocked from launching if the app does not have Intune MAM policy. Defaults to "no." 
MAMPolicyWarnAbsent | Boolean| Specifies whether the app will warn the user during launch if the app does not have Intune MAM policy. Note: apps cannot be submitted to the store with this setting set to YES | Optional.
MultiIdentity | Boolean| Specifies whether or not the app is multi-identity aware | Optional.
SplashIconFile <br>SplashIconFile~ipad | String  | Specifies the Intune splash icon file. See the section on “Image Files on Startup” here for more details. | Optional.
SplashDuration | Number | Minimum amount of time in seconds the Intune Splash screen will be displayed at application launch. Defaults to 1.5. | Optional.
BackgroundColor| String| Specifies background color for splash and PIN screens. Accepts a hexadecimal RGB string in the form of ‘#XXXXXX’, where the ‘X’s can range from 0-9 or A-F. The pound sign may be omitted.   | Optional, defaults to light grey.
ForegroundColor| String| Specifies foreground color for splash and PIN screens, such as text color. Accepts a hexadecimal RGB string in the form of ‘#XXXXXX’, where the ‘X’s can range from 0-9 or A-F. The pound sign may be omitted.  | Optional, defaults to Black.
AccentColor | String| Specifies accent color for PIN screen, such as button text color and box highlight color.  Accepts a hexadecimal RGB string in the form of ‘#XXXXXX’, where the ‘X’s can range from 0-9 or A-F. The pound sign may be omitted.| Optional, defaults to system blue.
MAMTelemetryDisabled| Boolean| Specifies if the SDK will not send any telemetry data back to its backend| Optional.
MAMTelemetryUsePPE | Boolean | Specifies if the SDK will send data to Pre-production Environment (PPE) backend. Use this when testing your apps with Intune policy so that test telemetry data does not mix up with customer data. | Optional.

## Telemetry 

By default, the Intune App SDK for iOS logs telemetry data on usage events, which is sent to Microsoft Intune. Data is logged on the following usage events: 

1. **App launch**: to help Microsoft Intune learn about MAM-enabled app usage by management type (MAM with MDM, MAM without MDM enrollment, etc.).

2. **EnrollApplication API call**: to help Microsoft Intune learn about success rate and various other performance metrics of `enrollApplication` calls from the client side.

**Note**: If you choose not to send Intune App SDK telemetry data to Microsoft Intune from your mobile application, you must disable Intune App SDK telemetry capture by setting the property `MAMTelemetryDisabled` to "YES" in the IntuneMAMSettings dictionary.


## Building the SDK into your extension (optional) 

When building extensions, follow the same instructions to build your mobile app as outlined in the section on “Building the SDK into your mobile app." Additionally, update each extension’s Info.plist file by adding a `ContainingAppBundleId` key under the IntuneMAMSettings dictionary with the value of the containing application’s bundle id.

## Building the SDK into your framework (optional)

With the latest updates to the Intune App SDK, you do not have to compile your mobile app with any specific linker flags if your mobile app contains embedded application frameworks. 

## Image Files on Startup (optional)

When an MAM-enabled app is actively managed by Microsoft Intune, the Intune App SDK will display a startup screen on app launch to indicate to the user that the app is managed. You can optionally add image file(s) to display on the “Managed by your company” startup page. Use the following guidelines for images:

* Add the file names under the IntuneMAMSettings dictionary in the app’s Info.plist with the key names `SplashIconFile` and `SplashIconFile~ipad`. 

* Image size and requirements:

    * 180 x 180 for the iPhone 6s Plus and iPhone 6 Plus, 120x120 for other iPhone models and 152x152 for the iPad. 
    
    * Remove the .png extension from file names. 
    
    * Use the `@2x` suffix for 2x scale versions and the `@3x` suffix for the 3x scale versions of the image files. If the images are not the correct size, they will be scaled to fit. If the SplashIconFile values are not specified, the Intune App SDK selects one of the app’s icons (60x60 for all iPhones, 76x76 for iPad).

**Note**: This screen is triggered by launch but can be permanently dismissed by the user.



#Enabling Multi-Identity (optional)

By default, the SDK will apply policy  to the app as a whole. Multi-Identity is a MAM feature which can be enabled to allow policy to be applied on a per-identity level.  This requires more app participation than other MAM features. 

The app is required to inform the app SDK when it intends to change the active identity. The SDK will also notify the app when an identity change is required. Currently, only one managed identity is supported. Once the user enrolls the device or the app, the SDK uses this identity and considers it the primary managed identity. Other users in the app will be treated as unmanaged with unrestricted policy settings. 

Note that an identity is simply defined as a string. Identities are case-insensitive and requests to the SDK for an identity may not return the same casing that was originally used when setting the identity.


##Understanding Identities 
  
An identity is simply the username of an account (e.g. user@contoso.com). Developers can set the identity of the app on the following different levels: 

* **Process identity**: the process identity sets the process-wide identity and is mainly used for single identity applications. This identity affects all operations, files, and UI.
* **UI identity**: determines what policies are applied to UI operations on the main thread such as cut/copy/paste, PIN, authentication, data sharing, etc. The UI identity does not affect file operations (encryption, backup, etc.).
* **Thread identity**: The thread identity affects what policies are applied on the current thread. This affects all operations, files, and UI.

It's the app's responsibility to set the identities appropriately whether or not the user is managed.

At any point in time, every thread has an effective identity for UI operations and file operations. This is the identity used to determine what policies, if any, should be applied. If the identity is 'no identity' or the user is not managed, then no policies will be applied. 
 
 

##Thread Queues
 
Apps often dispatch asynchronous and synchronous tasks to thread queues. The SDK intercepts Grand Central Dispatch (GCD) calls and associates the current thread identity with the dispatched tasks. When the tasks are executed, the SDK temporarily changes the thread identity to the identity associated with the task, executes the tasks, then restores the original thread identity. Since `NSOperationQueue` is built on top of GCD, `NSOperations` will run on the identity of the thread at the time they are added to the `NSOperationQueue`. The `NSOperations` or functions dispatched using GCD directly also have the ability to change the current thread identity as they are running. This identity will override the identity inherited from the dispatching thread. 

##File Owner
 
The SDK keeps track of local file owner identity and applies policies accordingly. The file owner is established when the file is created or when the file is opened in truncate mode. The owner is set to the effective file operation identity of the thread performing the operation. Alternatively, apps can set the file owner identity explicitly using the `IntuneMAMFilePolicyManager`. Apps can use the `IntuneMAMFilePolicyManager` to retrieve the file owner and set the UI identity prior to displaying the file contents.


##Shared Data Files
 
If the app creates files that contain data from both managed and unmanaged users, it’s the app's responsibility to encrypt the managed user’s data. Data can be encrypted using the `IntuneMAMDataProtectionManager`'s `protect` and `unprotect` APIs. The `protect` method accepts an identity which can be a managed or unmanaged user. If the user is managed, the data will be encrypted. If the user is unmanaged, a header will be added to the data encoding the identity but the data will not be encrypted.  The `protectionInfo` method can be used to retrieve the data’s owner.

##Share Extensions
 
If the app contains a Share Extension, the owner of the item being shared can be retrieved using the  `protectionInfoForItemProvider` method in `IntuneMAMDataProtectionManager`. If the shared item is a file, the SDK will handle setting the file owner. If the shared item is data, it’s the app's responsibility to set the file owner if this data is persisted to a file, and to call the `setUIPolicyIdentity` API (described below) before displaying this data in the UI.
 
##Turning On Multi-Identity
 
By default apps are considered single identity and the SDK sets the process identity to the enrolled user. To enable multi-identity support, a boolean setting with the name `MultiIdentity` with value 'YES' must be added to the **IntuneMAMSettings** dictionary within the app's Info.plist. 

> [!NOTE]
> When multi-identity is enabled, the process identity, UI identity, and thread identities will be set to nil. It is the app's responsibility to set them appropriately.

 
##Switching Identities
 
###App-initiated identity switch
At launch, multi-identity apps are considered to be running under an unknown, unmanaged account. The conditional launch UI will not run, and no policies will be enforced on the app. It’s the app's responsibility to notify the SDK whenever the identity should be changed. Typically, this will happen whenever the app is about to display data for a specific user account.

An example is when the user attempts to open a document, mailbox, or a tab in a notebook. The app needs to notify the SDK before the file, mailbox, or tab is actually opened. This is done through the `setUIPolicyIdentity` API in `IntuneMAMPolicyManager`. This API should be called whether or not the user is managed. If the user is managed, the SDK will perform the conditional launch checks (jailbreak detection, PIN, authentication, etc.). The result of the identity switch is returned to the app asynchronously through a completion handler. The app should postpone opening the document, mailbox, tab, etc. until a success result code is returned. If the identity switch failed, the app should cancel the operation. 

###SDK-initiated identity switch
There are cases where the SDK needs to ask the app to switch to a specific identity. Multi-identity apps must implement the `identitySwitchRequired` method in `IntuneMAMPolicyDelegate` to handle this request. When called, if the app is able to handle the request to switch to the specified identity it should pass `IntuneMAMAddIdentityResultSuccess` into the completion handler. If it is unable to handle switching the identity, the app should pass `IntuneMAMAddIdentityResultFailed` into the completion handler. The app does not have to call `setUIPolicyIdentity` in response to this call. If the SDK needs the app to switch to an unmanaged user account, the empty string will be passed into the `identitySwitchRequired` call. 
 
###Selective wipe
When the app is selectively wiped, the SDK will call the `wipeDataForAccount` method in `IntuneMAMPolicyDelegate`. It is  the app's responsibility to remove the specified user’s account and any data associated with it. The SDK is capable of removing all files owned by the user and will do so if the app returns "FALSE" from the `wipeDataForAccount` call. Note, this method is called from a background thread and the app should not return until all data for the user has been removed (with the exception of files if the app will return "FALSE").

# Debugging the Intune App SDK in Xcode

Before manually testing your MAM-enabled app with Microsoft Intune, you can use a **Settings.bundle** file while in Xcode. This will allow you to set test policies without requiring a connection to Intune. To enable it:

* Add a Settings.bundle file by right-clicking on the top level folder in your project. Select "Add -> New File" from the menu. Select the “Settings Bundle” template found under "Resources" to add.

* On debug builds only, copy the MAMDebugSettings.plist into Settings.bundle.

* In Root.plist (which is in Settings.bundle), add a preference with "Type" = Child Pane and "FileName" = MAMDebugSettings.

* In **Settings -> Your-App-Name**, turn on “Enable Test Policies."

* Launch the app (either inside or outside of Xcode). 

* In **Settings -> Your-App-Name -> Enable Test Policies**, turn on a policy, e.g. "PIN."

* Launch the app (either inside or outside of Xcode). Verify that PIN works as expected.

> [!NOTE]
> You can now use **Settings -> Your-App-Name -> Enable Test Policies** to enable and toggle settings.

# Recommended iOS Best Practices

The following are some recommended best practices for when developing for iOS:

The iOS file system is case sensitive. Ensure the case is correct for filenames such as `libIntuneMAM.a` and `IntuneMAMResources.bundle`.

If Xcode has trouble finding `libIntuneMAM.a`, you can fix the issue by adding the path to this library into the linker search paths.



##FAQ 

 **Do all users of my application need to be registered with the MAM service?**

No.  In fact, only work or school accounts should be registered with the Intune App SDK.  Apps are responsible for determining if an account is used in a work or school context.   
 
**What about users that have already signed into the application?  Do they need to be enrolled?** 

While the application is responsible for enrolling users after they have successfully authenticated, the application is also responsible for enrolling any existing accounts that may have been present before the application had MDM-less MAM functionality.   


To do this, the application should make use of the `registeredAccounts:` method.  This method returns an NSDictionary containing all of the accounts registered into the Intune MAM service.  If any existing accounts in the application are not present in the list, the application should register and enroll those accounts via `registerAndEnrollAccount:`. 


 

**How often does the SDK retry enrollments?** 

The SDK will automatically retry all previously failed enrollments on a 24-hour interval.  The SDK does this to ensure that if a user’s organization enabled MAM after the user signed into the application, then the user will successfully enroll and receive policies. 

The SDK will stop re-trying when it detects that a user has successfully enrolled the application.  This is because only 1 user can enroll an application at any given time. If the user is un-enrolled, the retries will begin again on the same 24-hour interval. 


 
**Why does the user need to be de-registered?** 

The SDK will take the following actions in the background periodically:

 - If the application is not yet enrolled, it will try to enroll all registered accounts every 24 hours. 
 - If the application is enrolled, the SDK will check for MAM policy updates every 8 hours. 

By de-registering a user, it notifies the SDK that the user will no longer be using the application and can halt any of the above periodic events for that user account.  It will also trigger an app un-enroll and selective wipe if necessary. 

**Should I set the doWipe flag to true in the deregister method?** 
This method should be called before the user is signed out of the application.  If, as part of the sign-out, the user’s data is deleted from the application, then `doWipe` can be set to false.  However, if the application does not actually remove the user’s data, then this should be set to true so that the SDK can manually delete the data itself. 

**Are there any other ways that an application can be un-enrolled?** 
Yes, the IT admin can send a selective wipe command to the application, which will result in the user being deregistered, un-enrolled, and the user’s data being wiped.  The SDK automatically handles this scenario and will send a notification via the un-enroll delegate method. 

#Submitting your app to the App Store
Both the static library and framework builds of the Intune App SDK are universal binaries, which means they contain code for all device and simulator architectures. Apple will reject apps submitted to the App Store if they contain simulator code. When compiling against the static library for device-only builds, the linker will automatically strip out the simulator code.

If your app uses the **framework build** of the Intune App SDK, you must manually strip out the simulator architectures from the universal framework before submitting your app to the App Store. The instructions below will help you do this:

1. Make sure `IntuneMAM.framework` is on your Desktop.
2. Run the following commands:
	
	```
	lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
	```
	The first command strips the simulator architectures from the framework's dylib.
	```
	cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM 
	```
	The second command copies the device-only dylib back into the framework directory.
