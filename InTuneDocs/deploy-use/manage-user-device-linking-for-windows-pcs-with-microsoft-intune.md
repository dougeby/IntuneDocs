---
# required metadata

title: Manage user-device linking for Windows PCs | Microsoft Intune
description: How to link a user to an Intune-managed Windows PC.
keywords:
author: staciebarkerms.author: stabar
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 53c99d63-c312-442a-8a71-de1b10fcd39b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: owenyen
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Manage user-device linking for Windows PCs
Before you can deploy software to a user, you must link the user to a computer. You can link a user to multiple computers, but each computer can be linked to only one user. Users are automatically linked to any computers that they enroll in Intune by using the company portal.

To link a user to a computer:

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the computer you want to link to a user).

2.  Select the computer that you want to link a user, and then choose **Link User**.

    The **Link User** dialog box displays a list of available users with their display name, user ID, and the number of computers to which each user is currently linked. If a user is already linked to the selected computer, that user’s name and user ID are displayed under **Current user**. If the computer is not linked to any user, **No User** appears under **Current User**.

3.  Do one of the following:

    -   To leave the computer linked to its current user, if there is one, choose **Cancel**.

    -   To remove the link to the current user, if there is one, choose **Remove link **&gt; **OK**.

    -   To link the computer to a new user, in the **All users** list, select a user. Confirm that the user data is correct, and then choose **OK**.

> [!TIP]
> If you want to restrict end users ability to link themselves to computers, enable the option **Restrict users' ability to link themselves to computers** in the **Microsoft Intune Agent Settings** policy.

### See also

[Common Windows PC management tasks with the Intune software client](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)