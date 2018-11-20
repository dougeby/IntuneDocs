---
# required metadata

title: Upgrade or use S mode on Windows 10 devices with Microsoft Intune - Azure | Microsoft Docs
description: Create a device profile in Microsoft Intune to upgrade Windows 10 devices to different editions. For example, you can upgrade from Windows 10 Professional to Windows 10 Enterprise. You can also enable or switch out of S mode on a device using the configuration profile. Also see the supported upgrade paths for Windows 10 Pro, N Edition, Education, Cloud, Enterprise, Core, Holographic, and Mobile. 
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/11/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Use a configuration profile to upgrade Windows 10, or switch from S mode in Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Configure an upgrade profile in Intune to automatically upgrade devices that run Windows 10 edition to a different edition. Also see the supported upgrade paths.

## Before you begin
Before you upgrade devices to the latest version, you need the following prerequisites:

- A valid product key to install the updated Windows version on all devices that you target with the policy (for Windows 10 Desktop editions). You can use either Multiple Activation Keys (MAK) or Key Management Server (KMS) keys. For Windows 10 Mobile and Windows 10 Holographic editions, you can use a Microsoft license file that includes the licensing information to install the updated Windows version on all devices that you target with the policy.
- The Windows 10 devices you assign the policy are enrolled in Microsoft Intune. You can't use the edition upgrade policy with PCs that run the Intune PC client software.

## Supported upgrade paths
The following table lists the supported upgrade paths for the Windows 10 edition upgrade profile.

| Upgrade from | Upgrade to |
|---|---|
| Windows 10 Pro | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro Education |
| Windows 10 Pro N edition | Windows 10 Education N edition <br/>Windows 10 Enterprise N edition <br/>Windows 10 Pro Education N edition | 
| Windows 10 Pro Education | Windows 10 Education | 
| Windows 10 Pro Education N edition | Windows 10 Education N edition |
| Windows 10 Cloud | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro <br/>Windows 10 Pro Education | 
| Windows 10 Cloud N edition | Windows 10 Education N edition <br/>Windows 10 Enterprise N edition <br/>Windows 10 Pro N edition <br/>Windows 10 Pro Education N edition | 
| Windows 10 Enterprise | Windows 10 Education | 
| Windows 10 Enterprise N edition | Windows 10 Education N edition | 
| Windows 10 Core | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro Education | 
| Windows 10 Core N edition | Windows 10 Education N edition <br/>Windows 10 Enterprise N edition <br/>Windows 10 Pro Education N edition | 
| Windows 10 Holographic | Windows 10 Holographic for Business |
| Windows 10 Mobile | Windows 10 Mobile Enterprise |


<!-- Testing a new table on 3/5/18 

The following lists provide the supported upgrade paths for the Windows 10 edition upgrade profile. The Windows 10 edition to upgrade to is in bold followed by the list of supported editions that you can upgrade from:

**Windows 10 Education**
- Windows 10 Pro
- Windows 10 Pro Education
- Windows 10 Cloud
- Windows 10 Enterprise
- Windows 10 Core
    
**Windows 10 Education N edition**    
- Windows 10 Pro N edition
- Windows 10 Pro Education N edition
- Windows 10 Cloud N edition
- Windows 10 Enterprise N edition
- Windows 10 Core N edition
    
**Windows 10 Enterprise**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Enterprise N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition
    
**Windows 10 Pro**
- Windows 10 Cloud
    
**Windows 10 Pro N edition**
- Windows 10 Cloud N edition
    
**Windows 10 Pro Education**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Pro Education N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition

**Windows 10 Holographic for Business**
- Windows 10 Holographic

**Windows 10 Mobile Enterprise**
- Windows 10 Mobile -->

<!--The following table provides information about the supported upgrade paths for Windows 10 editions in this policy:

![supported](./media/check_grn.png)  (X) = not supported    
![unsupported](./media/x_blk.png)    (green checkmark) = supported    

|Upgrade from edition\Upgrade to edition|Education|Education N|Pro Education|Pro Education N|Enterprise|Enterprise N|Professional|Professional N|Mobile Enterprise|Holographic for Business|
|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|
|Pro|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png) 	|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Mobile|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|
|Holographic|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png) -->

## Upgrade the edition

1. In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.
2. Select **Device configuration** > **Profiles** > **Create Profile**.
3. Enter a **Name** and **Description** for the profile. For example, enter something like `Windows 10 edition upgrade`
4. For **Platform**, select **Windows 10 and later**.
5. For **Profile type**, select **Edition upgrade**.
6. In the **Edition Upgrade** properties, enter the following settings:

   - **Edition to upgrade to**: Select the Windows 10 edition that you're upgrading to. The devices targeted by this policy are upgraded to the edition you choose.
   - **Product Key**: Enter the product key that you received from Microsoft. After you create the policy with the product key, the key can't be updated, and is hidden for security reasons. To change the product key, enter the entire key again.
   - **License File**: For **Windows 10 Holographic for Business** or **Windows 10 Mobile edition**, choose **Browse** to select the license file you received from Microsoft. This license file includes license information the editions you're upgrading the targeted devices to.

7. Select **OK** to save your changes. Select **Create** to create the profile.

## Switch out of S mode

[Windows 10 S mode](https://support.microsoft.com/help/4456067/windows-10-switch-out-of-s-mode) is designed for security and performance. If your devices only run apps from the Microsoft Store, then you can use S mode to help keep your devices secure. If your devices require apps that aren't available in the Microsoft Store, then you switch out of S mode. Switching out of S mode is one way. And once you switch out of S mode, you can't go back to Windows 10 S mode.

The following steps show how to create a profile that controls S mode on Windows 10 (1809 or later) devices.

1. In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.
2. Select **Device configuration** > **Profiles** > **Create Profile**.
3. Enter a **Name** and **Description** for the profile. For example, enter something like `Windows 10 switch off S mode`
4. For **Platform**, select **Windows 10 and later**.
5. For **Profile type**, select **Edition upgrade**.
6. Select **Mode switch (Windows Insider only)**, and set the **Switch out of S mode** property. Your options:

    - **No configuration**: An S mode device remains in S mode. An end user can switch the device out of S mode.
    - **Keep in S mode**: Disables the end user from switching the device out of S mode.
    - **Switch**: Switches the device out of S mode.

7. Select **OK** to save your changes. Select **Create** to create the profile.

The profile is created and is listed in the profiles.

## Next steps

[Assign this profle](device-profile-assign.md) to your groups.

>[!NOTE]
>If you remove the policy assignment later, the version of Windows on the device is not reverted, and continues to function normally.
