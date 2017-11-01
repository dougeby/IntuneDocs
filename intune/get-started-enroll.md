---
# required metadata

title: Getting started enrolling devices
titlesuffix: "Azure portal"
description: Learn the enrollment experience by going through a full enrollment experience of an iOS device.
keywords:
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b595848d-c451-43ab-812d-b22e0170fb7a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Get started enrolling devices

Microsoft Intune helps you enable your workforce with mobile devices while keeping your corporate data protected. Since your end users will interact with Intune on their devices rather than in the admin console, you want to make sure that you are fluent with the enrollment experience. This way, you can combine well-crafted compliance policies with your experience to show empathy for your users. This is especially important because your users will know exactly what information that you as an admin can see:

| What IT cannot see | What IT can see |
|---|---|
| Calling and web browsing history | Model |
| Location | Serial number |
| Personal email | Operating system version |
| Text messages | App names |
| Contacts | Owner |
| Passwords to your personal accounts | Device name |
| Calendar events | Manufacturer (for devices not made by Apple) |
| Pictures, including what's in the photos app or camera roll | Phone number (for work devices, the whole number. For personal devices, just the last four digits.) |
​
## How do I enroll a device?

Enrolling a device is the first experience that many end users will have with accessing corporate resources. [Understanding that experience](end-user-educate.md) can help make a potentially unpleasant experience into a better one.

1. Open the **App Store** and search for **Intune Company Portal**.
2. Download the **Microsoft Intune Company Portal** app.
3. Open the **Company Portal** app, enter your test user’s email address and password, then tap **Sign in**.
4. Update the temporary password to a new one.
5. On the **Company Access Setup** page, tap **Device Enrollment**.
6. On the **Why enroll your device?** page, read about what a user can do when they enroll their device, then tap **Continue**.
7. Review a list of what access a user gets when they enroll, then tap **Continue**.
8. Review what IT admins can and can’t see on a device, then tap **Continue**.
9. On the **What comes next** page, read about what happens during enrollment, then tap **Enroll**.
10. On the **Install Profile** page, tap **Install**, then enter the device passcode if prompted.
11. Tap **Install**.
12. Tap **Install** again to indicate that you’ve read the warning.
13. On the **Warning** popup, tap **Trust**.
14. When the screen changes to show that the profile has finished installing, tap **Done**.
15. An “Enrolling device” message shows on the screen, then shows that the device has successfully enrolled. A popup will appear asking to open the page in the Company Portal. Tap **Open**.
16. You return to the **Company Access Setup** screen. If you have no test policies set up, then the device should appear compliant. If you have any test policies, then tapping **Device Compliance** will show that there are things that need to be done to make the device secure.

## Next steps

[Get started with adding apps](get-started-apps.md) - Find and add apps to devices to make it possible for your employees to get work done.

## Learn more

* [Enrollment options for Intune](enrollment-options.md)
* [Enable bring your own device with Intune](byod-enable.md)
* [Educating your end users about enrollment and device management](end-user-educate.md)
