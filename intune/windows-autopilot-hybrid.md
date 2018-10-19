---
# required metadata

title: Set up Intune enrollment for hybrid Active Directory joined devices using Windows Autopilot
titleSuffix: Microsoft Intune
description: Use Windows Autopilot to enroll hybrid Active Directory joined devices in Intune.
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/11/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
 
# optional metadata
 
#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
 
---
 

# Deploy hybrid Azure AD joined devicces using Intune and Windows Autopilot
You can use Intune and Windows Autopilot to set up hybrid Azure Active Directory joined devices. To do so, follow the steps below.

## Prerequisites

1. Successfully configure [hybrid Azure Active Directory join for managed domains](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains).
    - Make sure to [verify the registration by using the Get-MsolDevice cmdlt]( https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#verify-the-registration).

The devices to be enrolled must also:
1. Be runninng Windows 10 with the [October 2018 update](https://blogs.windows.com/windowsexperience/2018/10/02/how-to-get-the-windows-10-october-2018-update/).
2. Have access to both the internet and your Active Directory.
3. Got through the Out-of-Box-Experience (OOBE).

## Increase the numberr of computer accounts that a user ccan  create in a domain

1. Open a command prompt on your domain coontroller and run **adsiedit**.
2. Expand the AD DS/LDS folder node > right-click thhe node that begins with **DC** > **Properties**.
3. Choose **ms-DS-MachiineAccountQuota** > **Edit**.
4. In the **Value** box, enter the number of hybrid Active Directory joined devices tthat yhou want to deploy using this feature. The maximum 2,147,483,647.
5. Choose **OK** > **OK** > close **ADSI Edit**.


## Enable Windows 10 automatic enrollment

1. Sign in to the [Azure portal](https://portal.azure.com), and select **Azure Active Directory**.

   ![Screenshot of the Azure portal](./media/auto-enroll-azure-main.png)

2. Select **Mobility (MDM and MAM)**.

   ![Screenshot of the Azure portal](./media/auto-enroll-mdm.png)

3. Select **Microsoft Intune**.

   ![Screenshot of the Azure portal](./media/auto-enroll-intune.png)

4. Configure **MDM User scope**. Specify which users’ devices should be managed by Microsoft Intune. These Windows 10 devices can automatically enroll for management with Microsoft Intune.
   - **Some** - Select the **Groups** with the users that you want to be set up by using Windows Autopilot on Hybrid Active Directory joined devices.
   - **All** - Use this option if you want all users to be set up using Windows Autopilot on Hybrid Active Directory joined devices.

   ![Screenshot of the Azure portal](./media/auto-enroll-scope.png)

5. Use the default values for the following URLs:
    - **MDM Terms of use URL**
    - **MDM Discovery URL**
    - **MDM Compliance URL**
6. Choose **Save**.

## Download and install the Intune Connector for Active Directory

The Intune Connector for Active Directory needs to be installed on a computer running Windows Server 2016 that has access to the Internet and your Active Directory.

1. In Intune in the Azure portal, choose **Device enrollment** > **Windows enrollment** > **Intune Connector for Active Directory** > **Add connector**. 
2. Follow the instructions to download  the connector.

## Create a dynamic device group
1. In [Intune in the Azure portal](https://aka.ms/intuneportal), choose **Groups** > **New group**.
2. In the **Group** blade:
    1. For **Group type**, choose **Security**.
    2. Type a **Group name** and **Group description**.
    3. For **Membership type**, choose **Dynamic Device**.
3. If you chose **Dynamic Devices** for **Membership type** above, then in the **Group** blade, choose **Dynamic device members** and type any of the following code in the **Advanced rule** box.
    - If you want to create a group that includes all of your Autopilot devices, type `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - If you want to create a group that includes all of your Autopilot devices with a specific order ID, type: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") `
    - If you want to create a group that includes all of your Autopilot devices with a specific Purchase Order ID, type: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    After adding the **Advanced rule** code, choose **Save**.
5. Choose **Create**.  

## Register the Autopilot devices

Choose one of the following ways to enroll your Autopilot  devices:

### Register Autopilot devices that are already enrolled

1. Create an Autopilot deployment profile with **Convert all targeted devices to Autopilot** set to **Yes**. 
2. Assign the profile to a group containing the members that you want to automatically register with Autopilot.

For more information, see [Create an Autopilot deployment profile](enrollment-autopilot.md#create-an-autopilot-deployment-profile).

### Register Autopilot devices that are not enrolled

If your devices are not yet enrolled, you can register them yourself. For more information, see [](enrollment-autopilot.md#create-an-autopilot-deployment-profile).

### Register devices from an OEM

If you're buying new devies, some OEMs can register the devices for you. For more information, see the [Windows Autopilot page](http://aka.ms/WindowsAutopilot).


## Create and assign an Autopilot deployment profile
Autopilot deployment profiles are used to configure the Autopilot devices.

1. In [Intune in the Azure portal](https://aka.ms/intuneportal), choose **Device enrollment** > **Windows enrollment** > **Deployment Profiles** > **Create Profile**.
2. Type a **Name** and optional **Description**.
3. For **Deployment mode**, choose **User-driven**.
4. In the **Join to Azure AD as** box, choose **Hybrid Azure AD joined**.
5. Choose **Out-of-box experience (OOBE)**, configure the options as needed, and then choose **Save**.
6. Choose **Create** to create the profile. 
7. In the profile blade, choose **Assignments**.
8. Choose **Select groups** > in the **Select groups** blade, choose the device group > **Select**.

It will take around 15 minutes for the dynamic device group’s profile status to change from **Not assigned** to **Assigning** and finally to **Assigned**.

## Turn on the enrollment status page

1.  In [Intune](https://aka.ms/intuneportal), choose **Device enrollment** > **Windows enrollment** > **Enrollment Status Page (Preview)**.
2.  In the **Enrollment Status Page** blade, choose **Default** > **Settings**.
3.  For **Show app and profile installation progress**, choose **Yes**.
4. For **Block device use until all apps and profiles are installed**, choose **Yes**.
5. Configure the other options as needed.
6.  Choose **Save**.

## Create and assign a Domain Join profile

1. In **Microsoft Intune**, select **Device configuration**, and select **Profiles**. Then select **Create Profile**.
2. Enter the following properties:
   - **Name**: Enter a descriptive name for the new profile.
   - **Description**: Enter a description for the profile.
   - **Platform**: Choose **Windows 10 and later**.
   - **Profile type**: Choose **Domain Join**.
3.  Choose **Settings** and provide a **Computer name prefix**, **Domain name**, and **Organizational unit** (optional). 
4. Choose **OK** > **Create**. The profile is created, and appears in the list.

