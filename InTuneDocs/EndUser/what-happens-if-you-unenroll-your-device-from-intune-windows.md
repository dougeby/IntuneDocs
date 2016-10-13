---
# required metadata

title: What happens if you unenroll your Windows device from Intune? | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c

# optional metadata

ROBOTS: NOINDEX,NOFOLLOW
#audience:
#ms.devlang:
ms.reviewer: priyar
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# What happens if you unenroll your Windows device from Intune?

Use the links at the right side of this page, under "In this article," to find information about the type of device you're using.


## Windows 10, Windows 8.1, Windows 8, Windows 7, Vista

-   Your device won’t appear in the Company Portal anymore, and you can’t install apps from the Company Portal anymore.

-   If you installed the Intune client software, it’s removed from your computer.

-   The Intune Endpoint Protection software is removed from your computer. If your computer has other virus protection software installed and it is disabled, that software may be re-enabled after Intune Endpoint Protection is removed. You should check your computer after removing it from the Company Portal.

    > [!IMPORTANT]
    > If the other virus protection software is not re-enabled or no other virus protection software is installed, your computer may be vulnerable to viruses and malware.

-   Any settings that were changed on your device when you added it (for example, disabling the camera, will no longer apply).

-   Your computer will no longer receive automatic software updates or antivirus software updates from the Intune service. However, depending on how it is configured, your computer may still receive updates from the Windows Server Update Services, Windows Update, or Microsoft Update.

In addition, for Windows 8.1:

-   You can’t use company apps and company data on your device anymore.

-   Some mail apps, such as Windows Mail, won’t be able to access company email that is stored on your device anymore.

-   You might not be able to connect to your company network using Wi-Fi or a Virtual Private Network.

-   You might not have access to some company resources, such as file shares or internal web sites, on your device anymore.

## Windows 10 mobile and Windows Phone 8.1

-   The Company Portal app is uninstalled from your device, which means that your device won’t appear in the Company Portal anymore, and you won't be able to install apps from the Company Portal app or Company Portal website.

-   You can’t use company apps and company data on your device anymore.

-   Any settings that were changed on your device when you added it, for example disabling the camera, or requiring a certain password length, will no longer apply.

    > [!IMPORTANT]
    > The only exception to this is encryption policies, which will still apply. If your company policy required that your Windows Phone be encrypted, the only way to unencrypt your phone is to reset your phone using the **Settings** menu on your Windows Phone.

## Windows RT running Windows 8.1

-   The Company Portal app is uninstalled from your device, which means that your device won’t appear in the Company Portal anymore, and you won't be able to install apps from the Company Portal.

-   You can’t use company apps and company data on your device anymore.

-   Any settings that were changed on your device when you added it, for example disabling the camera, or requiring a certain password length, will no longer apply.

-   You might not be able to connect to your company network using Wi-Fi or a Virtual Private Network anymore.

-   You might not have access to some company resources, such as file shares or internal web sites, on your device anymore.

-   Some mail apps, such as Windows Mail, won’t be able to access company email that is stored on your device anymore.

When you remove your Windows RT device, the following happens:

-   The Company Portal app is uninstalled from your device, which means that your device won’t appear in the Company Portal anymore, and you won't be able to install apps from the Company Portal.

-   You can’t use company apps and company data on your device anymore.

-   Any settings that were changed on your device when you added it, for example disabling the camera, or requiring a certain password length, will no longer apply.

If you have questions, contact your IT administrator. For their contact information, check the [Company Portal website](http://portal.manage.microsoft.com).

