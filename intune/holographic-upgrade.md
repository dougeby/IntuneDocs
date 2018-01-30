---
# required metadata
title: Upgrade Windows Holographic to Windows Holographic for Business
titleSuffix: "Azure portal"
description: Learn how to ugrade devices running Windows Holographic to Window Holographic for Business
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 1/30/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Upgrade devices running Windows Holographic to Windows Holographic for Business


To manage devices that run Windows Holographic with Microsoft Intune, you must create an Edition Upgrade profile to upgrade the devices from Windows Holographic to Windows Holographic for Business. For the Microsoft Hololens, you can purchase the Commercial Suite to obtain the required license for the upgrade. For more information, see [Unlock Windows Holographic for Business features](https://docs.microsoft.com/en-us/hololens/hololens-upgrade-enterprise).

## To set up an Edition Upgrade device configuration profile

1. Sign in to the [Azure portal](https://portal.azure.com) with your administrator account.


2.	Click **Device configuration**, **Profiles**, and then click **+ Create profile**.

    ![Create profile](media/Holographic-create-profile.png)

3.	In the **Create profile** blade, type a name for the profile, select **Windows 10 and later** for the platform, and select **Edition upgrade** for the profile type. Click **Settings Configure**.

5. In the **Edition Upgrade** blade, on **Edition to upgrade to**, select **Windows 10 Holographic for Business**. On **License File**, browse to and select the XML license file that was provided to you.

    ![Enter the XML file name](media/Holographic-edition-upgrade.png)
 
5.	Click **OK**, and then click **Create** to create the profile.


### Deploy the Edition Upgrade policy

Next, you assign the Edition Upgrade profile to selected groups or devices.

1. On the profile that you created in the previous steps, click **Assignments**.

2. In the **Assignments** blade, select the user groups and devices you want to include and exclude with the policy.

![Include and exclude groups](media/Holographic-groups.PNG)

When these users or devices are enrolled in Intune, the Edition Upgrade profile is applied. 


For more information about groups, see [Get started with groups](get-started-groups.md).


