---
title: MD Conversion - Prepare Android apps for mobile application management with the Microsoft Intune App Wrapping Tool
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ab698da6-c09d-4826-b1aa-9f20d5867768
---
# MD Conversion - Prepare Android apps for mobile application management with the Microsoft Intune App Wrapping Tool
Use the **Microsoft Intune App Wrapping Tool for Android** to modify the behavior of your in-house Android apps to let you configure features of the app without modifying the code of the app itself.

The tool is a Windows command line application that runs in PowerShell and creates a ‘wrapper’ around your app. Once the app is processed, you can then change the app’s functionality using an [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] mobile application management policy (see [Configure and deploy mobile application management policies in the Microsoft Intune console](../Topic/Configure_and_deploy_mobile_application_management_policies_in_the_Microsoft_Intune_console.md)).

If your app is using the Azure Active Directory Authentication Library (ADAL), you must complete the steps in [How to wrap apps that use the Azure Active Directory Library (ADAL)](#BKMK_ADAL_android) before you wrap your app. If you are unsure if your app uses this library, contact the developer of the app.

Before running the tool, review the [Security considerations for running the app wrapping tool](../Topic/Prepare_Android_apps_for_mobile_application_management_with_the_Microsoft_Intune_App_Wrapping_Tool.md#BKMK_androidappwraptool). To download the tool, see [Microsoft Intune App Wrapping Tool for Android](http://www.microsoft.com/en-us/download/details.aspx?id=47267).

## Step 1: Fulfill the prerequisites for using the app wrapping tool

-   You must run the app wrapping tool on a Windows computer running Windows 7 or later.

-   Your input app must be a valid Android application package with the extension **.apk** file and:

    -   Cannot be encrypted

    -   Must not have already been wrapped by the app wrapping tool

    -   Must be written for Android 4.0 or later

-   The app must be developed by, or for your company. You cannot use this tool to process apps downloaded from the Google Play Store.

-   To run the app wrapping tool, you must install the latest version of the [Java Runtime Environment](http://java.com/download/) and then ensure that the Java path variable has been set to **C:\ProgramData\Oracle\Java\javapath** in your Windows environment variables. For more help, see your [Java documentation](http://java.com/download/help/).

    > [!NOTE]
    > In some cases, the 32-bit version of Java may result in memory issues. We recommend that you install the 64-bit version instead.

## Step 2: Install the App Wrapping Tool

#### Install the app wrapping tool

1.  From the Microsoft Download Center, download and open the installation file for the app wrapping tool to a Windows computer.

2.  Accept the license agreement, then complete the installation.

Note the folder to which you installed the tool. The default location is: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**.

## Step 3: Run the App Wrapping Tool

1.  On the Windows computer where you installed the app wrapping tool, open a PowerShell window.

2.  From the folder where you installed the tool, import the app wrapping tool PowerShell module:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Run the tool by using the **invoke-AppWrappingTool** command together with the following parameters. Parameters that are marked as "optional" are for apps that use Azure Active Directory Library (ADAL). For more information, see [How to wrap apps that use the Azure Active Directory Library (ADAL)](#BKMK_ADAL_android).

    |Parameter|More information|
    |-------------|--------------------|
    |**-InputPath***&lt;String&gt;*|Path of the source Android app (.apk).|
    |**-OutputPath***&lt;String&gt;*|Path to the "output" Android app. If this is the same directory path as InputPath, the packaging will fail.|
    |**-KeyStorePath***&lt;String&gt;*|Path to the keystore file that contains the public/private key pair for signing.|
    |**-KeyStorePassword***&lt;SecureString&gt;*|Password used to decrypt the keystore.|
    |**-KeyAlias***&lt;String&gt;*|Name of the key to be used for signing.|
    |**-KeyPassword***&lt;SecureString&gt;*|Password used to decrypt the private key that will be used for signing.|
    |**-SigAlg***&lt;SecureString&gt;*|Name of the signature algorithm to be used for signing. The algorithm must be compatible with the private key.<br /><br />Examples: SHA256withRSA, SHA1withRSA, MD5withRSA|
    |**-ClientID***&lt;GUID&gt;*|Azure Active Directory Client ID of the input app (optional).|
    |**-AuthorityURI***&lt;Uri&gt;*|Azure Active Directory Authority URI of the input app (optional).|
    |**-SkipBroker***&lt;Boolean&gt;*|Indicates whether the input application supports device-wide brokered single sign-on (optional).<br /><br />**True** - the input application does not support device-wide brokered single sign-on. Use the NonBrokerRedirectURI parameter.<br /><br />**False** - the input application supports device-wide brokered single sign-on|
    |**-NonBrokerRedirectURI***&lt;URI&gt;*|Azure Active Directory Redirect URI to use if SkipBroker is true (optional).|
    |*&lt;CommonParameters&gt;*|(optional – supports common PowerShell parameters such as verbose, debug, etc.)<br /><br />For a list of common parameters, see the [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).|
    To see help for the tool, enter the command:

    ```
    Help Invoke-AppWrappingTool
    ```
    To find out more about Azure Active Directory (AAD) integration, see [here](https://technet.microsoft.com/library/dn878028.aspx).

    **Example:**

    ```
    Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
    Invoke-AppWrappingTool –InputPath <input-app.apk> -OutputPath <output-app.apk> -KeyStorePath <path-to-signing.keystore> -KeyAlias <signing-key-name> -ClientID <xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx> -AuthorityURI <http://AzureActivieDirectory.Authority.URL> -SkipBroker<$True|$False> -NonBrokerRedirectURI <urn:xxx:xx:xxxx:xx:xxx>
    ```
    You will then be prompted for the **KeyStorePassword** and **KeyPassword**.

The wrapped app is generated, and saved, along with a log file, in the output path you specified.

## <a name="BKMK_androidappwraptool"></a>Security considerations for running the app wrapping tool
To prevent potential spoofing, information disclosure, and elevation of privilege attacks:

-   Ensure that the input line-of-business application, output application, and Java KeyStore are on the same computer where the app wrapping tool is running.

-   Import the output application to the Intune Console on the same computer where the tool is running.

-   If the output application and the tool are on a Universal Naming Convention (UNC) path and you are not running the tool and input files on the same computer, configure the environment to be secure by using [Internet Protocol Security (IPsec)](http://en.wikipedia.org/wiki/IPsec) or [Server Message Block (SMB) signing](https://support.microsoft.com/en-us/kb/887429).

-   Ensure that the application is coming from a trusted source, especially if you are using Azure Active Directory (AAD), which might enable the application to access the AAD token during runtime.

-   Secure the output directory that contains the wrapped app. Consider using a user-level directory for the output.

## <a name="BKMK_ADAL_android"></a>How to wrap apps that use the Azure Active Directory Library (ADAL)
If your app is using the Azure Active Directory Authentication Library (ADAL), you must complete these steps before you wrap your app.

### Step 1: Ensure that you meet the requirements for ADAL
For apps that use ADAL, the following must be true:

-   The app must incorporate an ADAL version greater than or equal to 1.0.2.

-   The developer must [grant their app access to the Intune Mobile Application Management resource](../Topic/Prepare_iOS_apps_for_mobile_application_management_with_the_Microsoft_Intune_App_Wrapping_Tool.md#BKMK_AD).

### <a name="BKMK_review_IDs"></a>Step 2: Review the identifiers that you need to get when you register the app
In the next step, you will use the Azure management portal to register your apps (which are using  ADAL with Azure Active Directory (AAD)) to get the unique identifiers listed in the following table. You then give the identifiers to the developer when you integrate ADAL with the app. For more information about these identifier values, see [Microsoft Azure Active Directory Authentication Library (ADAL) for Android](https://github.com/AzureAD/azure-activedirectory-library-for-android/blob/master/README.md).

|Identifier|More information|Default value|
|--------------|--------------------|-----------------|
|**Client ID**|A unique GUID identifier that is generated for the app after it is registered with AAD.<br /><br />If you know the app's Client ID, specify that value. Otherwise, use the default value.|6c7e8096-f593-4d72-807f-a5f86dcc9c77|
|**Authority URI**|The authority Uniform Resource Identifier (URI) value for AAD) objects (for example, users and groups).<br /><br />The AuthorityURI parameter is optional for the app wrapping tool. The default URI is used if you don't use the parameter.|https://login.windows.net/common/|
|**SkipBroker**|Value indicating whether the company portal will be used as a broker.<br /><br />**True** – company portal will not be used for ADAL authentication.<br /><br />**False** – company portal will be used for ADAL authentication. The company portal is using the enrolled user for Single Sign On purposes.||
|**Non-Broker Redirect URI**|Login URI to be used when ADAL does not use the broker app (Intune company portal).|urn:ietf:wg:oauth:2.0:oob|
|**Resource ID**|Pointer to the app's AAD resources.|https://intunemam.microsoftonline.com|

### <a name="BKMK_AD"></a>Step 3: Configure access to mobile application management in AAD
Before you can use an app’s AAD registration values in the app wrapping tool, the application developer must grant that application access to the Intune Mobile Application Management resource by following these steps:

1.  Log into an existing AAD account in the Azure management portal.

2.  Click **existing LOB application registration**.

3.  In the **configure** section, choose **Configure Access to Web APIs in other applications**.

4.  From the first drop-down list in the **Permission to other applications** section, choose **Intune Mobile Application Management**.

You can now use the app’s Client ID in the app wrapping tool. You can find the Client ID in the Azure Active Directory management portal, as described in the table in [Step 2: Review the identifiers that you need to get when you register the app](#BKMK_review_IDs).

### Step 4: Use the AAD identifier values in the app wrapping tool
Using the identifier values that you got from the registration process, enter the values as command-line properties in the app wrapping tool. You must specify all of the values in the table in order for end users to successfully authenticate the app. Default values are used if you don't specify a value.

|Identifier|Parameter|
|--------------|-------------|
|Client ID|ClientID|
|Authority URI|Authority-URI|
|SkipBroker|SkipBroker|
|Non-Broker Redirect URI|NonBrokerRedirectURI|
|Resource ID|ResourceID|
Keep the following points in mind as you wrap your app:

-   The app wrapping tool does not search for ADAL binaries (if any) within the app. If the app links to an outdated version of the binaries, runtime errors may occur during login if you enabled authentication policies.

-   To verify that the authentication was successful,
                        [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] fetches the AAD token that is associated with the MAM resource-id. However, the token is not used in any call that would in turn verify the validity of the token. [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] only reads the user principal name (UPN) of the signed-in user to determine app access. The AAD token is not used for any further service calls.

-   Authentication tokens are shared between apps from the same publisher since they are stored in a shared keychain. To isolate a specific app, use a different signing certificate, provisioning profile keystore, and key alias for that app.

-   Double login prompts are prevented if you provide your client application’s Client ID and Authority URI. You need to register the Client ID to enable it to access the published [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] MAM resource ID in the AAD Dashboard. If you don't register the Client ID, users get a login failure when the app runs.

## Next Steps
To learn more about how to deploy your wrapped apps, see [Deploy apps to mobile devices in Microsoft Intune - deleted](../Topic/Deploy_apps_to_mobile_devices_in_Microsoft_Intune_-_deleted.md).

## See Also
[Configure and deploy mobile application management policies in the Microsoft Intune console](../Topic/Configure_and_deploy_mobile_application_management_policies_in_the_Microsoft_Intune_console.md)

