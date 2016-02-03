---
title: Microsoft Intune App SDK for Android Developer Guide
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
author: Msmbaldwin
---
# Microsoft Intune App SDK for Android Developer Guide
***Note**:  You may wish to first read the [Get Started with Intune App SDK Guide](Getting_Started_and_FAQ.md), which explains how to prepare for integration on each supported platform.* 

You can use the Microsoft Intune App SDK to enable mobile app management (MAM) features within your Android app. MAM policies allow IT administrators to deploy policies to enlightened apps (apps that have the Intune App SDK enabled) that are managed by Microsoft Intune.  

**Note**: You may wish to first read the [[Get Started with Intune App SDK guide](Getting_Started_and_FAQ.xml)](intune), which covers the current features of the SDK and describes how to prepare for integration on each supported platform. 

# What is in the SDK 

The Intune App SDK for Android is a standard Android library with no external dependencies. 
The SDK composed of:  

* **`Microsoft.Intune MAM.SDK.jar`**: The interfaces necessary to enable MAM in an app, in addition to enabling interoperability with the Microsoft Intune Company Portal app. Apps must specify it as an Android library reference.

*  **`Microsoft.Intune.MAM.SDK.Support.v4.jar`**: The interfaces necessary to enable MAM in apps that leverage the android v4 support library.  Apps which need this support must   reference the jar file directly. 

* **`Microsoft.Intune.MAM.SDK.Support.v7.jar`**: The interfaces necessary to enable MAM in apps that leverage the android v7 support library.   Apps which need this support must reference the jar file directly

* **The resource directory**: The resources (such as strings) on which the SDK relies. 

* **`Microsoft.Intune.MAM.SDK.aar`**: The SDK components, with the exception of the Support.V4 and Support.V7 jars. This file can be used in place of the individual components if your build system supports AAR files.

* **`AndroidManifest.xml`**: The additional entry points and the library requirements. 

* **`THIRDPARTYNOTICES.TXT`**:  An attribution notice that acknowledges 3rd party and/or OSS code that will be compiled into your app. 

# Requirements 

The Intune App SDK is a compiled Android project. As a result, it is largely agnostic to the version of Android the app uses for its minimum or target API versions. The SDK supports Android API 14 (Android 4.0+) to Android 24. 

# How the Intune App SDK works 

The Intune App SDK requires changes to an app's source code to enable app management policies. This is done through the replacement of the android base classes with equivalent managed classes, referred to in the document with the prefix `MAM`. The SDK classes live between the Android base class and the app's own derived version of that class.  Using an activity as an example, you end up with an inheritance hierarchy that looks like: `Activity ->MAMActivity->AppSpecificActivity`.

When `AppSpecificActivity` wants to interact with its parent, e.g. `super.onCreate())`, `MAMActivity` is the super class despite being in the inheritance hierarchy and replacing a few methods. Android apps  have a single mode , and have access to the whole system through their Context object.  Apps that have incorporated the Intune App SDK, on the other hand, have dual modes, as the apps continue to access the system through the Context object but, depending on the base Activity used, the Context object will either be provided by Android, or will intelligently multiplex  between a restricted view of the system and the Android-provided Context.

The Intune App SDK for android relies on the presence of the Company Portal app on the device  for enabling MAM policies. When the Company Portal app is not present, the behavior of the MAM enabled app will not be altered, and it will act like any other mobile app. When the Company Portal is installed and has policy for the user, the SDK entry points are initialized asynchronously. Initialization is only required when the process is initially created by Android. During initialization, a connection is established with Company Portal app, and app restriction policy is downloaded.  

# How to integrate with the Intune App SDK
 
As outlined earlier , the SDK requires changes to the app's source code to enable app management policies. Here are the steps necessary to enable MAM in your  app: 

## Replace classes, methods, and activities with their MAM equivalent (Required) 

