---
# required metadata

title: Add app configuration policies for managed iOS devices | Microsoft Docs
titlesuffix: "Azure portal"
description: Learn how to use app configuration policies to provide configuration data to an iOS app when it is run.
keywords:
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 10/31/2017
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

Use app configuration policies in Microsoft Intune to supply settings when users run an iOS app. You do not assign these policies directly to users and devices. Instead, you associate a policy with an app, and then assign the app. The policy settings are used when the app checks for them, typically the first time it is run.

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
4. Choose **App configuration policies** in the **Manage** group, and then choose **Add**.
5. Set the following details:
    - **Name**<br>
      The name of the profile that will appear in the Azure portal.
    - **Description**<br>
      The description of the profile that will appear in the Azure portal.
    - **Device enrollment type**<br>
      Choose **Managed devices**.
6. Select **iOS** for **Platform**.
7.	Choose **Associated App**. Then, on the **Associated App** blade, choose the managed app to which you want to apply the configuration.
8.	On the **Add Configuration Policy** blade, choose **Configuration settings**.
9. Select **Configuration settings format**. Select one of the following:
    - **[Use configuration designer](#use-configuration-designer)**
    - **[Enter XML data](#enter-xml-data)**
10. Once you have added your XML information, choose **OK**, and then choose **Add**.

## Use configuration designer

You can use the configuration designer for apps on devices that are enrolled or not enrolled in Intune. The designer lets you configure specific configuration keys and values. You must also specify the data type for each value. Settings are supplied to apps automatically when they're installed.

### Add a setting

1. For each key and value in the configuration, set:
   - **Configuration key**<br>
     The key that uniquely identifies the specific setting configuration.
   - **Value type**<br>
     The data type of the configuration value. Types include Integer, Real, String, or Boolean.
   - **Configuration value**<br>
     The value for the configuration.
2. Choose **OK** to set your configuration settings.

### Delete a setting

1. Choose the ellipsis (**...**) next to the setting.
2. Select **Delete**.

The \{\{ and \}\} characters are used by token types only and must not be used for other purposes.

## Enter XML data

You can type or paste an XML property list that contains the app configuration settings for devices enrolled in Intune. The format of the XML property list varies depending on the app that you are configuring. For details about the exact format to use, contact the supplier of the app.

Intune validates the XML format. However, Intune does not check that the XML property list (PList) will work with the target app.

To learn more about XML property lists:

  -  Read [Configure iOS apps with mobile app configuration policies in Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).
  -  Refer to [Understand XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in the iOS Developer Library.

### Example format for an app configuration XML file

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
### Supported XML PList data types

Intune supports the following data types in a property list:

- &lt;integer&gt;
- &lt;real&gt;
- &lt;string&gt;
- &lt;array&gt;
- &lt;dict&gt;
- &lt;true /&gt; or &lt;false /&gt;

### Tokens used in the property list

Additionally, Intune supports the following token types in the property list:
- \{\{userprincipalname\}\}—for example, **John@contoso.com**
- \{\{mail\}\}—for example, **John@contoso.com**
- \{\{partialupn\}\}—for example, **John**
- \{\{accountid\}\}—for example, **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- \{\{deviceid\}\}—for example, **b9841cd9-9843-405f-be28-b2265c59ef97**
- \{\{userid\}\}—for example, **3ec2c00f-b125-4519-acf0-302ac3761822**
- \{\{username\}\}—for example, **John Doe**
- \{\{serialnumber\}\}—for example, **F4KN99ZUG5V2** (for iOS devices)
- \{\{serialnumberlast4digits\}\}—for example, **G5V2** (for iOS devices)

## Next steps

Continue to [assign](apps-deploy.md) and [monitor](apps-monitor.md) the app as usual.