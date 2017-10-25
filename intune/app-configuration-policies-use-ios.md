---
# required metadata

title: Add app configuration policies for managed iOS devices | Microsoft Docs
titlesuffix: "Azure portal"
description: Learn how to use app configuration policies to provide configuration data to an iOS app when it is run.
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/27/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Add app configuration policies for managed iOS devices

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use app configuration policies in Microsoft Intune to supply settings that are used when users run an iOS app. For example, an app might require users to specify:

-   A custom port number.
-   Language settings.
-   Security settings.
-   Branding settings such as a company logo.

If users enter these settings incorrectly, it can increase the burden on your help desk and slow the adoption of new apps.

App configuration policies can help you eliminate these problems by letting you assign these settings to users in a policy before they run the app. The settings are then supplied automatically, and users need to take no action. Apps must have been written to support the use of app configurations. Consult your app vendor for more information.

You do not assign these policies directly to users and devices. Instead, you associate a policy with an app, and then assign the app. The policy settings are used whenever the app checks for them (typically, the first time it is run).

> [!TIP]
> This policy type is currently available only for devices running iOS 8.0 and later. It supports the following app installation types:
>
> -   **Managed iOS app from the app store**
> -   **App package for iOS**
>
> For more information about app installation types, see [How to add an app to Microsoft Intune](apps-add.md).

## Create an app configuration policy

1. Sign in to the Azure portal.
2. Choose **More Services** > **Monitoring + Management** + **Intune**.
3. Choose the **Mobile apps** workload.
4. Click **App configuration policies** in the **Manage** group, and then click **Add**.
5. Set the following details:
    - **Name**  
      The name of the profile that will appear in the Azure portal.
    - **Description**  
      The  description of the profile that will appear in the Azure portal.
    - **Device enrollment type**  
      Choose **Managed devices**.
6. Select **iOS** for the **Platform.
7.	Choose **Associated App**, then, on the **Associated App** blade, choose the managed app to which you want to apply the configuration.
8.	On the **Add Configuration Policy** blade, choose **Configuration settings**
9. On the **Configuration Settings** blade, choose how you want to specify the XML values that make up the configuration profile from:
	- **Enter XML data** (for devices enrolled with Intune only) - Enter or paste an XML property list that contains the app configuration settings that you want. The format of the XML property list varies depending on the app you are configuring. Contact the supplier of the app for details about the exact format to use.
Intune checks that the XML you entered is in a valid format. It does not check that the XML property list works with the app that it is associated with.
To find out more about XML property lists, see [Understanding XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in the iOS Developer Library.
	- **Use configuration designer** (whether or not the device is enrolled with Intune) - Lets you specify XML key and value pairs directly in the portal.
11.	When you're done, go back to the **Add Configuration Policy** blade, and hit **Create**.

The policy is created and appears on the policies list blade.



>[!Note]
>You can use the [Intune App SDK](https://docs.microsoft.com/intune/app-sdk-ios) to prepare line-of-business apps to be managed by Intune app protection policies, and app configuration policies, whether the device is enrolled with Intune or not. For example, you can use an app configuration policy to configure allowed and blocked URLs for the [Intune Managed Browser](app-configuration-managed-browser.md). Once an app is compatible with these policies, you can configure them using a policy.


When the assigned app is run on a device, it runs with the settings that you configured in the app configuration policy.
See the documentation for the app you are configuring for information about what happens if one or more app configuration policies conflict.

>[!Tip]
>Additionally, you can use Graph API to accomplish these tasks. For details, see [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).


## Information about the XML file format

Intune supports the following data types in a property list:

- &lt;integer&gt;
- &lt;real&gt;
- &lt;string&gt;
- &lt;array&gt;
- &lt;dict&gt;
- &lt;true /&gt; or &lt;false /&gt;

For more information about data types, see [About Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) in the iOS Developer Library.

Additionally, Intune supports the following token types in the property list:
- \{\{userprincipalname\}\} - (Example: **John@contoso.com**)
- \{\{mail\}\} - (Example: **John@contoso.com**)
- \{\{partialupn\}\} - (Example: **John**)
- \{\{accountid\}\} - (Example: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} - (Example: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} - (Example: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} - (Example: **John Doe**)
- \{\{serialnumber\}\} - (Example: **F4KN99ZUG5V2**) for iOS devices
- \{\{serialnumberlast4digits\}\} - (Example: **G5V2**) for iOS devices

The \{\{ and \}\} characters are used by token types only and must not be used for other purposes.

## Example format for an app configuration XML file

When you create an app configuration file, you can specify one or more of the following values by using this format:

```
<dict>
  <key>userprincipalname</key>
  <string>{{userprincipalname}}</string>
  <key>mail</key>
  <string>{{mail}}</string>
  <key>partialupn</key>
  <string>{{partialupn}}</string>
  <key>accountid</key>
  <string>{{accountid}}</string>
  <key>deviceid</key>
  <string>{{deviceid}}</string>
  <key>userid</key>
  <string>{{userid}}</string>
  <key>username</key>
  <string>{{username}}</string>
  <key>serialnumber</key>
  <string>{{serialnumber}}</string>
  <key>serialnumberlast4digits</key>
  <string>{{serialnumberlast4digits}}</string>
  <key>udidlast4digits</key>
  <string>{{udidlast4digits}}</string>
</dict>

```

## Next steps

Continue to [assign](apps-deploy.md) and [monitor](apps-monitor.md) the app as usual.