* Android base classes must be replaced by their MAM equivalent. To do so, find all instances of the classes listed in the table below and replace them with the Intune App SDK equivalent.  

    | Android Class | Intune App SDK Replacement |
    |--|--|
    | android.app.Activity | MAMActivity |
    | android.app.ActivityGroup | MAMActivityGroup |
    | android.app.AliasActivity | MAMAliasActivity |
    | android.app.Application | MAMApplication |
    | android.app.DialogFragment | MAMDialogFragment |
    | android.app.ExpandableListActivity | MAMExpandableListActivity |
    | android.app.Fragment | MAMFragment |
    | android.app.IntentService | MAMIntentService |
    | android.app.LauncherActivity | MAMLauncherActivity |
    | android.app.ListActivity | MAMListActivity |
    | android.app.NativeActivity | MAMNativeActivity |
    | android.app.PendingIntent | MAMPendingIntent |
    | android.app.Service | MAMService |
    | android.app.TabActivity | MAMTabActivity |
    | android.app.TaskStackBuilder | MAMTaskStackBuilder |
    | android.app.backup.BackupAgent | MAMBackupAgent |
    | android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
    | android.app.backup.FileBackupHelper | MAMFileBackupHelper |
    | android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
    | android.content.BroadcastReceiver | MAMBroadcastReceiver |
    | android.content.ContentProvider | MAMContentProvider |
    | android.os.Binder | MAMBinder* |
    | android.provider.DocumentsProvider | MAMDocumentsProvider |
    | android.preference.PreferenceActivity | MAMPreferenceActivity |

    *It is only necessary to replace Binder with MAMBinder if the Binder is not generated from an AIDL interface.

    **Microsoft.Intune.MAM.SDK.Support.v4.jar**:

    | Android Class	Intune MAM | SDK Replacement |
    |--|--|
    | android.support.v4.app.DialogFragment | MAMDialogFragment
    | android.support.v4.app.FragmentActivity | MAMFragmentActivity
    | android.support.v4.app.Fragment | MAMFragment
    | android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
    | android.support.v4.content.FileProvider | MAMFileProvider
    
    **Microsoft.Intune.MAM.SDK.Support.v7.jar**:

    |Android Class | Intune MAM SDK Replacement |
    |--|--|
    |android.support.v7.app.ActionBarActivity | MAMActionBarActivity |


* When using an android entry point that has been overridden by its MAM equivalent, an alternative version of the entry point's lifecycle must be used (with the exception of the class `MAMApplication`).

    For example, when deriving from `MAMActivity`, instead of overriding `onCreate` and calling `super.onCreate`, the Activity must override `onMAMCreate` and call s`uper.onMAMCreate`. This allows Activity launch (amongst others) to be restricted in certain cases. 

# Enable features that require app participation 

There are some policies the SDK cannot implement on its own. To enable the app to control its behavior for these features, we expose several APIs that you can find in the `AppPolicy` interface included below.  

    /**
     * External facing app policies.
     */
    public interface AppPolicy {
    	/**
    	 * Restrict where an app can save personal data.
    	 * 
    	 * @return True if the app is allowed to save to personal data stores;
    	 *         false otherwise.
    	 */
    	boolean getIsSaveToPersonalAllowed();
    
    	/**
    	 * Check if policy prohibits saving to a content provider location.
    	 * 
    	 * @param location
    	 *            a content URI to check
    	 * @return True if location is not a content URI or if policy does not 
    	 *         prohibit saving to the content location.
    	 */
    	boolean getIsSaveToLocationAllowed(android.net.Uri location); 
    
    	/**
    	 * Whether the SDK PIN prompt is enlightened for the app.
    	 * 
    	 * @return True if the PIN is enabled. False otherwise.
    	 */
    	boolean getIsPinRequired();
    	/**
    	 * Whether the Intune Managed Browser is required to open web links.
    	 *
    	 * @return True if the Managed Browser is required, false otherwise
    	 */
    	boolean getIsManagedBrowserRequired();
    }

## Enable IT admin control over app saving behavior

