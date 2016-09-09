---
# required metadata

title: Wrap Android apps with App Wrapping Tool | Microsoft Intune
description: Use the information in this topic to learn how to wrap your Android apps without modifying the code of the app itself. Prepare the apps so you can apply mobile app management policies.
keywords:
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: oldang
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Prepare Android apps for mobile application management with the Intune App Wrapping Tool
Use the **Microsoft Intune App Wrapping Tool for Android** to modify the behavior of your in-house Android apps to let you configure features of the app without modifying the code of the app itself.

The tool is a Windows command-line application that runs in PowerShell and creates a ‘wrapper’ around your app. Once the app is processed, you can then change the app’s functionality using [mobile application management policies](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) that you configure.


Before running the tool, review the [Security considerations for running the app wrapping tool](#security-considerations-for-running-the-app-wrapping-tool). To download the tool, see [Microsoft Intune App Wrapping Tool for Android](https://www.microsoft.com/download/details.aspx?id=47267).

>[!IMPORTANT]
>The version of the app wrapper tool, which supports devices not enrolled in Intune, is available for public preview. If you wish to participate in the public preview, you can download the tool from [this github page](https://github.com/msintuneappsdk/intune-app-wrapper-android-preview) for Android.

The scenario is described in the [Protect LOB apps on devices not enrolled in Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md) topic.


## Step 1 Fulfill the prerequisites for using the app wrapping tool

-   You must run the app wrapping tool on a Windows computer running Windows 7 or later.

-   Your input app must be a valid Android application package with the extension **.apk** file and:

    -   Cannot be encrypted

    -   Must not have already been wrapped by the app wrapping tool

    -   Must be written for Android 4.0 or later

-   The app must be developed by, or for your company. You cannot use this tool to process apps downloaded from the Google Play Store.

-   To run the app wrapping tool, you must install the latest version of the [Java Runtime Environment](http://java.com/download/) and then ensure that the Java path variable has been set to **C:\ProgramData\Oracle\Java\javapath** in your Windows environment variables. For more help, see your [Java documentation](http://java.com/download/help/).

    > [!NOTE]
    > In some cases, the 32-bit version of Java may result in memory issues. We recommend that you install the 64-bit version instead.

## Step 2 Install the app wrapping tool

1.  From the Microsoft Download Center, download and open the installation file for the app wrapping tool to a Windows computer.

2.  Accept the license agreement, then complete the installation.

Note the folder to which you installed the tool. The default location is: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**.

## Step 3 Run the app wrapping tool

1.  On the Windows computer where you installed the app wrapping tool, open a PowerShell window in administrator mode.

2.  From the folder where you installed the tool, import the app wrapping tool PowerShell module:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Run the tool by using the **invoke-AppWrappingTool** command together with the following parameters.

|Parameter|More information|Examples|
|-------------|--------------------|---------|
|**-InputPath**&lt;String&gt;|Path of the source Android app (.apk).| |
|**-OutputPath**&lt;String&gt;|Path to the "output" Android app. If this is the same directory path as InputPath, the packaging will fail.| |
|**-KeyStorePath**&lt;String&gt;|Path to the keystore file that contains the public/private key pair for signing.| |
|**-KeyStorePassword**&lt;SecureString&gt;|Password used to decrypt the keystore. Android requires that all application packages (.apk) to be signed. Use the Java Key Tool to generate the KeyStorePassword as shown in the example. Read more about [keystore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html).|keytool.exe -genkey -v -keystore keystorefile -alias ks -keyalg RSA -keysize 2048 -validity 50000 |
|**-KeyAlias**&lt;String&gt;|Name of the key to be used for signing.| |
|**-KeyPassword**&lt;SecureString&gt;|Password used to decrypt the private key that will be used for signing.| |
|**-SigAlg**&lt;SecureString&gt;|Name of the signature algorithm to be used for signing. The algorithm must be compatible with the private key.|Examples: SHA256withRSA, SHA1withRSA, MD5withRSA|
|**-ClientID**&lt;GUID&gt;|Azure Active Directory Client ID of the input app (optional).| |
|**-AuthorityURI**&lt;Uri&gt;|Azure Active Directory Authority URI of the input app (optional).| |
|**-SkipBroker**&lt;Boolean&gt;|Indicates whether the input application supports device-wide brokered single sign-on (optional). |**True** - the input application does not support device-wide brokered single sign-on. Use the NonBrokerRedirectURI parameter. **False** - the input application supports device-wide brokered single sign-on|
|**-NonBrokerRedirectURI**&lt;URI&gt;|Azure Active Directory Redirect URI to use if SkipBroker is true (optional).|  |


**&lt;CommonParameters&gt;**
    (optional – supports common PowerShell parameters such as verbose, debug, etc.)

- For a list of common parameters, see the [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- To see help for the tool, enter the command:

    ```
    Help Invoke-AppWrappingTool
    ```
- To find out more about Azure Active Directory (AAD) integration, see [How to wrap apps that use the Azure Active Directory library](#how-to-wrap-apps-that-use-the-azure-active-directory-library).

**Example:**


    Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
    invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app.wrapped\HelloWorld_wrapped2.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\keystorefile" -keyAlias ks -SigAlg SHA1withRSA -Verbose

You will then be prompted for the **KeyStorePassword** and **KeyPassword**.

The wrapped app is generated, and saved, along with a log file, in the output path you specified.

## Security considerations for running the app wrapping tool
To prevent potential spoofing, information disclosure, and elevation of privilege attacks:

-   Ensure that the input line-of-business application, output application, and Java KeyStore are on the same computer where the app wrapping tool is running.

-   Import the output application to the Intune console on the same computer where the tool is running. See [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html) for more information about the Java keytool.

-   If the output application and the tool are on a Universal Naming Convention (UNC) path and you are not running the tool and input files on the same computer, configure the environment to be secure by using [Internet Protocol Security (IPsec)](http://en.wikipedia.org/wiki/IPsec) or [Server Message Block (SMB) signing](https://support.microsoft.com/en-us/kb/887429).

-   Ensure that the application is coming from a trusted source, especially if you are using Azure Active Directory (AAD), which might enable the application to access the AAD token during runtime.

-   Secure the output directory that contains the wrapped app. Consider using a user-level directory for the output.


### Step 1 Configure access to mobile app management in AAD
Before you can use an app’s AAD registration values in the app wrapping tool, the app developer must grant that app access to the Intune Mobile Application Management resource by following these steps:

1.  Log into an existing AAD account in the Azure management portal.

2.  Chose **existing LOB application registration**.

3.  In the **configure** section, choose **Configure Access to Web APIs in other applications**.

4.  From the first drop-down list in the **Permission to other applications** section, choose **Intune Mobile Application Management**.

You can now use the app’s Client ID in the app wrapping tool. You can find the Client ID in the Azure Active Directory management portal, as described in the table in [Step 2 Review the identifiers you need to get when you register the app](#step-2-review-the-identifiers-you-need-to-get-when-you-register-the-app).

### Step 2 Use the AAD identifier values in the app wrapping tool
Using the identifier values that you got from the registration process, enter the values as command-line properties in the app wrapping tool. You must specify all of the values in the table in order for end users to successfully authenticate the app. Default values are used if you don't specify a value.

|Identifier|Parameter|
|--------------|-------------|
|Client ID|ClientID|
|Authority URI|Authority-URI|
|SkipBroker|SkipBroker|
|Non-Broker Redirect URI|NonBrokerRedirectURI|
|Resource ID|ResourceID|
Keep the following points in mind as you wrap your app:

-   To verify that the authentication was successful,
  [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] fetches the AAD token that is associated with the MAM resource-id. However, the token is not used in any call that would in turn verify the validity of the token. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] only reads the user principal name (UPN) of the signed-in user to determine app access. The AAD token is not used for any further service calls.

-   Double login prompts are prevented if you provide your client application’s Client ID and Authority URI. You need to register the Client ID to enable it to access the published [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] MAM resource ID in the AAD Dashboard. If you don't register the Client ID, users get a login failure when the app runs.


### See also
- [Decide how to prepare apps for mobile application management with Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [Use the SDK to enable apps for mobile application management](use-the-sdk-to-enable-apps-for-mobile-application-management.md)
