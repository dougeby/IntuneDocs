---
# required metadata

title: Android apps with MAM policies | Microsoft Intune
description: This topic describes what to expect when your app is managed by mobile app management policies.
keywords:
author: karthikaraman
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: andcerat
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# What to expect when your Android app is managed by MAM policies
This topic describes the user experience for apps with MAM policies. Mobile application management (MAM) polices are applied only when apps are used in the work context: like accessing apps using your work account, or accessing files stored in your company OneDrive business location.
##  Accessing apps

The Company Portal app is required for all apps associated with MAM policies on Android devices.

For devices not enrolled in Intune, the Company Portal app must be installed on the device. However, user does not have to launch  or sign into the Company Portal app before they can use apps managed by MAM policies.
The Company Portal app is a way for Intune to share data in a secure location, hence this is a requirement even if the device is not enrolled in Intune.


##  Using apps with multi-identity support

MAM polices are only applied in the work context when using the app, so you may see different app behaviors depending on the context: work or personal.

For apps that support multi-identity, Intune only applies the MAM policies when the end-user is using the app in the work context.  For example, the end-user will get a PIN prompt when accessing work data.  For the **Outlook app**, the end-user is prompted for a PIN on launching the app. For the **OneDrive app**, this happens when the end-user types in the work account.  For Microsoft **Word**, **PowerPoint*, and **Excel**, this happens when the end-user accesses documents stored in the company OneDrive for Business location.
##  Managing user accounts on the device

Intune only supports deploying MAM policies to only one user account per device.

* Depending on the app that you are using, the second user may or may not be blocked on the device. However, in all cases, only the first user who gets the MAM policies is affected by the policy.

  * **Microsoft Word**, **Excel**, and **PowerPoint** don't block a second user account, but the second user account is not affected by the MAM policies.

  * For **OneDrive and Outlook apps**, you can only use one work account.  Adding multiple work accounts are blocked on these apps.  You can however, remove a user and add a different user on the device.


* If a device has existing multiple user accounts before the MAM policies are deployed, the account that the MAM policies is deployed to first is managed by Intune MAM policies.


Read the example scenario below to get a deeper understanding of how multiple user accounts are treated.

User A works for two companies - **Company X**, and **Company Y**. User A has a work account for each company, and both use Intune to deploy MAM policies. **Company X** deploys MAM policies **before** **Company Y**. The account associated with **Company X** will get the MAM policy, but not the account associated with Company Y. If you want the user account associated with Company Y to be managed by the MAM policies, you must remove the user account associated with Company X.
### Adding a second account
####  Android
If you are using an Android device, you may see a blocking message with instructions to remove the existing account and add a new one.  To remove the existing account, go to **Settings  &gt;General &gt; Application Manager &gt;Company Portal and select "Clear Data"**.

![Screenshot of the error message and instructions to remove the account](../media/AppManagement/Android_SwitchUser.png)

##  Viewing media files with the Azure Information Protection app (previously known as Rights Management sharing app)
To view company AV, PDF, and image files on Android devices, use the [Azure Information Protection app](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).

Download this app from the  Google Play store.  

The following filetypes are supported:

* **Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (enhanced AAC+), AAC ELD (enhanced low delay AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.
* **Video:** H.263, H.264 AVC, MPEG-4 SP, VP8.
* **Image:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.
* **Documents:** PDF, PPDF

------------
|**pfile**|**text**|
|----|----|
|Pfile is a generic “wrapper” format for protected files that encapsulates the encrypted content and the Azure Information Protection licenses and can be used to protect any file type.|Text files, including XML, CSV, etc. can be opened for viewing in the app even when they are protected. File types: txt, ptxt, csv, pcsv, log, plog, xml, pxml.|
---------------


### See also
[Create and deploy mobile app management policies with Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)