Many apps implement features that allow the end user to save files locally or to another service. The Intune App SDK allows IT admins to protect against data leakage by applying policy restrictions as they see fit in their organization.  One of the policies that admin can control is if the end user can save to a personal data store. This includes saving to a local location, SD card, or backup services. App participation is needed to enable the feature. If your app allows saving to personal or cloud locations directly from the app, you must implement this feature to ensure that the IT admin can control whether saving to a location is allowed or not. The API below lets the app know whether saving to a personal store is allowed per the current admin policy. The app can then enforce the policy, since it is aware of personal data store available to the end user through the app.  

To determine if the policy is enforced, the app can make the following call: 

    MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();

**Note**: MAMComponents.get(AppPolicy.class) will always return a non-null App Policy, even if the device or app is not under management. 

## Allow app to detect if PIN Policy is required
 
 There are additional policies where the app may wish to disable some of its functionality so as to not duplicate functionality in the Intune App SDK. For example, if the app has its own PIN user experience, it may wish to disable it if the SDK is configured to require that the end user enter a PIN. 

To determine if PIN policy is configured to require PIN entry periodically, the app can make the following call: 

    MAMComponents.get(AppPolicy.class).getIsPinRequired();

## Registering for notifications from the SDK  

The Intune App SDK allows your app to have control over the behavior when certain policies, such as a remote wipe policy, are used by the IT admin. To do so, you will need to register for notifications from SDK by creating a `MAMNotificationReceiver` class and  registering it with `MAMNotificationReceiverRegistry`. This is done by providing the receiver and the type of notification the receiver wants to receive in  `App.onCreate`, as the example below illustrates:
 
    @Override
	  public void onCreate() {
		    super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class).registerReceiver(
    new ToastNotificationReceiver(), MAMNotificationType.WIPE_USER_DATA);
    }

`MAMNotificationReceiver` simply receives notifications. Some notifications are handled by the SDK directly, others require participation of the app. An app must return either true or false from a notification. It must always return true unless some action it tried to take as a result of the notification failed. This failure may be reported to the Intune service, such as if the app indicates it failed to wipe user data. It is safe to block in `MAMNotificationReceiver.onReceive`; its callback is not running on the UI thread. 

