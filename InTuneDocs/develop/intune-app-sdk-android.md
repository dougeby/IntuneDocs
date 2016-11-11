---
# required metadata

title: Microsoft Intune App SDK for Android Developer Guide | Microsoft Intune
description:
keywords: SDK
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Microsoft Intune App SDK for Android Developer Guide

> [!NOTE]
> You may wish to first read the [Intune App SDK overview](intune-app-sdk.md), which covers the current features of the SDK and describes how to prepare for integration on each supported platform. 

The Microsoft Intune App SDK for Android allows you to incorporate Intune Mobile App Management (MAM) into your Android app. A MAM-enabled application is one integrated with the Intune App SDK, and allows IT administrators to deploy policies to your mobile app when the app is actively managed by Intune.

# What's in the SDK 

The Intune App SDK for Android is a standard Android library with no external dependencies. The SDK is composed of:  

* **Microsoft.Intune.MAM.SDK.jar**: The interfaces necessary to enable MAM and  interoperability with the Intune Company Portal app. Apps must specify it as an Android library reference.

* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: The interfaces necessary to enable MAM in apps that leverage the Android v4 support library.  Apps that need this support must reference the jar file directly. 

* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: The interfaces necessary to enable MAM in apps that leverage the Android v7 support library. Apps that need this support must reference the jar file directly.

* **The resource directory**: The resources (such as strings) on which the SDK relies. 

* **Microsoft.Intune.MAM.SDK.aar**: The SDK components, with the exception of the Support.V4 and Support.V7 jars. This file can be used in place of the individual components if your build system supports AAR files.

* **AndroidManifest.xml**: The additional entry points and the library requirements. 

* **THIRDPARTYNOTICES.TXT**:  An attribution notice that acknowledges 3rd party and/or OSS code that will be compiled into your app. 

# Requirements 

The Intune App SDK is a compiled Android project. As a result, it is largely agnostic to the version of Android the app uses for its minimum or target API versions. The SDK supports Android API 14 (Android 4.0+) to Android API 24. 

The Intune App SDK for Android relies on the presence of the [Company Portal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) app on the device for enabling MAM policies. For MAM without device enrollment, the user is **not** required to enroll the device using Company Portal.


# How the Intune App SDK works 

##Entry Points

The Intune App SDK requires changes to an app's source code to enable Intune app management policies. This is done through the replacement of the Android base classes with equivalent Intune base classes, whose names have the prefix **MAM**. The SDK classes live between the Android base class and the app's own derived version of that class.  Using an activity as an example, you end up with an inheritance hierarchy that looks like: Activity > MAMActivity > AppSpecificActivity.

For example, when **AppSpecificActivity** interacts with its parent (e.g. calling `super.onCreate()`), **MAMActivity** is the super class. 

