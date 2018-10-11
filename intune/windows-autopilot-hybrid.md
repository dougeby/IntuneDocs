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
 

## Set up Intune enrollment for hybrid Active Directory joined devices using Windows Autopilot
You can use Windows Autopilot to set up Intune enrollment for hybrid Azure Active Directory joined devices.
## Set up hybrid Azure Active Directory devices
1.	Follow the steps in the [Tutorial: Configure hybrid Azure Active Directory join for managed domans](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains).
2.	Make sure to [verify the registration by using the Get-MsolDevice cmdlt]( https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#verify-the-registration).
## Enable Windows 10 automatic enrollment
Automatic enrollment lets users enroll their Windows 10 devices in Intune. To enroll, users add their work account to their personally owned devices or join corporate-owned devices to Azure Active Directory. In the background, the device registers and joins Azure Active Directory. Once registered, the device is managed with Intune.
**Prerequisites**
- Azure Active Directory Premium subscription ([trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune subscription
### Configure automatic MDM enrollment
1. Sign in to the [Azure portal](https://portal.azure.com), and select **Azure Active Directory**.
   ![Screenshot of the Azure portal](./media/auto-enroll-azure-main.png)
2. Select **Mobility (MDM and MAM)**.
   ![Screenshot of the Azure portal](./media/auto-enroll-mdm.png)
3. Select **Microsoft Intune**.
   ![Screenshot of the Azure portal](./media/auto-enroll-intune.png)
4. Configure **MDM User scope**. Specify which users’ devices should be managed by Microsoft Intune. These Windows 10 devices can automatically enroll for management with Microsoft Intune.
   - **Some** - Select the **Groups** with the users that you want to be set up by using Windows Autopilot on Hybrid Active Directory joined devices.
   - **All** - Use this option if you want all users to be set up using Windows Autopilot on Hybrid Active Directory joined devices.
      > [!IMPORTANT]
      > If both **MAM user scope** and automatic MDM enrollment (**MDM user scope**) are enabled for a group, only MAM is enabled. Only MAM is added for users in that group when they workplace join personal device. Devices are not automatically MDM enrolled.
   ![Screenshot of the Azure portal](./media/auto-enroll-scope.png)
5. Use the default values for the following URLs:
    - **MDM Terms of use URL**
    - **MDM Discovery URL**
    - **MDM Compliance URL**
6. Choose **Save**.
By default, two-factor authentication isn't enabled for the service. However, two-factor authentication is recommended when registering a device. To enable two-factor authentication, configure a two-factor authentication provider in Azure AD and configure your user accounts for multi-factor authentication. See [Getting started with the Azure Multi-Factor Authentication Server](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).
## Install the connector
Download [ODJConnectorSetupMSI.msi]( tp://download.microsoft.com/download/1/E/B/1EB59BBC-4C33-459B-8A1C-DD3EF98D7B51/ODJConnectorSetupMsi.msi) to a computer running Windows Server 2016 that has access to the Internet and your on-premise Azure Active Directory.
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
You can add Windows Autopilot devices by importing a CSV file with their information.

1. In [Intune in the Azure portal](https://aka.ms/intuneportal), choose **Device enrollment** > **Windows enrollment** > **Devices** > **Import**.

    ![Screenshot of Windows Autopilot devices](media/enrollment-autopilot/autopilot-import-device.png)

2. Under **Add Windows Autopilot devices**, browse to a CSV file listing the devices that you want to add. The file should list the serial numbers, Windows product IDs, hardware hashes, and optional order IDs of the devices.

    ![Screenshot of Adding Windows Autopilot devices](media/enrollment-autopilot/autopilot-import-device2.png)

3. Choose **Import** to start importing the device information. Importing can take several minutes.

4. After import is complete, choose **Device enrollment** > **Windows enrollment** > **Windows Autopilot** > **Devices** > **Sync**. A message displays that the synchronization is in progress. The process might take a few minutes to complete, depending on how many devices are being synchronized.

5. Refresh the view to see the new devices.

## Create and assign an Autopilot deployment profile
Autopilot deployment profiles are used to configure the Autopilot devices.
1. In [Intune in the Azure portal](https://aka.ms/intuneportal), choose **Device enrollment** > **Windows enrollment** > **Deployment Profiles** > **Create Profile**.
2. Type a **Name** and optional **Description**.
3. If you want all devices in the assigned groups to automatically convert to Autopilot, set **Convert all targeted devices to Autopilot** to **Yes**. All non-Autopilot devices in assigned groups will register with the Autopilot deployment service. Allow 48 hours for the registration to be processed. When the device is unenrolled and reset, Autopilot will enroll it. After a device is registered in this way, disabling this option or removing the profile assignment won't remove the device from the Autopilot deployment service. You must instead [remove the device directly](enrollment-autopilot.md#delete-autopilot-devices).
4. For **Deployment mode**, choose **User-driven**.
5. In the **Join to Azure AD as** box, choose **Hybrid Azure AD joined**.
6. Choose **Out-of-box experience (OOBE)**, configure the options as needed, and then choose **Save**.
7. Choose **Create** to create the profile. 
8. In the profile blade, choose **Assignments**.
9. Choose **Select groups**, then in the **Select groups** blade, choose the dynamic device group that created earlier, then choose **Select**.
It will take around 15 minutes for the dynamic device group’s profile status to change from **Not assigned** to **Assigning** and finally to **Assigned**.
## Turn on the enrollment status page
1.  In [Intune](https://aka.ms/intuneportal), choose **Device enrollment** > **Windows enrollment** > **Enrollment Status Page (Preview)**.
2.  In the **Enrollment Status Page** blade, choose **Default** > **Settings**.
3.  For **Show app and profile installation progress**, choose **Yes**.
4. For **Block device use until all apps and profiles are installed**, choose **Yes**.
5.  Choose **Save**.
## Create a Domain Join profile and assign it to the dynamic device group
1. In **Microsoft Intune**, select **Device configuration**, and select **Profiles**. Then select **Create Profile**.
2. Enter the following properties:
   - **Name**: Enter a descriptive name for the new profile.
   - **Description**: Enter a description for the profile.
   - **Platform**: Choose **Windows 10 and later**.
   - **Profile type**: Choose **Domain Join**.
3.  Choose **Settings** and provide a **Computer name prefix**, **Domain name**, and **Organizational unit** (optional). 
4. Choose **OK** > **Create**. The profile is created, and appears in the list.
## Install the latest Windows Insider build on the device
1.	Download and install the [Windows Insider Preview]( https://www.microsoft.com/software-download/windowsinsiderpreviewiso) to the device.
2.	Follow the instructions on the device.


