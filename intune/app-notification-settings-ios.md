---
# required metadata

title: Intune app notification settings for iOS devices
titleSuffix: "Intune on Azure"
description: Learn the settings you can use to control notifications from apps on iOS devices."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Intune app notifications settings for IOS devices

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Lets you configure how apps installed on a device send notifications. This settings supports supervised devices running iOS 9.3 and later.

## Configure settings

1. On the **Device features** blade choose **App Notifications (supervised only)**.
2. On the **App Notifications** blade, choose **Add**, and then configure the following values:
	- **App bundle ID** - Enter the **App Bundle ID** of the app you want to configure. See **Bundle ID reference for built-in iOS apps** later in this topic for help.
	- **App name** - Enter the name of the app you want to configure. This is not displayed on the device and is used to help you identify the app in the list.
	- **Publisher** - Enter the publisher of the app you want to configure. This is not displayed on the device and is used to help you identify the app in the list.
	- **Notifications** - Enable or disable the app from sending notifications to the device. If you disable this setting, the following settings are also disabled.
		- **Show in Notification Center** - Enable to allow the app to show notifications in the device Notification Center.
		- **Show in Lock Screen** - Enable to see notifications from the app on the device lock screen.
		- **Alert type** - Select the type of notification you want when the device is unlocked from:
			- **None** - No notification is displayed.
			- **Banner** - A banner is briefly displayed showing the notification.
			- **Modal** - The notification is displayed and the user must manually dismiss it before you can continue to use the device.
		- **Badge on app icon** - Enable this to add a badge to the app icon to indicate the app sent a notification.
		- **Sounds** - Enable to play a sound when a notification is delivered.
3. Continue to add as many apps as you need. When you are finished, choose **OK**.
4. Choose **OK** until you return to the **Create Profile** blade, then choose **Create**. 


## Bundle ID reference for built-in iOS apps

This list shows the bundle ID of some common built-in iOS apps. To find the bundle ID of other apps, contact your software vendor. 

|||
|-|-|
|App name|BundleID|
|App Store|com.apple.AppStore|
|Calculator|com.apple.calculator|
|Calendar|com.apple.mobilecal|
|Camera|com.apple.camera|
|Clock|com.apple.mobiletimer|
|Compass|com.apple.compass|
|Contacts|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Find Friends|com.apple.mobileme.fmf1|
|Find iPhone|com.apple.mobileme.fmip1|
|Game Center|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Health|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.apple.itunesu|
|Keynote|com.apple.Keynote|
|Mail|com.apple.mobilemail|
|Maps|com.apple.Maps|
|Messages|com.apple.MobileSMS|
|Music|com.apple.Music|
|News|com.apple.news|
|Notes|com.apple.mobilenotes|
|Numbers|com.apple.Numbers|
|Pages|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Photos|com.apple.mobileslideshow|
|Podcasts|com.apple.podcasts|
|Reminders|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Settings|com.apple.Preferences|
|Stocks|com.apple.stocks|
|Tips|com.apple.tips|
|Videos|com.apple.videos|
|VoiceMemos|com.apple.VoiceMemos|
|Wallet|com.apple.Passbook|
|Watch|com.apple.Bridge|
|Weather|com.apple.weather|

## Next steps

You can now assign the device profile to the groups you choose. For details, see [How to assign device profiles](device-profile-assign.md).