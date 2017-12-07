---
# required metadata

title: Validate your app protection policies 
titleSuffix: "Azure portal"
description: This topics describes how you can test and validate if your app protection policy is set up correctly and working as expected."
keywords:
author: erikre
ms.author: erikre
manager: angerobe
ms.date: 01/23/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to validate your app protection policy setup

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


This topic provides information on checking for issues after you set up an app protection policy. This guidance applies to app protection policies in the Azure portal.

### Checking for symptoms
Users are unlikely to report issues since app protection is a data protection tool. If there is a problem with the app protection configuration the user will have unrestricted access, as they would have without app protection, and would not be aware that there is an issue. For this reason we recommend that you validate your app protection configuration by piloting your app protection policies with a small group of users who can deliberately test the app protection restrictions.


### What to check

If testing shows that your app protection policy behavior is not as anticipated, we recommend that you check the following:

- Are the users licensed for app protection?
- Are the users licensed for O365?
- The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**.

#### User app protection status
1. In the Azure portal choose **Manage apps** > **Monitor** >  **App protection user status** > **users**.

2. Choose a user from the list or search for and choose a user, then choose **Select user**. At the top of the **App reporting** column you will see whether the user is licensed for app protection. Below that you will see whether the user is licensed for O365 and the app status for all of the user's devices.



### What to do
Here are the actions to take based on the user status:

- If the user is not licensed for app protection, assign an Intune license to the user.
- If the user is not licensed for O365 obtain a license for the user.
- If a user's app is listed as **Not checked in**, check if you've correctly configured a app protection policy for that app.
- Ensure that these conditions are applied across all users to which you want app protection policies to apply.

### See also

[What is Intune app protection policy?](app-protection-policies.md)
