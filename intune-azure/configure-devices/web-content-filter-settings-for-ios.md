---
# required metadata

title: Intune web content filter settings for iOS devices
titleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn the settings you can use to allow and block access to websites from iOS devices."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 16aa0f3c-8977-4495-9fbe-ca30ad278c9e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: karanda
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Web content filter settings for iOS devices

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use these settings to configure URLs that end users of the Safari browser, on iOS devices, can, or cannot visit. There are two methods you can use to do this.

1. **Configure URLs** - Use Apple’s built in web filter that looks for adult terms like profanity or sexually explicit language. This function evaluates each web page as it is loaded and attempts to identify and block unsuitable content. Additionally, you can configure URLs that will not be checked by the filter, or URLs that will always be blocked, regardless of the filter settings.

2. **Specific websites only** - These URLs are added to the Safari browser’s bookmarks. The user is **only** allowed to visit these sites; no other sites can be accessed. Use this option only if you know the exact list of URLs that can be accessed by users.



## Get started

1. On the **Device features** blade choose **Web Content Filter (supervised only)**.
2. On the **Web Content Filter** blade, choose the **Filter type** you want to configure from:
	- **Not Configured** - No filtering is performed.
	- **Configure URLs**
	- **Specific websites only**
3. Next, depending on the filter type you are using, follow the relevant procedure below.


## Configure URLs

1. On the **Web Content Filter** blade, choose one of the following if required:
	- **Permitted URLs** - On the **Permitted URLs** blade, enter the URLs you want to allow (bypassing the Apple web filter), and choose enter after each.
	- **Blocked URLs** - On the **Blocked URLs** blade, enter the URLs you want to block (regardless of the Apple web filter settings), and choose enter after each.
2. When you are finished, click **OK**.


## Configure specific websites only

1. On the **Web Content Filter** blade, for each web site you want to permit, enter the following:
	- **URL** - Enter the URL of the website you want to permit, for example, **http://www.contoso.com**.
	- **Bookmark Path** - Enter the path to where you want to store the bookmark, for example **/Contoso/Business Apps**.
	- **Title** - Enter a descriptive title for the bookmark.
2. Click **Add** after you enter the information for each website.
3. When you are finished, click **OK**.

>[!IMPORTANT] 
> The following URLs are permitted automatically by Intune.
> - www.microsoft.com
> - www.microsoft.net

## Finish up

Choose **OK** to return to the **Create Profile** blade, and then choose **Create**.