The `MAMNotificationReceiver interface is included below as defined in the SDK: 

    /**
     * The SDK is signaling that a MAM event has occurred. 
     * 
     */
    public interface MAMNotificationReceiver {
	  /**
	  * A notification was received.
	  * 
	  * @param notification
	  *            The notification that was received.
    * @return The receiver should return true if it handled the
    *   notification without error (or if it decided to ignore the
  	*   notification). If the receiver tried to take some action in 
    *   response to the notification but failed to complete that
	  *   action it should return false.
	  */
	  boolean onReceive(MAMNotification notification);
    }

The following notifications are sent to the app and some of them may require app participation: 

* **`WIPE_USER_DATA` notification**: This notification is sent in a `MAMUserNotification` class. When this notification is received, the app should delete all data associated with the identity passed with the `MAMUserNotification`. This notification is currently sent during Intune Service un-enrollment. The user's primary name is typically specified during the enrollment process. If you register for this notification, your app must ensure that all user data has been deleted. If you don't register for it, the default selective wipe behavior will be performed. 

* **`WIPE_USER_AUXILIARY_DATA` notification**: Apps can register for this notification if they'd like the Intune App SDK to perform the default wipe, but would still like to remove some auxiliary data when the wipe occurs.  

* **`REFRESH_POLICY` notification**: This notification is sent in a MAMNotification without any additional information. When this notification is received, any cached policy must  be considered no longer invalidated and therefore should check what the policy is. This is generally handled by the SDK, however should be handled by the app if the policy is used in any persistent way. 

## Pending Intents and methods 

After deriving from one of the MAM entry points, you can use the Context as you would normally, for starting Activities, using its `PackageManager`, etc.  `PendingIntents` are an exception to this rule. When calling such classes, you need to change the class name. For example, instead of using `PendingIntent.get*`, `MAMPendingIntents.get*` must be used. 

In some cases, a method available in the Android class has been marked as final in the MAM replacement class. In this case, the MAM replacement class provides a similarly named method (generally suffixed with "MAM") which should be overridden instead. For example, instead of overriding `ContentProvider.query`, you would override `MAMContentProvider.queryMAM`. The Java compiler should enforce the final restrictions to prevent accidental override of the original method instead of the MAM equivalent. 

# Protecting Backup data 

As of Android Marshmallow (API 23), Android now has two ways for an app to back up its data. these options are available for use in your app and require different steps to ensure that MAM data protection is applied appropriately. You can review the table below for quick overview on corresponding actions required for correct data protection behavior.  You can also find more on Android backup in the [Android Developer Data Backup guide](http://developer.android.com/guide/topics/data/backup.html.). 

## Automatic full backup

In Android M, Android began offering automatic full backups to apps regardless of target API when running on an Android M device. As long as the `android:allowBackup` attribute is not false, an app will receive full, unfiltered backups of their app. This poses a data leak risk, therefore the SDK require the changes outlined in the table below to ensure that data protection is applied.  It is important to follow the guidelines outlined below to protect customer data properly.  If you set `android:allowBackup=false` then your app  will never be queued for backups by the operating system and you have no further actions for MAM, since there will be no backup
 
 ## “key/value” backups

This option is available to all APIs and uses `BackupAgent` and `BackupAgentHelper`. 

### Using BackupAgentHelper

`BackupAgentHelper` is much simpler to implement than `BackupAgent` both in terms of native Android functionality and MAM integration. `BackupAgentHelper` allows the developer to register entire files and shared preferences to either a `FileBackupHelper` or `SharedPreferencesBackupHelper`, respectively, which are then added to the `BackupAgentHelper` upon creation. 

### Using BackupAgent

`BackupAgent` allows you to be much more explicit about what data is backed up. However, this options will mean that you will not be able to take advantage of the Android backup framework.  Because you are fairly responsible for the implementation, there are more steps required to ensure appropriate data protection from MAM. Since most of the work is pushed onto you, the developer, MAM integration is slightly more involved. 

#### App does not have a backup agent
  
These are the developer options when `Android:allowbBackup =true`:

##### Full back up according to a configuration file: 

Provide a resource under the `com.microsoft.intune.mam.FullBackupContent` metadata tag in your manifest. e.g.:
    `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Add the following attribute in the `<application>` tag: `android:fullBackupContent="@xml/my_scheme"`, where `my_scheme` is an XML resource in your app. 

##### Full back dup without exclusions 

Provide a tag in the manifest such as `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />` 
 
Add the following attribute in the `<application>` tag: 
`android:fullBackupContent="true"`.

#### App has a backup agent

Follow the recommendations in the `BackupAgent` and `BackupAgentHelper` sections as outlined above 

Consider switching to using our `MAMDefaultFullBackupAgent`, which provides easy back up on Android M. 

### Before your backup

Before beginning your backup, you must check that the files or data buffers you are planning on backing up are indeed allowed to be backed up. We've provided you with an `isBackupAllowed` function in `MAMFileProtectionManager` and `MAMDataProtectionManager` to determine this. If the file or data buffer is not allowed to be backed up then you should not attempt to continue utilizing it in your backup.

At some point during your backup, if you want the identities for the files you checked in step 1 backed up, you must call `backupMAMFileIdentity(BackupDataOutput data, File … files)` with the files you plan to extract data from. This will automatically create new backup entities and write them to the `BackupDataOutput` for you. These entities will be automatically consumed upon restore. 

## Configure Azure Directory Authentication Library (ADAL)  

