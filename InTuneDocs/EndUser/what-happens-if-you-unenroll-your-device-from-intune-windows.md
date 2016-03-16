---
title: What happens if you unenroll your device from Intune?
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 
author: Staciebarker

# What happens if you unenroll your device from Intune?

When you uninstall the Company Portal app from your device, it also unenrolls your device from Intune. For additional information about what happens, use the link that matches the type of device you're using.

- [Windows 10, 8.1, Windows 8, Windows 7, Vista](BKMK_what_happens_unenroll_win81_8_7_vista)
- [Windows 8.1 or Windows Phone 8](BKMK_what_happens_unenroll_wp81)
- [Windows RT running Windows 8.1 or Windows RT](BKMK_what_happens_unenroll_win81_rt)


## <a name="BKMK_what_happens_unenroll_win81_8_7_vista">Windows 8.1, Windows 8, Windows 7, Vista

-   Your device won’t appear in the company portal anymore, and you can’t install apps from the company portal anymore.

-   If you installed the [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] client software, it’s removed from your computer.

-   The [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] Endpoint Protection software is removed from your computer. If your computer has other virus protection software installed and it is disabled, that software may be re-enabled after [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] Endpoint Protection is removed. You should check your computer after removing it from the company portal.

    > [!IMPORTANT]
    > If the other virus protection software is not re-enabled or no other virus protection software is installed, your computer may be vulnerable to viruses and malware.

-   Any settings that were changed on your device when you added it (for example, disabling the camera, will no longer apply).

-   Your computer will no longer receive automatic software updates or antivirus software updates from the [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] service. However, depending on how it is configured, your computer may still receive updates from the Windows Server Update Services, Windows Update, or Microsoft Update.

In addition, for Windows 8.1:

-   You can’t use company apps and company data on your device anymore.

-   Some mail apps, such as Windows Mail, won’t be able to access company email that is stored on your device anymore.

-   You might not be able to connect to your company network using Wi-Fi or a Virtual Private Network.

-   You might not have access to some company resources, such as file shares or internal web sites, on your device anymore.

## <a name="BKMK_what_happens_unenroll_wp81">Windows Phone 8.1 or Windows Phone 8

-   The Company Portal app is uninstalled from your device, which means that your device won’t appear in the company portal anymore, and you won't be able to install apps from the Company Portal app or Company Portal website.

-   You can’t use company apps and company data on your device anymore.

-   Any settings that were changed on your device when you added it, for example disabling the camera, or requiring a certain password length, will no longer apply.

    > [!IMPORTANT]
    > The only exception to this is encryption policies, which will still apply. If your company policy required that your Windows Phone be encrypted, the only way to unencrypt your phone is to reset your phone using the **Settings** menu on your Windows Phone.

## <a name="BKMK_what_happens_unenroll_win81_rt">Windows RT running Windows 8.1 or Windows RT

-   The Company Portal app is uninstalled from your device, which means that your device won’t appear in the company portal anymore, and you won't be able to install apps from the Company Portal.

-   You can’t use company apps and company data on your device anymore.

-   Any settings that were changed on your device when you added it, for example disabling the camera, or requiring a certain password length, will no longer apply.

-   You might not be able to connect to your company network using Wi-Fi or a Virtual Private Network anymore.

-   You might not have access to some company resources, such as file shares or internal web sites, on your device anymore.

-   Some mail apps, such as Windows Mail, won’t be able to access company email that is stored on your device anymore.

When you remove your Windows RT device, the following happens:

-   The Company Portal app is uninstalled from your device, which means that your device won’t appear in the company portal anymore, and you won't be able to install apps from the Company Portal.

-   You can’t use company apps and company data on your device anymore.

-   Any settings that were changed on your device when you added it, for example disabling the camera, or requiring a certain password length, will no longer apply.


### See also
[Using your Windows device with Intune](using-your-windows-device-with-intune.md)