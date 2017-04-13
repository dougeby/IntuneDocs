---
# required metadata

title: Microsoft Intune App SDK for Android developer guide | Microsoft Docs
description: The Microsoft Intune App SDK for Android lets you incorporate Intune mobile app management (MAM) into your Android app.
keywords: SDK
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/15/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: oydang
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---


# Microsoft Intune App SDK for Android developer guide

> [!NOTE]
> You might want to first read the [Intune App SDK overview](intune-app-sdk.md), which covers the current features of the SDK and describes how to prepare for integration on each supported platform.

The Microsoft Intune App SDK for Android lets you incorporate Intune mobile app management (MAM) into your Android app. A MAM-enabled application is one that's integrated with the Intune App SDK. It lets IT admins deploy policies to your mobile app when Intune actively manages the app.

## What's in the SDK

The Intune App SDK for Android is a standard Android library with no external dependencies. The SDK consists of:  

* **Microsoft.Intune.MAM.SDK.jar**: The interfaces necessary to enable MAM and  interoperability with the Intune Company Portal app. Apps must specify it as an Android library reference.

* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: The interfaces necessary to enable MAM in apps that use the Android v4 support library. Apps that need this support must reference the JAR file directly.

* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: The interfaces necessary to enable MAM in apps that use the Android v7 support library. Apps that need this support must reference the JAR file directly.

* **The resource directory**: The resources (like strings) on which the SDK relies.

* **Microsoft.Intune.MAM.SDK.aar**: The SDK components, with the exception of the Support.V4 and Support.V7 JAR files. This file can be used in place of the individual components if your build system supports AAR files.

* **AndroidManifest.xml**: The additional entry points and the library requirements.

* **THIRDPARTYNOTICES.TXT**:  An attribution notice that acknowledges third-party and/or OSS code that will be compiled into your app.

## Requirements

The Intune App SDK is a compiled Android project. As a result, it's largely unaffected by the version of Android that the app uses for its minimum or target API versions. The SDK supports Android API 14 (Android 4.0+) to Android API 24.

The Intune App SDK for Android relies on the presence of the [Company Portal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) app on the device for enabling MAM policies. For MAM without device enrollment, the user is *not* required to enroll the device by using the Company Portal app.


## How the Intune App SDK works

###Entry points

The Intune App SDK requires changes to an app's source code to enable Intune app management policies. This is done through the replacement of the Android base classes with equivalent Intune base classes, whose names have the prefix `MAM`. The SDK classes live between the Android base class and the app's own derived version of that class. Using an activity as an example, you end up with an inheritance hierarchy that looks like: `Activity` > `MAMActivity` > `AppSpecificActivity`.

For example, when `AppSpecificActivity` interacts with its parent (for example, calling `super.onCreate()`), `MAMActivity` is the super class.

