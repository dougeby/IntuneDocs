---
# required metadata

title: Create app notifications for iOS devices - Microsoft Intune - Azure | Microsoft Docs
description: Add or create app notifications for iOS devices in Microsoft Intune. Choose which apps to send notifications, configure the notification settings on the lock screen, enable sound, choose the type of alert, and add a badge.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
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

# Configure app notifications settings on iOS devices in Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Configure how installed apps on an iOS device send notifications. These settings support supervised devices running iOS 9.3 and later.

## Add the app notification

1. Sign in to the [Azure Portal](https://portal.azure.com).
2. Within your iOS or macOS profile, select **Device features**. [iOS or macOS device features](device-features-configure.md) lists the steps to create a profile.
3. Select **App Notifications (supervised only)**, and then select **Add**: 
  ![Add app notification in iOS or macOS profile in Intune](./media/ios-macos-app-notifications.png)
4. Enter the following properties:

  - **App bundle ID**: Enter the **App Bundle ID** of the app you want to configure. **Bundle ID reference for built-in iOS apps** (in this article) provides some help.
  - **App name**: Enter the name of the app you want to configure. This name is not displayed on the device and is used to help you identify the app in the list.
  - **Publisher**: Enter the publisher of the app you want to configure. The publisher name is not displayed on the device, and is used only to help you identify the app in the list.
  - **Notifications**: Enable or disable the app from sending notifications to the device. If you disable this setting, the following settings are also disabled.
    - **Show in Notification Center** - Enable this setting to allow the app to show notifications in the device Notification Center.
    - **Show in Lock Screen** - Enable this setting to see notifications from the app on the device lock screen.
    - **Alert type** - Select the type of notification you want when the device is unlocked from:
      - **None** - No notification is displayed.
      - **Banner** - A banner is briefly displayed showing the notification.
      - **Modal** - The notification is displayed and the user must manually dismiss it before you can continue to use the device.
    - **Badge on app icon** - Enable this setting to add a badge to the app icon to indicate the app sent a notification.
    - **Sounds** - Enable this setting to play a sound when a notification is delivered.

5. Continue to add as many apps as you need. When finished adding apps, select **OK**.
6. Select **Create** to save your profile.

## Bundle ID reference for built-in iOS apps

The following list shows the bundle ID of some common built-in iOS apps. To find the bundle ID of other apps, it's best to contact your software vendor.

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

Assign the device profile to the groups you choose. [How to assign device profiles](device-profile-assign.md) lists the steps.