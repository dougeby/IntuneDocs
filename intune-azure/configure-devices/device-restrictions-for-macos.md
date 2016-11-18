---
# required metadata

title: Intune device restriction settings for macOS devices | Microsoft Docs
description: Description.
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3129cbaf-96c2-4837-8907-ca87a605a496

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# macOS device restriction settings

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## Password	
- 	**Password required** - Require the end user to enter a password to access the device.	
- 	**Required password type** - Specify whether the password can be Numeric only, or whether it must be Alphanumeric (contain letters and numbers). This setting is supported only on Mac OS X version 10.10.3 and later.	
- 	**Number of non-alphanumeric characters in password** - Specify the number of complex characters required in the password (**0** to **4**).<br>A complex character is a symbol, such as **?**.
- 	**Minimum password length** - Enter the minimum length of password a user must configure (between **4** and **16** characters).	
- 	**Simple passwords** - Allow the use of simple passwords such as **0000** or **1234**.	
- 	**Maximum minutes after screen lock before password is required** - Specify how long the computer must be inactive before a password is required to unlock it.	
- 	**Maximum minutes of inactivity until screen locks** - Specify the length of time that the computer must be idle before the screen locks.	
- 	**Password expiration (days)** - Specify how many days elapse before the user must change the password (**1** to **255** days).	
- 	**Prevent reuse of previous passwords** - Specify the number of previously used passwords that cannot be reused (**1** to **24**).	

## Restricted apps

In the restricted apps list, you can configure one of the following lists:

A **Prohibited apps** list - List the apps (not managed by Intune) that users are not allowed to install and run.
An **Approved apps** list - List the apps that users are allowed to install. To remain compliant, users must not install apps that are not listed. Apps that are managed by Intune are automatically allowed.

To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.

### How to specify the URL to an app in the store

To specify an app URL in the apps list, use the following format:

Using a search engine, find the app that you want to use in the iTunes App Store and open the page for the app.
Copy the URL of the page and use this as the URL to configure the allowed or prohibited apps list or an app that you want to run in kiosk mode.

> [!Note]
> You can also use iTunes to find the app and then use the **Copy Link** command to get the app URL.