Typical Android apps have a single mode and can access the system through their [Context](https://developer.android.com/reference/android/content/Context.html) object.  Apps that have incorporated the Intune App SDK, on the other hand, have dual modes. These apps continue to access the system through the Context object, but, depending on the base Activity used, the Context object will either be provided by Android, or will intelligently multiplex between a restricted view of the system and the Android-provided Context.

When using an Android [entry point](https://developer.android.com/guide/components/fundamentals.html) that has been overridden by its MAM equivalent, the MAM version of the entry point's lifecycle must be used (with the exception of the class **MAMApplication**).

For example, when deriving from **MAMActivity**, instead of overriding `onCreate` and calling `super.onCreate`, the Activity must override `onMAMCreate` and call `super.onMAMCreate`. This allows Activity launch (among others) to be restricted by Intune in certain cases. 


##SDK Permissions

The Intune App SDK requires three [Android system permissions](https://developer.android.com/guide/topics/security/permissions.html) on apps that integrate it:

* `android.permission.GET_ACCOUNTS`  [requested at runtime if required]
* `android.permission.MANAGE_ACCOUNTS`
* `android.permission.USE_CREDENTIALS`

These permissions are required by the Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/)) to perform brokered authentication. If these permissions are not granted to the app or are revoked by the user, authentication flows that require the broker (the Company Portal app) will be disabled.


##Company Portal

Why is the Company Portal app required? When the Company Portal is installed onto the device and has retrieved application restriction policy for the user from the Intune service, the SDK entry points are initialized asynchronously. Initialization is only required when the process is initially created by Android. During initialization, a connection is established with Company Portal app, and policy is retrieved from the app.  

> [!NOTE]
> When the Company Portal app is not present on the device, the behavior of the Intune-enabled app will not be altered, and it will behave as a normal app.


# How to integrate with the Intune App SDK
 
As stated earlier, the SDK requires changes to the app's source code to enable app management policies. Here are the steps necessary to enable MAM in your  app: 

## Replace classes, methods, and activities with their MAM equivalent (required) 

Android base classes must be replaced by their respective MAM equivalents. To do so, find all instances of the classes listed in the table below and replace them with the Intune App SDK equivalent. 

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
| android.app.PendingIntent | **MAMPendingIntent** * |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | **MAMBinder** (Only necessary if the Binder is not generated from an Android Interface Definition Language (AIDL) interface) |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


**Microsoft.Intune.MAM.SDK.Support.v4.jar**:

| Android Class	Intune MAM | Intune App SDK replacement |
|--|--|
| android.support.v4.app.DialogFragment | MAMDialogFragment
| android.support.v4.app.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| android.support.v4.content.FileProvider | MAMFileProvider
    
**Microsoft.Intune.MAM.SDK.Support.v7.jar**:

|Android Class | Intune App SDK replacement |
|--|--|
|android.support.v7.app.ActionBarActivity | MAMActionBarActivity |

>[!NOTE]
>Remember -- when using an Android [entry point](https://developer.android.com/guide/components/fundamentals.html) that has been overridden by its MAM equivalent, the MAM version of the entry point's lifecycle must be used (with the exception of the class **MAMApplication**).
>
>For example, when deriving from **MAMActivity**, instead of overriding `onCreate` and calling `super.onCreate`, the Activity must override `onMAMCreate` and call `super.onMAMCreate`. This allows Activity launch (among others) to be restricted by Intune in certain cases. 

### PendingIntents and renamed methods 

After deriving from one of the MAM entry points, it's safe to use the Context as you would normally -- starting Activities, using its **PackageManager**, etc.  

**PendingIntents** are an exception to this rule. When calling such classes, you need to change the class name. For example, instead of  `PendingIntent.get*`, `MAMPendingIntents.get*` method must be used. After this, the resultant **PendingIntents** can be used per usual.

In some cases, a method available in the Android class has been marked as final in the MAM replacement class. In this case, the MAM replacement class provides a similarly named method (generally suffixed with "MAM") which should be overridden instead. For example, instead of overriding `ContentProvider.query`, you would override `MAMContentProvider.queryMAM`. The Java compiler should enforce the final restrictions to prevent accidental override of the original method instead of the MAM equivalent. 

##Enable features that require app participation 

There are some policies the SDK cannot implement on its own. The app can control its behavior to achieve these features using several APIs you can find in the **AppPolicy** interface included below.  

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

## Enable IT control over app saving behavior

Many apps implement features that allow the end user to save files locally or to a cloud storage service. The Intune App SDK allows IT administrators to protect against data leakage by applying policy restrictions as they see fit in their organization.  One of the policies that IT can control is whether the end user can save to a "personal," unmanaged data store. This includes saving to a local location, SD card, or third-party backup services. 

**App participation is needed to enable the feature.** If your app allows saving to personal or cloud locations directly from the app, you must implement this feature to ensure that the IT administrator can control whether saving to a location is allowed. The API below lets the app know whether saving to a personal store is allowed by the current Intune administrator's policy. The app can then enforce the policy, since it is aware of personal data store available to the end user through the app.  

To determine if the policy is enforced, the app can make the following call: 

```
MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();
```

**Note**: `MAMComponents.get(AppPolicy.class)` will always return a non-null App Policy, even if the device or app is not under an Intune management policy. 

## Allow app to detect if PIN Policy is required
 
For some Intune app restrictions, you may want your app to disable some of its functionality so as to not duplicate functionality in the Intune App SDK. For example, if the app has its own PIN user experience, it may wish to disable it if the SDK is configured to require the end user to enter a PIN. 

To determine if an Intune PIN policy is configured to  require an app PIN on launch, the app can make the following call: 

```
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

## Registering for notifications from the SDK  

The Intune App SDK allows your app to control the behavior of certain policies, such as a selective wipe, when they are deployed by the IT administrator. When an IT administrator deploys such a policy, the Intune service sends down a notification to the SDK.

Your app must register for notifications from the SDK by creating a **MAMNotificationReceiver** class and  registering it with **MAMNotificationReceiverRegistry**. This is done by providing the receiver and the type of notification desired in  `App.onCreate`, as the example below illustrates:

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

**MAMNotificationReceiver** simply receives notifications from the Intune service. Some notifications are handled by the SDK directly, while others require the app's participation. 

An app **must** return either true or false from a notification. 

It must always return true unless some action it tried to take as a result of the notification failed. 

* This failure may be reported to the Intune service. An example of a scenario to report is if the app fails to wipe user data after the IT administrator initiates a wipe. 

It is safe to block in `MAMNotificationReceiver.onReceive` because its callback is not running on the UI thread. 

The **MAMNotificationReceiver** interface is included below as defined in the SDK: 

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

##Types of notifications
The following notifications are sent to the app and some of them may require app participation: 

* **`WIPE_USER_DATA`**: This notification is sent in a **MAMUserNotification** class. When this notification is received, the app is expected to delete all data associated with the "corporate" identity passed with the **MAMUserNotification**. This notification is currently sent during Intune Service un-enrollment. The user's primary name is typically specified during the enrollment process. If you register for this notification, your app must ensure that all the user's data has been deleted. If you don't register for it, the default selective wipe behavior will be performed.

* **`WIPE_USER_AUXILIARY_DATA`**: Apps can register for this notification if they'd like the Intune App SDK to perform the default selective wipe behavior, but would still like to remove some auxiliary data when the wipe occurs.  

* **`REFRESH_POLICY`**: This notification is sent in a **MAMUserNotification**. When this notification is received, any cached Intune policy must be invalidated and updated. This is generally handled by the SDK; however, it should be handled by the app if the policy is used in any persistent way. 



## Protecting Backup data 

As of Android Marshmallow (API 23), Android has two ways for an app to back up its data. Each option is available to your app and requires different steps to ensure that Intune data protection is correctly implemented. You can review the table below on corresponding actions required for correct data protection behavior.  You can read more about the backup methods in the [Android API guide](http://developer.android.com/guide/topics/data/backup.html). 

### Auto Backup for Apps

Android began offering [automatic full backups](https://developer.android.com/guide/topics/data/autobackup.html) to apps on Android Marshmallow devices, regardless of the app's target API. In your AndroidManifest.xml, if you explicitly set `android:allowBackup` to **false**, then your app will never be queued for backups by Android and "corporate" data will stay within the app. In this case, no further action is necessary.

However, by default the `android:allowBackup` attribute is set to true, even if `android:allowBackup` isn't specified in the manifest file. This means all app data is automatically backed up to the user's Google Drive account, a default behavior that poses a **data leak risk**. Therefore, the SDK requires the changes outlined below to ensure that data protection is applied.  It is important to follow the guidelines  below to protect customer data properly if you want your app to run on Android Marshmallow devices.  

*  If you have not written a backup agent to back up your app using a **MAMBackupAgent** or **MAMBackupAgentHelper**, then you must consider and control how your app data will be uploaded by Auto Backup. Intune allows you to utilize all the [Auto Backup features](https://developer.android.com/guide/topics/data/autobackup.html) available from Android, including the ability to define custom rules in XML, but you must follow the steps below to secure your data:

	1. Use the default MAMBackupAgent to allow for automatic full backups that are Intune-policy compliant. Put `android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"` in your app manifest. 
	2. When you decide which type of full backup your app should receive (unfiltered, filtered, or none) you'll need to set the attribute `android:fullBackupContent`  to true, false, or an XML resource in your app. Please copy whatever you put into `android:fullBackupContent` into a metadata tag named `com.microsoft.intune.mam.FullBackupContent`

	**Examples**: If you want your app to have full backups according to your custom rules in an XML file, please provide a resource under the `com.microsoft.intune.mam.FullBackupContent` metadata tag in your manifest like so: 
	```
	<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
	```



### Key/Value Backup

This option is available to all APIs and uses `BackupAgent` and `BackupAgentHelper`. 

#### Using BackupAgentHelper

`BackupAgentHelper` is much simpler to implement than `BackupAgent` both in terms of native Android functionality and MAM integration. `BackupAgentHelper` allows the developer to register entire files and shared preferences to either a `FileBackupHelper` or `SharedPreferencesBackupHelper`, respectively, which are then added to the `BackupAgentHelper` upon creation. 

#### Using BackupAgent

`BackupAgent` allows you to be much more explicit about what data is backed up. However, this options will mean that you will not be able to take advantage of the Android backup framework.  Because you are fairly responsible for the implementation, there are more steps required to ensure appropriate data protection from MAM. Since most of the work is pushed onto you, the developer, MAM integration is slightly more involved. 

##### App does not have a backup agent
  
These are the developer options when `android:allowBackup =true`:

###### Full back up according to a configuration file: 

Provide a resource under the `com.microsoft.intune.mam.FullBackupContent` metadata tag in your manifest. e.g.:
    `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Add the following attribute in the `<application>` tag: `android:fullBackupContent="@xml/my_scheme"`, where `my_scheme` is an XML resource in your app. 

###### Full back dup without exclusions 

Provide a tag in the manifest such as `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />` 
 
Add the following attribute in the `<application>` tag: 
`android:fullBackupContent="true"`.

##### App has a backup agent

Follow the recommendations in the `BackupAgent` and `BackupAgentHelper` sections as outlined above 

Consider switching to using our `MAMDefaultFullBackupAgent`, which provides easy back up on Android M. 

#### Before your backup

Before beginning your backup, you must check that the files or data buffers you are planning on backing up are indeed allowed to be backed up. We've provided you with an `isBackupAllowed` function in `MAMFileProtectionManager` and `MAMDataProtectionManager` to determine this. If the file or data buffer is not allowed to be backed up then you should not attempt to continue utilizing it in your backup.

At some point during your backup, if you want the identities for the files you checked in step 1 backed up, you must call `backupMAMFileIdentity(BackupDataOutput data, File … files)` with the files you plan to extract data from. This will automatically create new backup entities and write them to the `BackupDataOutput` for you. These entities will be automatically consumed upon restore. 

### Configure Azure Directory Authentication Library (ADAL)  

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

#### Common ADAL configurations 

The following are common configuration for the values explained above. 

##### App does not integrate ADAL

* The authority must  be set to the desired environment where AAD accounts have been configured.

* SkipBroker must be set to true.

##### App integrates ADAL

* The authority must be set to the desired environment where AAD accounts have been configured.

* Client ID must be set to the app's client ID.

* `NonBrokerRedirectURI` should be set to a valid redirect URI for the app.
    * Or `urn:ietf:wg:oauth:2.0:oob` must be configured as a valid AAD redirect URI.

* SkipBroker must be set to false (or be absent)

* AAD must be configured to accept the broker redirect URI.

##### App integrates ADAL but does not support the AAD Authenticator app.

* The authority must be set to the desired environment where AAD accounts have been configured.

* Client ID must be set to the app's client ID.

* `NonBrokerRedirectURI` must be set to a valid redirect URI for the app.

    * Or `urn:ietf:wg:oauth:2.0:oob` should be configured as a valid AAD redirect URI.

### How to enable logging in the SDK 

Logging is done through the `java.util.logging` framework. To receive the logs, set up global logging as described in the [Java technical guide](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). Depending on the app, `App.onCreate` is usually the best place  to initiate logging. Please note that Log messages are keyed by the class name, which may be obfuscated.

##Multi-Identity
###Overview
By default, the Intune App SDK will apply policy  to the app as a whole. Multi-Identity is a MAM feature which can be enabled to allow policy to be applied on a per-identity level.  This requires significantly more app participation than other MAM features. The app is required to inform the app SDK when it intends to change the active identity, the SDK will also notify the app when an identity change is required. Currently, only one managed identity is supported. Once the user enrolls the device or the app, the SDK uses this identity and considers it the primary managed identity. Other users in the app will be treated as unmanaged with unrestricted policy settings. 

Note that an identity is simply defined as a string. Identities are case-insensitive and requests to the SDK for an identity may not return the same casing that was originally used when setting the identity.

###Enabling Multi-Identity
By default, all apps are considered to be single-identity apps. An app declares that it is multi-identity aware by placing the following meta-data in the Android manifest.

```
<meta-data
            android:name="com.microsoft.intune.mam.MAMMultiIdentity"
            android:value="true" />
```
###Setting the Identity

Developers can set the identity of the app on the following levels: 
1. Process level, 
2. Context  (generally Activity) level 
3. Thread level 

An identity set at the thread level supersedes an identity set at the Context level which supersedes an identity set at the process level. An identity set on a Context is only used when appropriate. File IO operations, for example do not have an associated Context. The following methods on MAMPolicyManager may be used to set the identity and retrieve the identity values previously set.

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
You can also clear the identity of the app by setting it to null. The empty string may be used as an identity which will never have restrictions. All of the methods to set the identity report back  result values via ``` MAMIdentitySwitchResult```. There are four values that can be returned:

1.**SUCCEEDED**: the identity change was successful
2.**NOT_ALLOWED**: the identity change is not allowed. This will occur if an attempt is made to switch to a different corporate user belonging to the same company as the enrolled user. It will also occur if an attempt is made to set the UI (Context) identity when a different identity is set on the current thread.
3.**CANCELLED**: the user cancelled the identity change, generally be pressing the back button on a PIN/Auth prompt.
4.**FAILED**: the identity change failed for an unspecified reason.

In the case of setting a Context identity, the result is reported asynchronously. If the Context is an Activity, it will not be known if the identity change succeeded until after conditional launch is performed which may require the user to enter a PIN or their full corporate credentials. The app  is expected to implement a ```MAMSetUIIdentityCallback``` to receive this result although it is permissible to pass null for this parameter.

```
public interface MAMSetUIIdentityCallback {
	void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult); 
}
```

You can also set the identity of an activity  directly through a method on MAMActivity instead of calling ``` MAMPolicyManager.setUIPolicyIdentity``` . You can do so by using the following method:

 ```public final void switchMAMIdentity(final String newIdentity);```

Apps may also override a method on MAMActivity to be notified of the result of attempts to change the identity of that activity 

```public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);```

**Note:** Switching the identity may require recreating the activity. In this case, the ```onSwitchMAMIdentityComplete``` callback will be delivered to the new instance of the activity.

###Implicit Identity Changes

In addition to the app's ability to set the identity, a thread or a context's identity may change based on data ingress from another MAM enabled app. For instance, If an activity is launched from an Intent sent by another MAM app, the activity’s identity will be set based on the effective identity in the other app at the point the Intent was sent.
For services, the thread's identity will be set similarly for the duration of an onStart or onBind call. Calls into the Binder returned from onBind will also temporarily set the thread identity.
Calls into a ```ContentProvider``` will similarly set the thread identity for their duration.
In addition, user interaction with an activity may cause an implicit identity switch.
For instance, a user canceling out of an authorization prompt during ```Resume``` will result in an implicit switch to an empty identity.
The app is given an opportunity to be made aware of these changes, and in some cases, forbid them if necessary. ```MAMService``` and ```MAMContentProvider``` expose the following method which subclasses may override:

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
The ```AppIdentitySwitchReason``` captures the source of the implicit switch, and can accept the values ```CREATE```, ```RESUME_CANCELLED```, and ```NEW_INTENT```.  The ```RESUME_CANCELLED``` reason is used when activity resume causes PIN, authentication, or other compliance UI to be displayed and the user attempts to cancel out of that UI, generally though use of the back button.
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
Where ```AppIdentitySwitchResult``` is either ```SUCCESS``` or ```FAILURE```. 

The method ```onMAMIdentitySwitchRequired``` is called for all implicit identity changes except for those made through a Binder returned from ```MAMService.onMAMBind```. The default implementations of ```onMAMIdentitySwitchRequired``` immediately calls ```reportIdentitySwitchResult(FAILURE)``` when the reason is ```RESUME_CANCELLED```, and ```reportIdentitySwitchResult(SUCCESS)``` in all other cases. 

It is not expected that most apps will need to block or delay an identity switch in a different manner, but if an app needs to do so, the following points must be considered:
*If an identity switch is blocked the result is the same as if ```Receive``` sharing settings had prohibited the data ingress.
*If a Service is running on the main thread, ```reportIdentitySwitchResult``` **must** be called synchronously or the UI thread will hang. 
*For ```Activity``` creation, ```onMAMIdentitySwitchRequired``` will be called before ```onMAMCreate```. If the app must show UI to determine whether to allow the identity switch, that UI must be shown using a different activity.
*In an Activity, when a switch to the empty identity is requested with reason equal to ```RESUME_CANCELLED```, the app must modify the resumed activity to display data consistent with that identity switch.  If this is not possible, the app should refuse the switch, and the user will be asked again to comply with policy for the resuming identity (e.g. by being presented with the PIN entry screen). 

**Note:** a multi-identity app will always receive incoming data from both managed and unmanaged apps. It is the responsibility of the app to treat data from managed identities in a managed manner. If a requested identity is managed ```(MAMPolicyManager.getIsIdentityManaged)```, but the app is not able to use that account (e.g. because accounts, such as email accounts, must be set up in the app first) then the identity switch should be refused.

##File Protection
Every file will have an identity associated with it at the time of creation based on thread and process identity. This identity will be used for both file encryption and selective wipe. Only files whose identity has policy requiring encryption will be encrypted. The SDK's default selective wipe will only wipe files associated with the identity for which a wipe has been requested. The app may query or change a file’s identity using ```MAMFileProtectionManager```
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

**Note:** File identity tagging is senstive to offline mode. The following points should be taken into account.
* If the Company Portal is not installed, files cannot be identity-tagged. 
* If the Company Portal is installed, but the app does not have policy, files cannot be reliably identity-tagged.
* When file identity tagging becomes available, all previously created files are treated as personal (belonging to the empty-string identity) unless the app was previously installed as a single-identity managed app in which case they are treated as belonging to the enrolled user.

###Data Protection
It is not possible to tag a file as belonging to multiple identities. Apps which must store data belonging to different users in the same file can do so manually using the features provided by ```MAMDataProtectionManager```. This allows the app to encrypt data and tie it to a particular user. The encrypted data is suitable for storing to disk in a file. You can query the data associated with the identity and the data can be unecrypted later. 

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
##Content Providers
If the app is providing potentially corporate data other than a ```ParcelFileDescriptor``` through a ```ContentProvider```, the app must call the ```MAMContentProvider``` method ```isProvideContentAllowed(String)``` passing the owner ```UPN``` for the content. If this function returns false, the content may not be returned to the caller. File descriptors returned through a content provider are handled automatically based on the file identity.

##Selective Wipe
If an app registers for the ```WIPE_USER_DATA``` notification, it will not receive the benefit of SDK default selective wipe behavior. For multi-identity aware apps, this may be more significant since MAM default selective wipe will wipe only files matching the identity to be wiped. If you are building a multi-Identity aware app, you can register for ```WIPE_USER_AUXILIARY_DATA```, which will allow you to take advantage of the SDK default wipe behavior. This notification will be sent immediately before performing the SDK default selective wipe. Note that an app should never register for both ```WIPE_USER_DATA```and ```WIPE_USER_AUXILIARY_DATA```.

## Known Platform Limitations 

### File Size Limitations 

On Android, the limitations of the Dalvik executable file format may become an issue for large code bases that run without ProGuard. Specifically, the following limitations may  occur: 

* The 65K limit on fields.

* The 65K limit on methods.

When including many projects, every android:package will get a copy of R  which will dramatically increase the number of fields as libraries are added. The following recommendations may help mitigate this limitation:
 
* All library projects should share the same android:package where possible. This will not sporadically fail in the field, since it is purely a build-time problem.   In addition, newer versions of the Android SDK will pre-process DEX files to remove some of the redundancy. This lowers the distance from the fields even further.

* Use the newest Android SDK build tools available.

* Remove all unnecessary and unused libraries (e.g. `android.support.v4`)

### Policy Enforcement Limitations

**Screen Capture**: The SDK is unable to enforce a new screen capture setting value in Activities that have already gone through Activity.onCreate. This can result in a period of time where the app has been configured to disable screenshots but screenshots can still be taken.

**Using Content Resolvers*: The transfer or receive policy may block or partially block the use of a content resolver to access the content provider in another app. This will cause ContentResolver methods to return null or throw a failure value (e.g. `openOutputStream` will throw `FileNotFoundException` if blocked). The app can determine whether a failure to write data through a content resolver was caused by policy (or would be caused by policy) by making the call:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Exported Services**: The `AndroidManifest.xml` file included in the Intune App SDK contains `MAMNotificationReceiverService`, which must be an exported service to allow the Company Portal to send notifications to an enlightened app. The service checks the caller to ensure that only the Company Portal is allowed to send notifications. 

## Recommended Android Best Practices 

The Intune SDK maintains the contract provided by the Android API, though failure conditions may be triggered more frequently as a result of policy enforcement. These Android best practices will reduce the likelihood of failure: 

* Android SDK Functions that may return null have a higher likelihood of being null now.  To minimize issues, ensure that null checks are in the right places.

* Features that can be checked for must be checked for through their SDK APIs.

* Any derived functions must call through to their super class versions.

* Avoid use of any API in an ambiguous way. For example, `Activity.startActivityForResult/onActivityResult` without checking the requestCode will cause strange behavior.



