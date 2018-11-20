---
# required metadata

title: Connect your Intune account to your Android enterprise account
titlesuffix: "Microsoft Intune"
description: Learn how to connect your Intune account to your Android enterprise account.
keywords:
author: ErikjeMS 
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Connect your Intune account to your Android enterprise account

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

To support Android work profile devices and Android kiosk devices, you must connect your Intune tenant account to your Android enterprise account. 

> [!NOTE]
> Due to interaction between Google and Microsoft domains, this step may require that you adjust your browser settings.  Make sure that "portal.azure.com" and "play.google.com" are in the same security zone in your browser.

1. If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](mdm-authority-set.md) as **Microsoft Intune**.
2. Sign in to the [Intune in the Azure portal](https://aka.ms/intuneportal), choose **Device enrollment** > **Android enrollment** > **Managed Google Play**.  If you are using a custom Intune admin role, access to this requires Organization Read and Update permissions.
   
   ![Android enterprise enrollment screen](./media/android-work-bind.png)

3. Choose **I agree** to grant Microsoft permission to [send user and device information to Google](data-intune-sends-to-google.md). 
   
4. Choose **Launch Google to connect now** to open the Managed Google Play website. The website opens on a new tab in your browser.
  
5. On Google's sign in page, enter the Google account that will be associated with all Android enterprise management tasks for this tenant. This is the Google account that your company's IT admins share to manage and publish apps in the Google Play console. You can use an existing Google account or create a new one. The account you choose must not be associated with a G-Suite domain.
    
    > [!Note]
    > If you are using the Microsoft Edge browser, click **Sign-In** in the upper right corner to sign-in to your Google account.

6. Provide your company's name for **Organization name**. For **Enterprise mobility management (EMM) provider**, **Microsoft Intune** should be displayed.

7. Agree to the Android agreement, and then choose **Confirm**. Your request will be processed.

## Disconnect your Android enterprise administrative account

You can turn off Android enterprise enrollment and management. To do this, you must first retire any enrolled Android work profile devices. Then, choose **Disconnect** in the Intune administration console to remove all enrolled Android work profile devices and kiosk devices from enrollment. This also removes the relationship between the Android enterprise account and Intune.

1. As an Intune administrator, in the [Azure portal](https://portal.azure.com), choose **All Services** > **Monitoring + Management** > **Intune**.
2. Choose **Device enrollment** > **Android enrollment** > **Managed Google Play** > **Disconnect**.
3. Choose **Yes** to disconnect and unenroll all Android enterprise devices from Intune.

## Next steps

After connecting to the Android enterprise account, you can [set up Android work profile devices](android-work-profile-enroll.md) and
[set up Android kiosk devices](android-kiosk-enroll.md).
