---
# required metadata

title: Remove your Windows device from Intune | Microsoft Docs
description: Describes how to remove a Windows device from Intune
keywords:
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 03/28/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 018bda65-7238-41f5-b92a-e5f67b7fe085
searchScope: - User help

# optional metadata

ROBOTS:   
#audience:
#ms.devlang:
ms.reviewer: jieyang
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-enduser

---


# Remove your Windows device from Intune

If your device is registered with Intune, but you no longer want to use your Windows device to access work or school email, apps, or other resources, you need to remove your device from management. Once you remove your device from Intune, you will no longer be able to access these resources. For more about what happens when you remove your device from management, see [What happens if you unenroll your device from Intune?](what-happens-if-you-unenroll-your-device-from-intune-windows.md).

## Remove your Windows 10 device

1.  From your apps list, tap the **Company Portal** app.

2.  Sign in using your work or school credentials.

3.  In **My Devices**, select the device you want to unenroll.

4.  Tap **Remove** &gt; **Remove**.

## Remove your Windows 8.1 computer

1.  Go to **PC Settings** &gt; **Network** &gt; **Workplace**.

2.  Under **Workplace Join**, select **Leave**.

3.  Under **Turn on device management,** select **Turn off**.

4.  On the popup window that opens, select **Turn off**.

## Remove your Windows Phone 8.1 mobile device

1.  Go to **Settings** &gt; **Workplace**.

2.  Tap the workplace account that you want to unenroll.

3.  Tap **Delete** at the bottom of the screen.

4.  On the **Delete account** dialog box, tap **Delete**.

## Removing your personal information after removing the Company Portal

There are two kinds of data that the Company Portal stores on your Windows device:

-	**Diagnostic logs**: standard app activity data that Microsoft collects, like how long the app was open or if it's crashed, is automatically erased when you remove the device from the Company Portal.
-	**Application cache**: storing of certain support files required for the app to work, like icons and settings.

There are a few steps you need to take to completely delete this information.

### Uninstall the Company Portal  

[Uninstalling the Company Portal app](https://support.microsoft.com/help/4028003/windows-10-uninstall-apps-and-programs) will remove some of the app data stored on your device.  

### Reset the Company Portal

You can reset the rest of the Company Portal's app data by resetting the app in Settings. Open **Settings** > **Apps & Features** > **Company Portal** > **Advanced options** > **Reset**.


Still need help? Contact your company support. For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).
