---
# required metadata

title: Get started with users
titleSuffix: "Intune on Azure"
description:
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/11/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Get started with managing users

Users are one of the core pieces of accessing Intune. Think about all the different people in your organization. Every one of them that uses company data will need a user to manage access to it in Intune.

## How do I create a user?

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Using **Search resources**, search for **Intune**.
3. Once you've opened the **Microsoft Intune** blade, select **Users**. On the **All Users** page, select **+ New user**.
4. Enter details for the user, such as **Name** and **User name**. The domain name portion of the user name must either be the initial default domain name “contoso.onmicrosoft.com” domain name, or a verified, non-federated domain name such as “contoso.com.”
5. Under **Groups**, choose the test group to add the user to.
6. Save the automatically generated user password so that you can use it to log in to a test device. You must give this password to users so that they can change it to a normal password that they can remember.
7. On the **User** blade, select **Create**.

## Assigning licenses to users

After you've created a user, you need to use the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) to assign an Intune license to that user. Without assigning them a license, they can't enroll their device into management.

1. Sign in to the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) with the same credentials you used to sign in to Intune.
2. Select **Users** > **Active Users**, then select the user you previously created.
3. You may need to wait a moment for all of the user's information to load. Once it loads, select **Edit** for the user's **Product licenses**.
4. Assign the user a **Location**, then switch Intune to **on**.

 > [!NOTE]
 > This uses one of your licenses for this user. If you are using your live environment, you can turn off using this license later to reassign it to a real user.

5. Select **Save**.

## Next steps

After you've finished creating your user, you'll need to [create a group](get-started-groups.md) to easily assign apps and settings to large numbers of users and devices.
