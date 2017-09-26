---
# required metadata

title: Manually sync your Windows device | Microsoft Docs
description:
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/19/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 443c6de7-5187-4dc4-b844-6085a0c659bdsearchScope: - User help

# optional metadata

ROBOTS:  
#audience:
#ms.devlang:
ms.reviewer: priyar
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-enduser

---

# Sync your Windows device manually

Sometimes trying to install an app on your Windows device may take longer than you think it should. If this happens, you can try to manually sync your Windows device. Syncing may help speed up the installation.

> [!Note]
> Apps could take awhile to install if you are on a network with slower speeds or higher amounts of devices downloading content at the same time.

The following versions of Windows can sync manually. Unfortunately, if your device is using a different version of Windows, you can't start a manual sync.

* [Sync Windows 10 desktop](#windows-10-desktop)
* [Sync Windows 10 Mobile](#windows-10-mobile)
* [Sync Windows Phone 8.1](#windows-phone-81)

## Windows 10 desktop
There is more than one version of Windows 10, so there are two sets of steps. To figure out which steps to use, look at the screenshots, and then follow the steps that look like what you see on your device.

1. Choose the **Start** button, and then choose **Settings**.

    ![The Start button](./media/win10pc-sync-1-start-button.png)

2. On the **Settings** page, choose **Accounts**.

    ![Choosing Accounts on the Settings page](./media/win10pc-sync-2-settings-accounts.png)

3. Look at the next two screens, and find the one that looks like the one you see on your device. Follow the steps that go with the screen that you see on your device.

	If you see this screen, which shows "Access work or school," follow the instructions in [Steps to follow if you see Access work or school](#steps-to-follow-if-you-see-access-work-or-school).

	![Sync steps to follow if you see Access work or school](./media/w10-enroll-rs1-connect-to-work-or-school.png)

	If you see this screen, which shows "Work access," follow the steps in [Steps to follow if you see Work access](#steps-to-follow-if-you-see-work-access).

	![Choosing work access as the account type](./media/win10pc-sync-3-work-access.png)

### Steps to follow if you see Access work or school

1. On the **Accounts** page, choose **Access work or school**.

    ![Choose Access work or school](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2. Choose your work or school account. Depending on how your company support has set things up, you might see two accounts that look similar to the example shown below. One account has a briefcase next to it, and the other has the Microsoft logo next to it.

	- If you see the account with the briefcase, select it, and look for an **Info** button under it.
	- If you see only the account with the Microsoft logo, select the account, and look for an **Info** button under it.

    ![Choose your account name next to the briefcase or Microsoft logo](./media/win10pc-rs1-sync-info-button.png)

3. Choose the **Info** button. A dialog opens that looks similar to the example below.

    ![Choose your account name next to the briefcase or Microsoft logo](./media/win10pc-rs1-sync-button.png)

4. Choose the **Sync** button. Your device will be synced with Intune.

### Steps to follow if you see Work access

1. On the **Accounts** page, choose **Work access**.

    ![Choosing work access as the account type](./media/win10pc-sync-3-work-access.png)

2. Under the section **Enroll in to device management**, choose the name of your company.

    ![Choosing the company name for device management](./media/win10pc-sync-4-tap-com-name.png)

3. Choose the **Sync** button.

    ![Choosing the Sync button](./media/win10pc-sync-5-tap-sync.png)

   The button becomes grayed out until the sync is finished.

### Windows 10 Mobile
To manually sync your Windows 10 Mobile device to speed up a slow app installation:

   1. Go to **All apps** > **Settings** > **Accounts**.

       ![Choosing Accounts on the Settings screen](./media/win10m-sync-1-settings-accounts.png)

   2. Choose **Work access**.

       ![Choosing work access as the account type](./media/win10m-sync-2-work-access.png)

   3. Under **Enroll in to device management**, choose your company name.

       ![Choosing the company name for device management](./media/win10m-sync-3-tap-comp-name.png)

   4. Choose the **Sync** icon.

       ![Choosing the Sync icon](./media/win10m-sync-4-tap-sync.png)

       The message “We’re synching your account” appears at the top of the screen. The **Sync** button is grayed out until your device finishes syncing.

## Windows Phone 8.1
To manually sync your Windows Phone 8.1 device to speed up a slow app installation:

1. Go to **All apps** > **Settings** > **workplace**.

    ![List of settings](./media/wp81-1-sync-settings-workplace.png)

2. Choose the name of your company.

    ![Choosing the company name for the workplace account](./media/wp81-2-sync-tap-compname.png)

3. Choose the **Sync** icon.

    ![Choosing the Sync icon](./media/wp81-3-sync-tap-sync-button.png)

   The message “We’re synching your account” appears at the top of the screen until your device finishes syncing.

Still need help? Contact your company support. For contact information, check the [Company Portal website](http://portal.manage.microsoft.com).
