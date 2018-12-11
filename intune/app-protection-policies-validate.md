---
# required metadata

title: Validate your app protection policy setup
titleSuffix: Microsoft Intune
description: Learn how to test that your app protection policy is set up and working correctly.
keywords:
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/13/2018
ms.prod:
ms.service: microsoft-intune
ms.topic: article
ms.technology:
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to validate your app protection policy setup

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Validate that your app protection policy is correctly set up and working. This guidance applies to app protection policies in the Azure portal.

### Checking for symptoms
Users are unlikely to report issues since app protection is a data protection tool. If there's a problem with the app protection configuration the user has unrestricted access, as they would have without app protection, and don't know there's an issue. For this reason, we recommend you validate your app protection configuration by piloting your app protection policies with a small group of users who can deliberately test the app protection restrictions.


### What to check

If testing shows that your app protection policy behavior isn't as expected, check these items:

- Are the users licensed for app protection?
- Are the users licensed for O365?
- The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**.

#### User app protection status
1. Sign into the [Azure portal](https://portal.azure.com).
2. Select **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. Select **Client apps** > **Monitor** >  **App protection status**, and then select the **Assigned users** tile. 
4. On the **App reporting** page, select **Select user** to bring up a list of users and groups. 
5. Search for and select a user from the list, then choose **Select user**. At the top of the **App reporting** pane, you can see whether the user is licensed for app protection. You can also see whether the user has a license for O365 and the app status for all of the user's devices.



### What to do
Here are the actions to take based on the user status:

- If the user isn't licensed for app protection, assign an Intune license to the user.
- If the user isn't licensed for O365, get a license for the user.
- If a user's app is listed as **Not checked in**, check if you've correctly configured an app protection policy for that app.
- Ensure that these conditions apply across all users to which you want app protection policies to apply.

### See also

[What is Intune app protection policy?](app-protection-policies.md)
