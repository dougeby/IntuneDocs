---
# required metadata

title: Wrap Android apps with the Intune App Wrapping Tool 
description: Learn how to wrap your Android apps without changing the code of the app itself. Prepare the apps so you can apply mobile app management policies.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/05/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: aanavath
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Prepare Android apps for app protection policies with the Intune App Wrapping Tool

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Use the Microsoft Intune App Wrapping Tool for Android to change the behavior of your in-house Android apps by restricting features of the app without changing the code of the app itself.

The tool is a Windows command-line application that runs in PowerShell and creates a wrapper around your Android app. After the app is wrapped, you can change the app’s functionality by configuring [mobile application management policies](/intune-classic/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console) in Intune.


Before running the tool, review [Security considerations for running the App Wrapping Tool](#security-considerations-for-running-the-app-wrapping-tool). To download the tool, go to the [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) on GitHub.



## Fulfill the prerequisites for using the App Wrapping Tool

-   You must run the App Wrapping Tool on a Windows computer running Windows 7 or later.

-   Your input app must be a valid Android application package with the file extension .apk and:

    -   It cannot be encrypted.
    -   It must not have previously been wrapped by the Intune App Wrapping Tool.
    -   It must be written for Android 4.0 or later.

-   The app must be developed by or for your company. You cannot use this tool on apps downloaded from the Google Play Store.

-   To run the App Wrapping Tool, you must install the latest version of the [Java Runtime Environment](http://java.com/download/) and then ensure that the Java path variable has been set to C:\ProgramData\Oracle\Java\javapath in your Windows environment variables. For more help, see the [Java documentation](http://java.com/download/help/).

    > [!NOTE]
    > In some cases, the 32-bit version of Java may result in memory issues. It's a good idea to install the 64-bit version.

- Android requires all app packages (.apk) to be signed. For **reusing** existing certificates and overall signing certificate guidance, see [Reusing signing certificates and wrapping apps](https://docs.microsoft.com/intune/app-wrapper-prepare-android#reusing-signing-certificates-and-wrapping-apps). The Java executable keytool.exe is used to generate **new** credentials needed to sign the wrapped output app. Any passwords that are set must be secure, but make a note of them because they're needed to run the App Wrapping Tool.

## Install the App Wrapping Tool

1.  From the [GitHub repository](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android), download the installation file InstallAWT.exe for the Intune App Wrapping Tool for Android to a Windows computer. Open the installation file.

2.  Accept the license agreement, then finish the installation.

Note the folder to which you installed the tool. The default location is: C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.

## Run the App Wrapping Tool

1.  On the Windows computer where you installed the App Wrapping Tool, open a PowerShell window.

2.  From the folder where you installed the tool, import the App Wrapping Tool PowerShell module:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Run the tool by using the **invoke-AppWrappingTool** command, which has the following usage syntax:
	```
	Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
    -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
	```

 The following table details the properties of the **invoke-AppWrappingTool** command:

|Property|Information|Example|
|-------------|--------------------|---------|
|**-InputPath**&lt;String&gt;|Path of the source Android app (.apk).| |
 |**-OutputPath**&lt;String&gt;|Path to the output Android app. If this is the same directory path as InputPath, the packaging will fail.| |
|**-KeyStorePath**&lt;String&gt;|Path to the keystore file that has the public/private key pair for signing.|By default, keystore files are stored in "C:\Program Files (x86)\Java\jreX.X.X_XX\bin." |
|**-KeyStorePassword**&lt;SecureString&gt;|Password used to decrypt the keystore. Android requires all application packages (.apk) to be signed. Use Java keytool to generate the KeyStorePassword. Read more about Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) here.| |
|**-KeyAlias**&lt;String&gt;|Name of the key to be used for signing.| |
|**-KeyPassword**&lt;SecureString&gt;|Password used to decrypt the private key that will be used for signing.| |
|**-SigAlg**&lt;SecureString&gt;| (Optional) The name of the signature algorithm to be used for signing. The algorithm must be compatible with the private key.|Examples: SHA256withRSA, SHA1withRSA|
| **&lt;CommonParameters&gt;** | (Optional) The command supports common PowerShell parameters like verbose and debug. |


- For a list of common parameters, see the [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- To see detailed usage information for the tool, enter the command:

    ```
    Help Invoke-AppWrappingTool
    ```

**Example:**

Import the PowerShell module.
```
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```
Run the App Wrapping Tool on the native app HelloWorld.apk.
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

You will then be prompted for **KeyStorePassword** and **KeyPassword**. Enter the credentials you used to create the key store file.

The wrapped app and a log file are generated and saved in the output path you specified.

## How often should I rewrap my Android application with the Intune App Wrapping Tool?
The main scenarios in which you would need to rewrap your applications are as follows:
* The application itself has released a new version. The previous version of the app was wrapped and uploaded to the Intune console.
* The Intune App Wrapping Tool for Android has released a new version that enables key bug fixes, or new, specific Intune application protection policy features. This happens every 6-8 weeks through GitHub repo for the [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android).

Some best practices for rewrapping include: 
* Maintaining signing certificates used during the build process, see [Reusing signing certificates and wrapping apps](https://docs.microsoft.com/intune/app-wrapper-prepare-android#reusing-signing-certificates-and-wrapping-apps)

## Reusing signing certificates and wrapping apps
Android requires that all apps must be signed by a valid certificate in order to be installed on Android devices.

Wrapped apps can be signed either as part of the wrapping process or *after* wrapping using your existing signing tools (any signing information in the app before wrapping is discarded).
 
If possible, the signing information that was already used during the build process should be used during wrapping. In certain organizations, this may require working with whoever owns the keystore information (ie. the app build team). 

If the previous signing certificate cannot be used, or the app has not been deployed before, you may create a new signing certificate by following the instructions in the [Android Developer Guide](https://developer.android.com/studio/publish/app-signing.html#signing-manually).

If the app has been deployed previously with a different signing certificate, the app can't be uploaded to Intune after upgrade. App upgrade scenarios will be broken if your app is signed with a different certificate than the one the app is built with. As such, any new signing certificates should be maintained for app upgrades. 

## Security considerations for running the App Wrapping Tool
To prevent potential spoofing, information disclosure, and elevation of privilege attacks:

-   Ensure that the input line-of-business (LOB) application, output application, and Java KeyStore are on the same Windows computer where the App Wrapping Tool is running.

-   Import the output application to Intune on the same machine where the tool is running. See [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html) for more about about Java keytool.

-   If the output application and the tool are on a Universal Naming Convention (UNC) path and you are not running the tool and input files on the same computer, set up the environment to be secure by using [Internet Protocol Security (IPsec)](http://wikipedia.org/wiki/IPsec) or [Server Message Block (SMB) signing](https://support.microsoft.com/kb/887429).

-   Ensure that the application is coming from a trusted source.

-   Secure the output directory that has the wrapped app. Consider using a user-level directory for the output.

## Requiring user login prompt for an automatic APP-WE service enrollment, requiring Intune app protection policies in order to use your wrapped Android LOB app, and enabling ADAL SSO (optional)

The following is guidance for requiring user prompt on app launch for an automatic APP-WE service enrollment (we call this **default enrollment** in this section), requiring Intune app protection policies to allow only Intune protected users to use your wrapped Android LOB app. It also covers how to enable SSO for your wrapped Android LOB app. 

> [!NOTE] 
> The benefits of **default enrollment** include a simplified method of obtaining policy from APP-WE service for an app on the device.

### General Requirements
* The Intune SDK team will require your app's Application ID. A way to find this is through the [Azure Portal](https://portal.azure.com/), under **All Applications**, in the column for **Application ID**. A good way to reach out to the Intune SDK team is through emailing msintuneappsdk@microsoft.com.
	 
### Working with the Intune SDK
These instructions are specific to all Android and Xamarin apps who wish to require Intune app protection policies for use on a end user device.

1. Configure ADAL using the steps defined in the [Intune SDK for Android guide](https://docs.microsoft.com/intune/app-sdk-android#configure-azure-active-directory-authentication-library-adal).
> [!NOTE] 
> The term "client id" tied to your app is the same as the term "application id" from the Azure Portal tied to your app. 
* To enable SSO, "Common ADAL configuration" #2 is what is needed.

2. Enable default enrollment by putting the following value in the manifest:
```xml <meta-data android:name="com.microsoft.intune.mam.DefaultMAMServiceEnrollment" android:value="true" />```
> [!NOTE] 
> This must be the only MAM-WE integration in the app. If there are any other attempts to call MAMEnrollmentManager APIs, conflicts can arise.

3. Enable MAM policy required by putting the following value in the manifest:
```xml <meta-data android:name="com.microsoft.intune.mam.MAMPolicyRequired" android:value="true" />```
> [!NOTE] 
> This forces the user to download the Company Portal on the device and complete the default enrollment flow before use.

### See also
- [Decide how to prepare apps for mobile application management with Microsoft Intune](apps-prepare-mobile-application-management.md)

- [Microsoft Intune App SDK for Android developer guide](app-sdk-android.md)
