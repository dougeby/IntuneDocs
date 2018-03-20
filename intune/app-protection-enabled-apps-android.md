---
# required metadata

title: Android apps with app protection policies
titlesuffix: Microsoft Intune
description: Learn what to expect from an Android app that has protection policies.
keywords:
author: erikre
ms.author: erikre
manager: dougeby
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

Learn what expect from Androids apps with app protection policies. App protection polices are applied only when apps are used in the work context. For example, when you access an app with a work account, or when you access files stored in your company OneDrive location.
##  Accessing apps

The Company Portal app is required for all apps on Android devices that have app protection policies.

Install the Company Portal on all devices that aren't enrolled in Intune. Users aren't required to sign in to the Company Portal app to use apps that have app protection policies.
The Company Portal app lets you share data in a secure location. So it's a requirement even for unenrolled devices.


##  Using apps with multi-identity support

App protection policies only take effect when a user tries to access work-related data.  You may see different behaviors if the user accesses the app for personal use.

Some apps support multi-identity. In this case, Intune only applies app protection policies when a user accesses work data.  For example, a user may get a PIN prompt.  In the **Outlook app**, a prompt occurs when a user launches the app. In the **OneDrive app**, a prompt occurs when a user types in the work account.  In Microsoft **Word**, **PowerPoint**, and **Excel**, a prompt occurs when a user accesses company OneDrive documents.
##  Managing user accounts on the device

Intune supports deploying app protection policies to one user account per device.

* Depending on the app that you are using, the second user may or may not be blocked on the device. However, in all cases, only the first user who gets the app protection policies is affected by the policy.

  * **Microsoft Word**, **Excel**, and **PowerPoint** won't block access to an additional user account. However, the user account will not be affected by the app protection policies.

  * For **OneDrive and Outlook apps**, you can only use one work account.  Adding multiple work accounts are blocked on these apps.  However, you can remove a user from a device, and then add a different user to the device.


* Prior to app protection policy deployment, a device may have multiple existing user accounts. In this case, the first account that the app protection policies are deployed to is managed by Intune app protection policies.


Read the following example scenario to learn how Intune handles multiple user accounts.

User A works for two companies: **Company X**, and **Company Y**. User A has a work account for each company, and both use Intune to deploy app protection policies. **Company X** deploys app protection policies **before** **Company Y**. The account associated with **Company X** will get the app protection policy, but not the account associated with Company Y. To have the Company Y user account managed by the app protection policies, User A must remove the Company X user account.
### Adding a second account
####  Android
You may receive a prompt to remove the existing account and add a new one.  To remove the existing account, go to **Settings  &gt;General &gt; Application Manager &gt;Company Portal. Then select "Clear Data."**

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
|Pfile is a generic “wrapper” format for protected files. It encapsulates the encrypted content and the Azure Information Protection licenses. It can be used to protect any file type.|Text files, including XML, CSV, etc. can be opened for viewing in the app even when they are protected. File types: txt, ptxt, csv, pcsv, log, plog, xml, pxml.|
---------------
## Next steps
[What to expect when your iOS app is managed by app protection policies](app-protection-enabled-apps-ios.md)

### See also
[Create and deploy app protection policies with Microsoft Intune](app-protection-policies.md)
