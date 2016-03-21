---
title: Decide how to prepare apps for mobile application management with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
author: Staciebarker
---
# Decide how to prepare apps for mobile application management with Microsoft Intune
You can enable your apps to use mobile application management policies by using either the Intune App Wrapping Tool or the Intune App SDK. Use this information to learn about these two methods and when to use them.

## Intune App Wrapping Tool
The App Wrapping Tool is used primarily for internal line-of-business (LOB) apps. The tool is a command line application that creates a wrapper around the app, which then allows the app to be managed by an Intune mobile application management policy. You don't need the source code to use the tool, but you do need signing credentials.  For more about signing credentials, see the [Intune blog](http://blogs.technet.com/b/microsoftintune/archive/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios.aspx). For the App Wrapping Tool documentation, see [Android App Wrapping Tool ](https://technet.microsoft.com/library/mt147413.aspx) and [iOS App Wrapping Tool](https://technet.microsoft.com/library/dn878028.aspx).

The App Wrapping Tool does not support Apps in the App or Play Store or features that require development time integration (see the following feature comparison table).

You should use the App Wrapping Tool, rather than the SDK, if the  app has already been written or if the source code isn't available.

## Intune App SDK
The App SDK is designed mainly for customers who have apps in the App or Play stores and want to be able to manage the apps with Intune. However, any app can take advantage of integrating the SDK, even if it’s a LOB app.

To integrate the SDK, you need access to the app’s source code. For instructions on integrating the SDK, see [Microsoft Intune App SDK](https://msdn.microsoft.com/library/mt627769.aspx).

## Feature comparison
This table lists the settings that you can use for the App SDK and App Wrapping Tool.

> [!NOTE]
> The App Wrapping Tool can be used only when you are using  either Intune Standalone or Intune with Configuration Manager.

|Feature|App SDK|App Wrapping Tool|
|-----------|---------------------|-----------|
|Restrict web content to display in a corporate managed browser|X|X|
|Prevent Android, iTunes or iCloud backups|X|X|
|Allow app to transfer data to other apps|X|X|
|Allow app to receive data from other apps|X|X|
|Restrict cut, copy and paste with other apps|X|X|
|Require simple PIN for access|X|X|
|Replace built-in app PIN with Intune PIN|X||
|Specify the number of attempts before PIN reset|X|X|
|Require fingerprint instead of PIN (iOS only)<br></br>**Note:** Only available in MAM-only environments.|X||
|Require corporate credentials for access|X|X|
|Block managed apps from running on jailbroken or rooted devices|X|X|
|Encrypt app data|X|X|
|Recheck the access requirements after a specified number of minutes|X|X|
|Specify the offline grace period|X|X|
|Block screen capture (Android only)|X|X|
|Full Wipe|X|X|
|Selective Wipe <br></br>**Note:** For iOS, when the management profile is removed, the app is also removed.|X||
|Prevent “Save as” |X||
|Support for Multi-Identity|X||
