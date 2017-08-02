---
# required metadata

title: Android apps with app protection policies
titleSuffix: "Intune on Azure"
description: This topic describes what to expect when your Android app is managed by app protection policies."
keywords:
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: andcerat
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# What to expect when your Android app is managed by app protection policies 

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

This topic describes the user experience for apps with app protection policies. App protection polices are applied only when apps are used in the work context: like accessing apps using your work account, or accessing files stored in your company OneDrive business location.
##  Accessing apps

The Company Portal app is required for all apps associated with app protection policies on Android devices.

For devices not enrolled in Intune, the Company Portal app must be installed on the device. However, user does not have to launch  or sign into the Company Portal app before they can use apps managed by app protection policies.
The Company Portal app is a way for Intune to share data in a secure location, hence this is a requirement even if the device is not enrolled in Intune.


##  Using apps with multi-identity support

App protection polices are only applied in the work context when using the app, so you may see different app behaviors depending on the context: work or personal.

For apps that support multi-identity, Intune only applies the app protection policies when the end-user is using the app in the work context.  For example, the end-user will get a PIN prompt when accessing work data.  For the **Outlook app**, the end-user is prompted for a PIN on launching the app. For the **OneDrive app**, this happens when the end-user types in the work account.  For Microsoft **Word**, **PowerPoint*, and **Excel**, this happens when the end-user accesses documents stored in the company OneDrive for Business location.
##  Managing user accounts on the device

Intune only supports deploying app protection policies to only one user account per device.

* Depending on the app that you are using, the second user may or may not be blocked on the device. However, in all cases, only the first user who gets the app protection policies is affected by the policy.

  * **Microsoft Word**, **Excel**, and **PowerPoint** don't block a second user account, but the second user account is not affected by the app protection policies.

  * For **OneDrive and Outlook apps**, you can only use one work account.  Adding multiple work accounts are blocked on these apps.  You can however, remove a user and add a different user on the device.


* If a device has existing multiple user accounts before the app protection policies are deployed, the account that the app protection policies is deployed to first is managed by Intune app protection policies.


Read the example scenario below to get a deeper understanding of how multiple user accounts are treated.

User A works for two companies - **Company X**, and **Company Y**. User A has a work account for each company, and both use Intune to deploy app protection policies. **Company X** deploys app protection policies **before** **Company Y**. The account associated with **Company X** will get the app protection policy, but not the account associated with Company Y. If you want the user account associated with Company Y to be managed by the app protection policies, you must remove the user account associated with Company X.
### Adding a second account
####  Android
If you are using an Android device, you may see a blocking message with instructions to remove the existing account and add a new one.  To remove the existing account, go to **Settings  &gt;General &gt; Application Manager &gt;Company Portal and select "Clear Data"**.

![Screenshot of the error message and instructions to remove the account](./media/android-switch-user.png)

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
## Next steps
[What to expect when your iOS app is managed by app protection policies](app-protection-enabled-apps-ios.md)

### See also
[Create and deploy app protection policies with Microsoft Intune](app-protection-policies.md)
