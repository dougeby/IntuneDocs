---
title: Quickstart - Create a user in Intune
description: Quickstart - Create a user in Intune.
services: microsoft-intune
author: ErikjeMS

ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 09/15/2018
ms.author: erikje
---

# Quickstart: Create a user and assign a license to it

In this quickstart, you'll create a user and then assign a license to it. When using Intune, each person that you want to have access to company data must have a user account. Intune admins will be able to configure such users to manage access control.

If you don’t have an Intune subscription, [sign up for a free trial account](free-trial-sign-up.md).

## Prerequisites

- [Create a group](get-started-groups.md) that you'll assign the user to.

## Sign in to Intune

Sign in to the [Intune](https://aka.ms/intuneportal) as a Global Administrator or an Intune Service Administrator.

## Create a user

People must have a user account to enroll in Intune device management.

1. In Intune, choose **Users** > **All users** > **New user**.
![Browser](media/quickstart-create-user/create-user.png)
2. In the **Name** box, enter *John Doe*.
3. In the **User name** box, enter *john@contoso.onmicrosoft.com*.
4. Choose **Groups** > **Everyone** > **Select**.
5. Choose **Show password** and make a note of the automatically generated password so that you can sign in to a test device.
6. Choose **Create**.

## Assign a license to the user

After you've created a user, you must use the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) to assign an Intune license to that user. Without assigning a license, they can't enroll their device into Intune. 

1. Sign in to the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) with the same credentials you used to sign in to Intune.
2. Choose **Users** > **Active Users** > choose the user you just created.
3. Under **Location**, choose a location for the user.
3. Choose **Product licenses** and set **Enterprise Mobility + Security E3** (or another license you have that includes Intune) to **On**
   > [!NOTE]
   > This uses one of your licenses for this user. If you are using your live environment, you can turn off using this license later to reassign it to a real user.
5. Choose **Save**.


## Clean up resources

To delete the user, choose **Users** > **All users** > choose the user in the list > **Delete user** > **Yes**.

## Next steps

The user can now enroll in Intune as described in [Enroll your Windows device in Intune](device-compliance-get-started.md).