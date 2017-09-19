---
# required metadata

title: Intune Home screen layout settings for iOS devices
titlesuffix: "Azure portal"
description: Learn the settings you can use customize the home screen and dock on iOS devices."
keywords:
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6aba4491-afb9-43cd-9ccc-14e6a2a5a3b1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: karanda
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Intune Home screen layout settings for iOS devices

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use these settings to configure the layout of apps and folder on the dock and Home screen of iOS.

iOS devices to which you assign the profile must be in supervised mode and running iOS 9.3 or later.

1. On the **Device features** blades choose **Home Screen Layout (supervised only)**.
2. On the **Home Screen Layout (supervised only)** blade, choose whether you want to configure the **Dock**, or **Pages** layouts.

## Add items to the dock

On the **Dock** blade, you can add up to six items or folders to the dock of the iOS screen. However, many devices support fewer items; for example, iPhone devices support up to four items. In this case, only the first four items you configured are displayed on the device.

1. Choose **Add** to add an item to the dock.
2. On the **Add Row** blade, choose whether you want to add an **App**, or a **Folder**.
3. Using the information in this topic, configure the apps and folders you want to appear in the dock.
4. Continue to add items. When you are finished, click **OK** on each blade until you return to the **Create Profile** blade. Choose **Create**.

>[!TIP]
> You can drag and drop items in any Home screen and pages lists to reorder them. 

### Example

In this example, you've configured the dock screen to show only the Safari, Mail, and Stocks apps. In the following image, the Mail app is selected to illustrate its properties:

![Sample iOS dock settings](http://i.imgur.com/FfFiUcP.png)

When you assign the policy to an iPhone, the result is a dock that looks similar to this screenshot:

![Sample iOS dock layout on iPhone](http://i.imgur.com/bAgCe8F.png)

## Add Home screen pages

Add the pages you want to appear on the home screen, and the apps that appear on each page. Apps that you add to a page are arranged from left to right, in the order they are specified in the list. If you add more apps than can fit on a page, the apps are moved to a subsequent page.


1. On the **Pages** blade, choose **Add**.
2. On the **Add Row** blade, enter a **Page name**. This name is used for your reference in the Azure portal, and *is not displayed* on the iOS device.
3. Choose **Add**, then choose whether you want to add an **App**, or a **Folder** to the page.
4. Using the information in this topic, configure the apps and folders you want to appear on the page.

### Example

In this example, you've configured a new page named **Contoso**. The page shows only the Find Friends, and Settings apps. In the following image, the Settings app is selected to illustrate its properties:

![iOS Home screen settings example](http://i.imgur.com/Jc2OxyX.png)

When you assign the policy to an iPhone, the result is a page that looks similar to this screenshot:

![iOS device with modified home screen](http://i.imgur.com/Bd37PHa.png)

## How to add an app to the list

1. Enter the **App Name**. This name is used for your reference in the Azure portal, and *is not displayed* on the iOS device.
2. Enter the **App Bundle ID** of the app you want to display. See **Bundle ID reference for built-in iOS apps** later in this topic for help.
3. Click **OK**, then continue to add items, up to a maximum of **6** for the device dock, and **60** for a device page.
4. When you are finished, click **OK**.

## How to add a folder to the list

Apps that you add to a page in a folder are arranged from left to right, in the order they are specified in the list. If you add more apps than can fit on a page, the apps are moved to a subsequent page.

1. Enter the **Folder name**. This name is displayed to users on their device.
2. Choose **Add** to create a page in the folder. You can add up to 20 pages.
3. On the **Add Row** blade, enter a name for the page. This name is used for your reference in the Azure portal, and *is not displayed* on the iOS device.
3. Enter the **App Name**. This name is used for your reference in the Azure portal, and *is not displayed* on the iOS device.
2. Enter the **App Bundle ID** of the app you want to display. See **How to add an app to the list** for help.
3. Choose **Add**. You can add up to 60 items.
4. When you are finished, click **OK**.


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