The SDK relies on ADAL for its authentication and conditional launch scenarios, which requires that apps have some amount of Azure Active Directory configuration. The configuration values are communicated to the SDK via `AndroidManifest` metadata. To configure your app and enable proper authentication, add the following to the app node in the `AndroidManifest`. Some of these configurations are only required if your app uses ADAL for authentication in general; in that case, you will need the specific values that your app use to register itself with AAD. This is done to ensure that the end user does not get prompted for authentication twice due to AAD recognizing two separate registration values: one from the app and one from the SDK. 

        <meta-data
            android:name="com.microsoft.intune.mam.aad.Authority"
            android:value="https://AAD authority/" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.ClientID"
            android:value="your-client-ID-GUID" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.NonBrokerRedirectURI"
            android:value="your-redirect-URI" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.SkipBroker"
            android:value="[true | false]" />

The GUIDs are not expected to have the preceding or trailing curly bracket.

### Common ADAL configurations 

The following are common configuration for the values explained above. 

#### App does not integrate ADAL

* The authority must  be set to the desired environment where AAD accounts have been configured.

* SkipBroker must be set to true.

#### App integrates ADAL

* The authority must be set to the desired environment where AAD accounts have been configured.

* Client ID must be set to the app's client ID.

* `NonBrokerRedirectURI` should be set to a valid redirect URI for the app.
    * Or `urn:ietf:wg:oauth:2.0:oob` must be configured as a valid AAD redirect URI.

* SkipBroker must be set to false (or be absent)

* AAD must be configured to accept the broker redirect URI.

#### App integrates ADAL but does not support the AAD Authenticator app.

* The authority must be set to the desired environment where AAD accounts have been configured.

* Client ID must be set to the app's client ID.

* `NonBrokerRedirectURI` must be set to a valid redirect URI for the app.

    * Or `urn:ietf:wg:oauth:2.0:oob` should be configured as a valid AAD redirect URI.

## How to enable logging in the SDK 

Logging is done through the `java.util.logging` framework. To receive the logs, set up global logging as described in the [Java technical guide](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). Depending on the app, `App.onCreate` is usually the best place  to initiate logging. Please note that Log messages are keyed by the class name, which may be obfuscated.

# Known Platform Limitations 

## File Size Limitations 

On Android, the limitations of the Dalvik executable file format may become an issue for large code bases that run without ProGuard. Specifically, the following limitations may  occur: 

* The 65K limit on fields.

* The 65K limit on methods.

When including many projects, every android:package will get a copy of R  which will dramatically increase the number of fields as libraries are added. The following recommendations may help mitigate this limitation:
 
* All library projects should share the same android:package where possible. This will not sporadically fail in the field, since it is purely a build-time problem.   In addition, newer versions of the Android SDK will pre-process DEX files to remove some of the redundancy. This lowers the distance from the fields even further.

* Use the newest Android SDK build tools available.

* Remove all unnecessary and unused libraries (e.g. `android.support.v4`)

## Policy Enforcement Limitations

**Screen Capture**: The SDK is unable to enforce a new screen capture setting value in Activities that have already gone through Activity.onCreate. This can result in a period of time where the app has been configured to disable screenshots but screenshots can still be taken.

**Using Content Resolvers*: The transfer or receive policy may block or partially block the use of a content resolver to access the content provider in another app. This will cause ContentResolver methods to return null or throw a failure value (e.g. `openOutputStream` will throw `FileNotFoundException` if blocked). The app can determine whether a failure to write data through a content resolver was caused by policy (or would be caused by policy) by making the call:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Exported Services**: The `AndroidManifest.xml` file included in the Intune App SDK contains `MAMNotificationReceiverService`, which must be an exported service to allow the Company Portal to send notifications to an enlightened app. The service checks the caller to ensure that only the Company Portal is allowed to send notifications. 

# Recommended Android Best Practices 

The Intune SDK maintains the contract provided by the Android API, though failure conditions may be triggered more frequently as a result of policy enforcement. These Android best practices will reduce the likelihood of failure: 

* Android SDK Functions that may return null have a higher likelihood of being null now.  To minimize issues, ensure that null checks are in the right places.

* Features that can be checked for must be checked for through their SDK APIs.

* Any derived functions must call through to their super class versions.

* Avoid use of any API in an ambiguous way. For example, `Activity.startActivityForResult/onActivityResult` without checking the requestCode will cause strange behavior.