Typical Android apps have a single mode and can access the system through their [Context](https://developer.android.com/reference/android/content/Context.html) object. Apps that have incorporated the Intune App SDK, on the other hand, have dual modes. These apps continue to access the system through the `Context` object. Depending on the base `Activity` used, the `Context` object will be provided by Android or will intelligently multiplex between a restricted view of the system and the Android-provided `Context`.

When an Android [entry point](https://developer.android.com/guide/components/fundamentals.html) has been overridden by its MAM equivalent, the MAM version of the entry point's lifecycle must be used (with the exception of the class `MAMApplication`).

For example, when deriving from `MAMActivity`, instead of overriding `onCreate` and calling `super.onCreate`, `Activity` must override `onMAMCreate` and call `super.onMAMCreate`. This lets Intune restrict `Activity` launch (among others) in certain cases.


###SDK permissions

The Intune App SDK requires three [Android system permissions](https://developer.android.com/guide/topics/security/permissions.html) on apps that integrate it:

* `android.permission.GET_ACCOUNTS`  (requested at runtime if required)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

The Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) requires these permissions to perform brokered authentication. If these permissions are not granted to the app or are revoked by the user, authentication flows that require the broker (the Company Portal app) will be disabled.


###Company Portal app

Why is the Company Portal app required? When the Company Portal app is installed onto the device and has retrieved an application restriction policy for the user from the Intune service, the SDK entry points are initialized asynchronously. Initialization is required only when Android initially creates the process. During initialization, a connection is established with the Company Portal app, and the policy is retrieved from the app.  

> [!NOTE]
> When the Company Portal app is not on the device, the behavior of the Intune-enabled app will not be altered and will behave as a normal app.


## How to integrate with the Intune App SDK

As stated earlier, the SDK requires changes to the app's source code to enable app management policies. Here are the steps necessary to enable MAM in your  app.

### Replace classes, methods, and activities with their MAM equivalent (required)

Android base classes must be replaced with their respective MAM equivalents. To do so, find all instances of the classes listed in the following table and replace them with the Intune App SDK equivalent.

| Android base class | Intune App SDK replacement |
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
| android.app.PendingIntent | MAMPendingIntent* |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | MAMBinder (necessary only if Binder is not generated from an Android Interface Definition Language (AIDL) interface) |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


**Microsoft.Intune.MAM.SDK.Support.v4.jar**:

| Android class	Intune MAM | Intune App SDK replacement |
|--|--|
| android.support.v4.app.DialogFragment | MAMDialogFragment
| android.support.v4.app.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| android.support.v4.content.FileProvider | MAMFileProvider

**Microsoft.Intune.MAM.SDK.Support.v7.jar**:

|Android class | Intune App SDK replacement |
|--|--|
|android.support.v7.app.ActionBarActivity | MAMActionBarActivity |

>[!NOTE]
>Remember--when an Android [entry point](https://developer.android.com/guide/components/fundamentals.html) has been overridden by its MAM equivalent, the MAM version of the entry point's lifecycle must be used (with the exception of the class `MAMApplication`).
>
>For example, when deriving from `MAMActivity`, instead of overriding `onCreate` and calling `super.onCreate`, `Activity` must override `onMAMCreate` and call `super.onMAMCreate`. This lets Intune restrict `Activity` launch (among others) in certain cases.

#### PendingIntent classes and renamed methods

After you derive from one of the MAM entry points, it's safe to use `Context` as you would normally--for example, starting `Activity` classes and using `PackageManager`.  

`PendingIntent` classes are an exception to this rule. When you're calling such classes, you need to change the class name. For example, instead of `PendingIntent.get*`, you must use the `MAMPendingIntent.get*` method. After this, you can use the resultant `PendingIntent` as usual.

In some cases, a method available in the Android class has been marked as final in the MAM replacement class. In this case, the MAM replacement class provides a similarly named method (generally suffixed with `MAM`) that you should override instead. For example, instead of overriding `ContentProvider.query`, you would override `MAMContentProvider.queryMAM`. The Java compiler should enforce the final restrictions to prevent accidental override of the original method instead of the MAM equivalent.

###Enable features that require app participation

The SDK cannot implement some policies on its own. The app can control its behavior to achieve these features by using several APIs that you can find in the following `AppPolicy` interface.

```
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * <strong>This function is now deprecated. Please use {@link #getIsSaveToLocationAllowed(SaveLocation, String)} instead</strong>
 * @return True if the app is allowed to save to personal data stores; false otherwise.
 */
@Deprecated
boolean getIsSaveToPersonalAllowed();

/**
 * Check if policy prohibits saving to a content provider location.
 *
 * @param location
 *            a content URI to check
 * @return True if location is not a content URI or if policy does not prohibit saving to the content location.
 */
boolean getIsSaveToLocationAllowed(Uri location);

/**
 * Determines if the SaveLocation passed in can be saved to by the username associated with the cloud service.
 *
 * @param service
 *           see {@link SaveLocation}.
 * @param username
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between the AAD username and the cloud service username does not exist or the username is not known.
 * @return true if the location can be saved to by the identity, false if otherwise.
 */
boolean getIsSaveToLocationAllowed(SaveLocation service, String username);

/**
 * Whether the SDK PIN prompt is enabled for the app.
 *
 * @return True if the PIN is enabled. False otherwise.
 */
boolean getIsPinRequired();

/**
 * Whether the Intune Managed Browser is required to open web links.
 * @return True if the Managed Browser is required, false otherwise
 */
boolean getIsManagedBrowserRequired();

/**
 * Check if policy allows Contact sync to local contact list.
 *
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();


}

```

### Enable IT control over app saving behavior

Many apps implement features that let the user save files locally or to a cloud storage service. The Intune App SDK helps IT admins protect against data leakage by applying policy restrictions as they see fit in their organization.  One of the policies that IT can control is whether the user can save to a "personal," unmanaged data store. This includes saving to a local location, an SD card, or third-party backup services.

App participation is needed to enable the feature. If your app allows saving to personal or cloud locations directly from the app, you must implement this feature to ensure that the IT admin can control whether saving to a location is allowed.   

To determine if the policy is enforced, the app can make the following call. This call lets the app know whether the current Intune admin's policy allows saving to a personal store. The app can then enforce the policy, because it is aware of the personal data store available to the user through the app.

```
MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();
```

> [!NOTE]
> `MAMComponents.get(AppPolicy.class)` will always return a non-null app policy, even if the device or app is not under an Intune management policy.

### Let the app detect if a PIN policy is required

For some Intune app restrictions, you might want your app to disable some of its functionality so it doesn't duplicate functionality in the Intune App SDK. For example, if the app has its own PIN user experience, you might want to disable it if the SDK is set up to require the user to enter a PIN.

To determine if an Intune PIN policy is set up to require an app PIN on launch, the app can make this call:

```
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

### Register for notifications from the SDK  

The Intune App SDK lets your app control the behavior of certain policies, like a selective wipe, when the IT admin deploys them. When an IT admin deploys such a policy, the Intune service sends a notification to the SDK.

Your app must register for notifications from the SDK by creating a `MAMNotificationReceiver` class and registering it with `MAMNotificationReceiverRegistry`. This is done by providing the receiver and the type of notification desired in `App.onCreate`, as this example illustrates:

```
@Override
public void onCreate() {
	super.onCreate();
	MAMComponents.get(MAMNotificationReceiverRegistry.class)
.registerReceiver(
				new ToastNotificationReceiver(),
MAMNotificationType.WIPE_USER_DATA);
	}
```

`MAMNotificationReceiver` simply receives notifications from the Intune service. The SDK handles some notifications directly. Other notifications require the app's participation.

An app *must* return either true or false from a notification. It must always return true unless some action that it tried to take as a result of the notification failed. This failure might be reported to the Intune service. An example of a scenario to report is if the app fails to wipe user data after the IT admin initiates a wipe.

It is safe to block in `MAMNotificationReceiver.onReceive` because its callback is not running on the UI thread.

The following `MAMNotificationReceiver` interface is defined in the SDK:

```
/**
 * The SDK is signaling that a WG event has occurred.
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

```

###Types of notifications

The following notifications are sent to the app. Some of them might require app participation.

* **`WIPE_USER_DATA`**: This notification is sent in a `MAMUserNotification` class. When this notification is received, the app is expected to delete all data associated with the "corporate" identity passed with `MAMUserNotification`. This notification is currently sent during Intune service unenrollment. The user's primary name is typically specified during the enrollment process. If you register for this notification, your app must ensure that all the user's data has been deleted. If you don't register for it, the app will perform the default selective wipe behavior.

* **`WIPE_USER_AUXILIARY_DATA`**: Apps can register for this notification if they want the Intune App SDK to perform the default selective wipe behavior, but they still want to remove some auxiliary data when the wipe occurs.  

* **`REFRESH_POLICY`**: This notification is sent in `MAMUserNotification`. When this notification is received, any cached Intune policy must be invalidated and updated. The SDK generally handles this task. But the app should handle this task if the policy is used in any persistent way.



### Protection of backup data

As of Android Marshmallow (API 23), Android has two ways for an app to back up its data. Each option is available to your app and requires different steps to ensure that Intune data protection is correctly implemented. You can read more about the backup methods in the [Android API guide](http://developer.android.com/guide/topics/data/backup.html).

#### Automatic backup for apps

Android began offering [automatic full backups](https://developer.android.com/guide/topics/data/autobackup.html) to apps on Android Marshmallow devices, regardless of the app's target API. If you explicitly set `android:allowBackup` to false in your AndroidManifest.xml file, Android will never queue your app for backups, and "corporate" data will stay within the app. In this case, no further action is necessary.

By default, the `android:allowBackup` attribute is set to true, even if `android:allowBackup` isn't specified in the manifest file. This means all app data is automatically backed up to the user's Google Drive account, a default behavior that poses a *data leak risk*. The SDK requires the following changes to ensure that data protection is applied. It's important to follow these guidelines to protect customer data properly if you want your app to run on Android Marshmallow devices.  

If you have not written a backup agent to back up your app by using `MAMBackupAgent` or `MAMBackupAgentHelper`, you must consider and control how Auto Backup will upload your app data. Intune lets you use all the [Auto Backup features](https://developer.android.com/guide/topics/data/autobackup.html) available from Android, including the ability to define custom rules in XML. But you must follow these steps to help secure your data:

1. Use the default `MAMBackupAgent` to allow for automatic full backups that are Intune policy compliant. Put `android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"` in your app manifest.

2. When you decide which type of full backup your app should receive (unfiltered, filtered, or none), set the attribute `android:fullBackupContent` to true, false, or an XML resource in your app. Copy whatever you put into `android:fullBackupContent` into a metadata tag named `com.microsoft.intune.mam.FullBackupContent`.

	For example, if you want your app to have full backups according to your custom rules in an XML file, provide a resource under the `com.microsoft.intune.mam.FullBackupContent` metadata tag in your manifest like this:
	```
	<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
	```



#### Key/value backup

The key/value backup option is available to all APIs and uses `BackupAgentHelper` and `BackupAgent`.

##### BackupAgentHelper

`BackupAgentHelper` is much simpler to implement than `BackupAgent`, in terms of both native Android functionality and MAM integration. `BackupAgentHelper` lets you register entire files and shared preferences to either `FileBackupHelper` or `SharedPreferencesBackupHelper`, respectively. These are then added to `BackupAgentHelper` upon creation.

##### BackupAgent

`BackupAgent` lets you be much more explicit about what data is backed up. But this option will mean that you can't take advantage of the Android backup framework. Because you are responsible for the implementation, more steps are required to ensure appropriate data protection from MAM. Because most of the work is pushed onto you, the developer, MAM integration is slightly more involved.

###### App does not have a backup agent

These are the developer options when `android:allowBackup =true`.

####### Full backup according to a configuration file

Provide a resource under the `com.microsoft.intune.mam.FullBackupContent` metadata tag in your manifest. For example:
    `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Add the following attribute in the `<application>` tag: `android:fullBackupContent="@xml/my_scheme"`, where `my_scheme` is an XML resource in your app.

####### Full backup without exclusions

Provide a tag in the manifest, like `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />`.

Add the following attribute in the `<application>` tag:
`android:fullBackupContent="true"`.

###### App has a backup agent

Follow the recommendations earlier in this guide for `BackupAgent` and `BackupAgentHelper`.

Consider switching to using `MAMDefaultFullBackupAgent`, which provides easy backup on Android Marshmallow.

##### Before your backup

Before you begin your backup, you must check that the files or data buffers that you plan to back up are allowed to be backed up. We've given you an `isBackupAllowed` function in `MAMFileProtectionManager` and `MAMDataProtectionManager` to check this. If the file or data buffer is not allowed to be backed up, you should not try to continue using it in your backup.

At some point during your backup, if you want to back up the identities for the files that you checked in step 1, you must call `backupMAMFileIdentity(BackupDataOutput data, File … files)` with the files that you plan to extract data from. This will automatically create new backup entities and write them to `BackupDataOutput` for you. These entities will be automatically consumed upon restore.

#### Azure Directory Authentication Library setup  

The SDK relies on ADAL for its authentication and conditional launch scenarios. These scenarios require that apps have some amount of Azure Active Directory (Azure AD) configuration. The configuration values are communicated to the SDK via `AndroidManifest` metadata.

To set up your app and enable proper authentication, add the following to the app node in `AndroidManifest`. Some of these configurations are required only if your app uses ADAL for authentication in general. In that case, you will need the specific values that your app used to register itself with Azure AD. This ensures that the user isn't prompted for authentication twice because Azure AD recognizes two separate registration values: one from the app and one from the SDK.

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

##### Common ADAL configurations

The following are common configurations for the values explained earlier.

###### App does not integrate ADAL

* The authority must be set to the desired environment where Azure AD accounts have been set up.

* SkipBroker must be set to true.

###### App integrates ADAL

* The authority must be set to the desired environment where Azure AD accounts have been set up.

* Client ID must be set to the app's client ID.

* `NonBrokerRedirectURI` should be set to a valid redirect URI for the app. Or, `urn:ietf:wg:oauth:2.0:oob` must be set up as a valid Azure AD redirect URI.

* SkipBroker must be set to false (or be absent).

* Azure AD must be set up to accept the broker redirect URI.

###### App integrates ADAL but does not support the Azure AD Authenticator app

* The authority must be set to the desired environment where Azure AD accounts have been set up.

* Client ID must be set to the app's client ID.

* `NonBrokerRedirectURI` must be set to a valid redirect URI for the app. Or, `urn:ietf:wg:oauth:2.0:oob` should be set up as a valid Azure AD redirect URI.

#### Logging in the SDK

Logging is done through the `java.util.logging` framework. To receive the logs, set up global logging as described in the [Java technical guide](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). Depending on the app, `App.onCreate` is usually the best place to initiate logging. Note that log messages are keyed by the class name, which might be hidden.

###Multi-identity

By default, the Intune App SDK applies a policy to the app as a whole. Multi-identity is a MAM feature that you can enable to apply a policy on a per-identity level. This requires significantly more app participation than other MAM features. The app is required to inform the app SDK when it intends to change the active identity. The SDK must also notify the app when an identity change is required.

Currently, only one managed identity is supported. After the user enrolls the device or the app, the SDK uses this identity and considers it the primary managed identity. Other users in the app are treated as unmanaged with unrestricted policy settings.

Note that an identity is simply defined as a string. Identities are case-insensitive. Requests to the SDK for an identity might not return the same casing that was originally used when the identity was set.

####Enabling multi-identity

By default, all apps are considered to be single-identity apps. An app declares that it is multi-identity aware by placing the following metadata in the Android manifest.

```
<meta-data
            android:name="com.microsoft.intune.mam.MAMMultiIdentity"
            android:value="true" />
```
####Setting the identity

You can set the identity of the app on the following levels:

1. Process level

2. Context (generally `Activity`) level

3. Thread level

An identity set at the thread level supersedes an identity set at the `Context` level, which supersedes an identity set at the process level. An identity set on `Context` is used only when appropriate. File I/O tasks, for example, do not have an associated `Context`. You can use the following methods on `MAMPolicyManager` to set the identity and retrieve the identity values previously set.

```
public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

public static String getUIPolicyIdentity(final Context context);

public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

public static String getProcessIdentity();

public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

public static String getCurrentThreadIdentity();

/**
 * Get the currently applicable app policy. Same as MAMComponents.get(AppPolicy.class). This method does
	not take the context identity into account.
 */
public static AppPolicy getPolicy();

/**
 * Get the currently applicable app policy, taking the context
 * identity into account.
 */
public static AppPolicy getPolicy(final Context context);


public static AppPolicy getPolicyForIdentity(final String identity);

public static boolean getIsIdentityManaged(final String identity);

```
You can also clear the identity of the app by setting it to null. The empty string can be used as an identity that will never have restrictions. All of the methods to set the identity report back result values via ``` MAMIdentitySwitchResult```. Four values can be returned:

* **SUCCEEDED**: The identity change was successful.

* **NOT_ALLOWED**: The identity change is not allowed. This will occur if an attempt is made to switch to a different corporate user who belongs to the same company as the enrolled user. It will also occur if an attempt is made to set the UI (`Context`) identity when a different identity is set on the current thread.

* **CANCELLED**: The user canceled the identity change, generally by choosing the back button on a PIN/auth prompt.

* **FAILED**: The identity change failed for an unspecified reason.

In the case of setting a `Context` identity, the result is reported asynchronously. If `Context` is an `Activity` class, it will not be known if the identity change succeeded until after conditional launch. A conditional launch might require the user to enter a PIN or their full corporate credentials. The app is expected to implement ```MAMSetUIIdentityCallback``` to receive this result, although it is permissible to pass null for this parameter.

```
public interface MAMSetUIIdentityCallback {
	void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
}
```

You can also set the identity of an activity directly through a method on `MAMActivity`, instead of calling ```MAMPolicyManager.setUIPolicyIdentity``` . You can do so by using the following method:

 ```public final void switchMAMIdentity(final String newIdentity);```

Apps can also override a method on `MAMActivity` to be notified of the result of attempts to change the identity of that activity.

```public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);```

> [!NOTE]
> Switching the identity might require re-creating the activity. In this case, the ```onSwitchMAMIdentityComplete``` callback will be delivered to the new instance of the activity.


####Implicit identity changes

In addition to the app's ability to set the identity, a thread or a context's identity might change based on data ingress from another MAM-enabled app. For instance, if an activity is launched from an `Intent` class sent by another MAM app, the activity’s identity will be set based on the effective identity in the other app at the point where the `Intent` class was sent.

For services, the thread's identity will be set similarly for the duration of an `onStart` or `onBind` call. Calls into `Binder` returned from `onBind` will also temporarily set the thread identity. Calls into a ```ContentProvider``` will similarly set the thread identity for their duration.

In addition, user interaction with an activity might cause an implicit identity switch. For instance, a user canceling out of an authorization prompt during ```Resume``` will result in an implicit switch to an empty identity.
The app has an opportunity to be made aware of these changes, and in some cases, forbid them if necessary. ```MAMService``` and ```MAMContentProvider``` expose the following method, which subclasses can override:

```
public void onMAMIdentitySwitchRequired(final String identity,
	final AppIdentitySwitchResultCallback callback);
```
In the case of ```MAMActivity```, an additional parameter is present in the method:
```
public void onMAMIdentitySwitchRequired(final String identity,
	final AppIdentitySwitchReason reason,
	final AppIdentitySwitchResultCallback callback);
```
The ```AppIdentitySwitchReason``` part captures the source of the implicit switch. It can accept the values ```CREATE```, ```RESUME_CANCELLED```, and ```NEW_INTENT```.  The ```RESUME_CANCELLED``` reason is used when resuming an activity causes PIN, authentication, or other compliance UI to be shown and the user attempts to cancel out of that UI, generally though use of the back button.
```AppIdentitySwitchResultCallback``` is as follows:
```
public interface AppIdentitySwitchResultCallback {
	/**
	 * @param result
	 *            whether the identity switch can proceed.
	 */
	void reportIdentitySwitchResult(AppIdentitySwitchResult result);
}
```
```AppIdentitySwitchResult``` is either ```SUCCESS``` or ```FAILURE```.

The method ```onMAMIdentitySwitchRequired``` is called for all implicit identity changes, except for those made through a `Binder` class returned from ```MAMService.onMAMBind```. The default implementation of ```onMAMIdentitySwitchRequired``` immediately calls ```reportIdentitySwitchResult(FAILURE)``` when the reason is ```RESUME_CANCELLED```, and ```reportIdentitySwitchResult(SUCCESS)``` in all other cases.

Most apps probably won't need to block or delay an identity switch in a different manner. But if an app needs to do so, consider the following points:

* If an identity switch is blocked, the result is the same as if ```Receive``` sharing settings had prohibited the data ingress.

* If a service is running on the main thread, ```reportIdentitySwitchResult``` *must* be called synchronously or the UI thread will hang.

* For ```Activity``` creation, ```onMAMIdentitySwitchRequired``` will be called before ```onMAMCreate```. If the app must show UI to check whether to allow the identity switch, that UI must be shown using a different activity.

* In ```Activity```, when a switch to the empty identity is requested with reason equal to ```RESUME_CANCELLED```, the app must change the resumed activity to show data consistent with that identity switch. If this is not possible, the app should refuse the switch. And the user will be asked again to comply with policy for the resuming identity (for example, by being presented with the PIN entry screen).

> [!NOTE]
> A multi-identity app will always receive incoming data from both managed and unmanaged apps. The app is responsible for treating data from managed identities in a managed manner. If a requested identity is managed ```(MAMPolicyManager.getIsIdentityManaged)```, but the app can't use that account (for example, because accounts like email accounts must be set up in the app first), the identity switch should be refused.

###File protection

Every file has an identity associated with it at the time of creation, based on thread and process identity. This identity is used for both file encryption and selective wipe. Only files whose identity has a policy that requires encryption will be encrypted. The SDK's default selective wipe will wipe only files associated with the identity for which a wipe has been requested. The app can query or change a file’s identity by using ```MAMFileProtectionManager```.
```
public final class MAMFileProtectionManager {

	/**
	 * Protect a file. This will synchronously trigger whatever protection is required for the file, and will tag the file for
	 * future protection changes.
	 *
	 * @param identity
	 *            Identity to set.
	 * @param file
	 *            File to protect.
	 * @throws IOException
	 *             If the file cannot be changed.
	 */
	public static void protect(final File file, final String identity) throws IOException;

	/**
	 * Get the protection info on a file.
	 *
	 * @param file
	 *            File or directory to get information on.
	 * @return File protection info, or null if there is no protection info.
	 * @throws IOException
	 *             If the file cannot be read or opened.
	 */
	public static MAMFileProtectionInfo getProtectionInfo(final File file) throws IOException;
}

public interface MAMFileProtectionInfo {
String getIdentity();
}
```

> [!NOTE]
> File identity tagging is sensitive to offline mode. Take the following points into account:
> * If the Company Portal app is not installed, files cannot be identity-tagged.
>
> * If the Company Portal app is installed but the app does not have a policy, files cannot be reliably identity-tagged.
>
> * When file identity tagging becomes available, all previously created files are treated as personal (belonging to the empty-string identity) unless the app was previously installed as a single-identity managed app. In that case, they are treated as belonging to the enrolled user.

####Data protection

It is not possible to tag a file as belonging to multiple identities. Apps that must store data that belongs to different users in the same file can do so manually by using the features that ```MAMDataProtectionManager``` provides. This lets the app encrypt data and tie it to a particular user. The encrypted data is suitable for storing to disk in a file. You can query the data associated with the identity, and the data can be unencrypted later.

```
public final class MAMDataProtectionManager {
	/**
	 * Protect a stream. This will return a stream containing the protected
 * input.
	 *
	 * @param identity
	 *            Identity to set.
	 * @param input
	 *            Input data to protect, read sequentially. This function
 *            will change the position of the stream but may not have
	 *            read the entire stream by the time it returns. The
 *            returned stream will wrap this one. Calls to read on the
	 *            returned stream may cause further reads on the original
 *            input stream. Callers should not expect to read directly
	 *            from the input stream after passing it to this method.
 *            Calling close on the returned stream will close this one.
	 * @return Protected input data.
	 * @throws IOException
	 *             If the data could not be protected
	 */
	public static InputStream protect(final InputStream input, final String identity);

	/**
	 * Protect a byte array. This will return protected bytes.
	 *
	 * @param identity
	 *            Identity to set.
	 * @param input
	 *            Input data to protect.
	 * @return Protected input data.
	 * @throws IOException
	 *             If the data could not be protected
	 */
	public static byte[] protect(final byte[] input, final String identity) throws IOException;

	/**
	 * Unprotect a stream. This will return a stream containing the
 * unprotected input.
	 *
	 * @param input
	 *            Input data to protect, read sequentially.
	 * @return Protected input data.
	 * @throws IOException
	 *             If the data could not be unprotected
	 */
	public static InputStream unprotect(final InputStream input) throws IOException;

	/**
	 * Unprotect a byte array. This will return unprotected bytes.
	 *
	 * @param input
	 *            Input data to protect.
	 * @return Protected input data.
	 * @throws IOException
	 *             If the data could not be unprotected
	 */
	public static byte[] unprotect(final byte[] input) throws IOException;

	/**
	 * Get the protection info on a stream.
	 *
	 * @param input
	 *            Input stream to get information on. Either this input
 *            stream must have been returned by a previous call to
 	 *            protect OR input.markSupported() must return true.
 *            Otherwise it will be impossible to get protection info
 *            without advancing the stream position. The stream must be
 *            positioned at the beginning of the protected data.
	 * @return Data protection info, or null if there is no protection
 *            info.
	 * @throws IOException
	 *             If the input cannot be read.
	 */
	public static MAMDataProtectionInfo getProtectionInfo(final InputStream input) throws IOException;

	/**
	 * Get the protection info on a stream.
	 *
	 * @param input
	 *            Input bytes to get information on. These must be bytes
 *            returned by a previous call to protect() or a copy of
 *            such bytes.
	 * @return Data protection info, or null if there is no protection
 *            info.
	 * @throws IOException
	 *             If the input cannot be read.
	 */
	public static MAMDataProtectionInfo getProtectionInfo(final byte[] input) throws IOException;
}
```
###Content providers

If the app is providing potentially corporate data other than ```ParcelFileDescriptor``` through ```ContentProvider```, the app must call the ```MAMContentProvider``` method ```isProvideContentAllowed(String)```, passing the owner ```UPN``` for the content. If this function returns false, the content cannot be returned to the caller. File descriptors returned through a content provider are handled automatically, based on the file identity.

###Selective wipe

If an app registers for the ```WIPE_USER_DATA``` notification, it will not receive the benefit of SDK default selective wipe behavior. For apps that are multi-identity aware, this might be more significant because MAM default selective wipe will wipe only files that match the identity to be wiped.

If you are building an app that's multi-identity aware, you can register for ```WIPE_USER_AUXILIARY_DATA```. This notification lets you take advantage of the SDK default wipe behavior. This notification will be sent immediately before you perform the SDK default selective wipe. Note that an app should never register for both ```WIPE_USER_DATA``` and ```WIPE_USER_AUXILIARY_DATA```.

### Known platform limitations

#### File size limitations

On Android, the limitations of the Dalvik executable file format might become an issue for large code bases that run without ProGuard. Specifically, the following limitations might  occur:

* The 65,000 limit on fields

* The 65,000 limit on methods

When you're including many projects, every `android:package` will get a copy of R. This will dramatically increase the number of fields as libraries are added. The following recommendations might help mitigate this limitation:

* All library projects should share the same `android:package` where possible. This will not sporadically fail in the field, because it is purely a build-time problem. In addition, newer versions of the Android SDK will preprocess DEX files to remove some of the redundancy. This lowers the distance from the fields even further.

* Use the newest Android SDK build tools available.

* Remove all unnecessary and unused libraries (for example, `android.support.v4`).

#### Policy enforcement limitations

**Screen capture**: The SDK can't enforce a new screen capture setting value in `Activity` classes that have already gone through `Activity.onCreate`. This can result in a period of time where the app has been set up to disable screenshots but screenshots can still be taken.

**Content resolvers**: The transfer or receive policy might block or partially block the use of a content resolver to access the content provider in another app. This will cause `ContentResolver` methods to return null or throw a failure value. (For example, `openOutputStream` will throw `FileNotFoundException` if blocked.) The app can make this call to check whether a policy caused (or might cause) a failure to write data through a content resolver:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Exported services**: The `AndroidManifest.xml` file included in the Intune App SDK has `MAMNotificationReceiverService`. This must be an exported service to let the Company Portal app send notifications to an enlightened app. The service checks the caller to ensure that only the Company Portal app is allowed to send notifications.

### Android best practices

The Intune SDK maintains the contract provided by the Android API, though failure conditions might be triggered more frequently as a result of policy enforcement. These Android best practices will reduce the likelihood of failure:

* Android SDK functions that might return null have a higher likelihood of being null now. To minimize problems, ensure that null checks are in the right places.

* For features that you can check for, use their SDK APIs to check for them.

* Any derived functions must call through to their super-class versions.

* Avoid use of any API in an ambiguous way. For example, using `Activity.startActivityForResult/onActivityResult` without checking `requestCode` will cause strange behavior.
