---
# required metadata

title: How to use app configuration policies - Intune | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn how to use app configuration policies to provide configuration data to an iOS app when it is run."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/18/2016
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
#ms.custom:
---

# How to use app configuration policies with Intune Azure preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use app configuration policies in Microsoft Intune to supply settings that might be required when users run an app. For example, an app might require users to specify:

-   A custom port number.

-   Language settings.

-   Security settings.

-   Branding settings such as a company logo.

If users enter these settings incorrectly, this can increase the burden on your help desk and slow the adoption of new apps.

App configuration policies can help you eliminate these problems by letting you assign these settings to users in a policy before they run the app. The settings are then supplied automatically, and users need to take no action.

You do not assign these policies directly to users and devices. Instead, you associate a policy with an app, and then deploy the app. The policy settings will be used whenever the app checks for them (typically, the first time it is run).

> [!TIP]
> This policy type is currently available only for devices running iOS 8.0 and later. It supports the following app installation types:
>
> -   **Managed iOS app from the app store**
> -   **App package for iOS**
>
> For more information about app installation types, see [How to add an app to Microsoft Intune](/intune-azure/manage-apps/add-apps).

## Create an app configuration policy

1. Sign into the Azure portal.
2. Choose **More Services** > **Other** > **Intune**.
3. On the **Intune** blade, choose **Manage apps**.
1.  In the **Manage apps** workload, choose **Manage** > **App Configuration Policies**.

2.  In the list of policies blade, choose **Add**.

3.  On the **Add Configuration Policy** blade, supply a name and an optional description for the app configuration policy.
4.  Choose **Associated App**, then, on the **Associated App** blade, choose the managed app to which you want to apply the configuration.
5.  On the **Add Configuration Policy** blade, choose **Configuration settings** and then, on the Configuration Settings blade, choose how you want to specify the XML values that make up the configuration profile from:
	- **Enter XML data** - enter or paste an  XML property list that contains the app configuration settings that you want. The format of the XML property list will vary depending on the app you are configuring. Contact the supplier of the app for details about the exact format to use.
	Intune checks that the XML you entered is in a valid format. It does not check that the XML property list will work with the app that it is associated with.
	To find out more about XML property lists, see [Understanding XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in the iOS Developer Library.
	- **Use configuration designer** - Lets you specify XML key and value pairs directly in the portal.
8. When you're done, go back to the **Add Configuration Policy** blade, and hit **Create**.

The policy will be created and appears on the policies list blade.

Then, continue to [assign](deploy-apps.md) and [monitor](monitor-apps.md) the app as usual.

When the assigned app is run on a device, it will run with the settings that you configured in the app configuration policy.

> [!TIP]
> If one or more app configuration policies conflict, neither policy is enforced.

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
