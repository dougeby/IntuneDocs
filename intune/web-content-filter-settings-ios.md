---
# required metadata

title: Intune web content filter settings for iOS devices
titlesuffix: "Azure portal"
description: Learn the settings you can use to allow and block access to websites from iOS devices."
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

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

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use these settings to configure URLs that end users of web browsers, on iOS devices, can, or cannot visit. There are two methods you can use to do configure URLs:

- **Configure URLs** - Use Apple’s built-in web filter that looks for adult terms like profanity or sexually explicit language. This function evaluates each web page as it is loaded and attempts to identify and block unsuitable content. You can also configure URLs that are not checked by the filter, or URLs that are blocked, regardless of the filter settings.

- **Specific websites only** (for the Safari web browser only) - These URLs are added to the Safari browser’s bookmarks. The user is **only** allowed to visit these sites; no other sites can be accessed. Use this option only if you know the exact list of URLs that users can access.
If you do not specify any URLs, then end users cannot access any websites except for microsoft.com, microsoft.net, and apple.com.



## Get started

1. From [Intune in the Azure Portal](https://portal.azure.com), navigate to [**Device features** in the device configuration area](device-features-configure.md). 
1. On the **Device features** pane, choose **Web Content Filter (supervised only)**.
2. On the **Web Content Filter** pane, choose the **Filter type** you want to configure from:
	- **Not Configured** - No filtering is performed.
	- **Configure URLs**
	- **Specific websites only**
3. Next, depending on the filter type you are using, use one of the following procedures:


## Configure URLs

1. On the **Web Content Filter** pane, choose one of the following settings as required:
   - **Permitted URLs** - On the **Permitted URLs** pane, enter the URLs you want to allow (bypassing the Apple web filter), and choose enter after each.
     > [!NOTE]
     > The URLs you specify here are the ones you do not want to subject to the Apple web filter. These URLs do not represent a list of the only web sites allowed. If that is what you want, use **Specific websites only**.

   - **Blocked URLs** - On the **Blocked URLs** pane, enter the URLs you want to block (regardless of the Apple web filter settings), and choose enter after each.
2. When you are finished, click **OK**.


## Specific websites only

1. On the **Web Content Filter** pane, for each web site you want to permit, configure the following settings:
	- **URL** - Enter the URL of the website you want to permit, for example, **http://www.contoso.com**.
	- **Bookmark Path** - Enter the path to where you want to store the bookmark, for example **/Contoso/Business Apps**. If you don't add a path, the bookmark is added to the default bookmark folder on the device.
	- **Title** - Enter a descriptive title for the bookmark.
2. Click **Add** after you enter the information for each website.
3. When you are finished, click **OK**.

>[!IMPORTANT] 
> The following URLs are permitted automatically by Intune.
> - www.microsoft.com
> - www.microsoft.net
> - www.apple.com

## Finish up

Choose **OK** to return to the **Create Profile** pane, and then choose **Create**.

## Next steps

You can now assign the device profile to the groups you choose. For details, see [How to assign device profiles](device-profile-assign.md).
