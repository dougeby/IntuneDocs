---
# required metadata

title: Manage Windows AutoPilot Deployment in Intune
description: "Learn to create and assign AutoPilot profiles in Intune to control what is included in the Windows set up experience for new Windows 10 devices."
keywords:
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 09/28/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944

---

# Manage Windows AutoPilot Deployment in Intune
Windows AutoPilot Deployment Program simplifies device set up for IT Admins. With Microsoft Intune, you can create and then assign an *AutoPilot deployment profile* to your new Windows 10 devices. When people in your organization run the out-of-box experience (OOBE) on the device, the profile configures Windows based on the AutoPilot deployment profile you assigned to the device. Using Intune to manage AutoPilot profiles, you can monitor the AutoPilot progress of new devices through Intune enrollment, and then continue to manage policies, profiles, apps, etc. on the devices after they are enrolled. For an overview of benefits, scenarios, and prerequisites, see [Overview of Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-10-auto-pilot). 



## Register your devices to your organization 
To manage new Windows 10 devices using Intune, you must first register devices to your organization by adding the devices to the Microsoft Store for Business. You can also add devices using Microsoft Store for Education or the Partner Center admin portal.   
 
You will need a .csv file that contains specific information about the devices. You should be able to get this from your Microsoft account contact or the store where you purchased the devices. We are actively working with various hardware vendors to enable them to provide the required information to you, or upload it on your behalf. If you would like to capture that information by yourself, you can use the Get-WindowsAutoPilotInfo PowerShell script, which will generate a .csv file with the device's hardware ID.    

### Device information file format
Columns in the device information file need to use this naming and be in this order:
- Column A: Device Serial Number
- Column B: Windows Product ID 
- Column C: Hardware Hash    
    
In the .csv file, do not use spaces before or after commas that separate each column. Here's a sample of a device information file:

![Notepad file showing example entries for Column A (Device Serial Number), Column B (Windows Product ID), and Column C (Hardware Hash).](./media/autopilot-csv.png)

### Add devices to Microsoft Store for Business or Education
Use the following procedure to add devices to the Microsoft Store for Business.    
1. Sign in to [Microsoft Store for Business](http://businessstore.microsoft.com) or [Microsoft Store for Education](https://educationstore.microsoft.com). 
2. Click **Manage**, and then click **Devices**.
3. Click **Add devices**, navigate to the *.csv file and select it. 
4. Choose whether to create a new AutoPilot deployment group, or choose one from the list, and then click **Add**. Use these groups to apply AutoPilot deployment profiles to a group of devices. Click **No, thanks** if you don't want to add devices to a group. Later in Intune, you can apply a deployment profile to individual devices that you select.   
   ![Screenshot of Add devices to a group dialog. You can create a new group, or select a current group.](./media/autopilot-add-devices.png)    

> [!NOTE]
> You can only add devices to a group for devices that are added to the **Microsoft Store for Business and Education**. If you decide to reorganize devices into different groups, you'll need to delete them from **Devices** in the Microsoft store, and add them again.    

After the devices are added, you can synchronize your devices and manage those devices in Intune. 


## Synchronize devices
After you add devices to the Microsoft Store for Business, you must synchronize the devices into Intune. 

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device enrollment**.
4. On the **Windows enrollment** blade, choose **Devices**.
5. Click **Sync** to import the devices from the Microsoft Store for Business. You might have to refresh the view for the devices to display. 


## AutoPilot deployment profiles
AutoPilot deployment profiles have two main parts. There are default settings that can't be changed, and optional settings that you can include. 

### AutoPilot deployment profiles - default settings
The following settings are configured with all AutoPilot deployment profiles:
- Skip Cortana, OneDrive, and OEM registration setup pages
- Automatically set up for work or school
- Sign in experience with company or school brand 

### AutoPilot deployment profiles - optional settings
The following settings are off by default. You can turn them on for your AutoPilot deployment profiles:
- Show or hide privacy settings
- Show or hide the end user license agreement (EULA)
- Disable local admin account creation on the device

### Create an AutoPilot deployment profile
After you synchronize devices, you must create an AutoPilot deployment profile in Intune.
1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device enrollment**.
4. On the **Windows enrollment** blade, choose **Deployment Profiles**.
5. Click **Create Profile**, and choose a name and description. 
6. For **Join type**, specify how devices join Active Directory (AD) in your organization:
   - **Azure AD joined**: Cloud-only without an on-premises Windows Server Active Directory.​
   - **Hybrid Azure AD joined**: Both cloud (Azure AD) and on-premises Windows Server Active Directory.
7. For **Out-of-box experience (OOBE)**, configure the following options and then click **OK**: 
   - **Privacy settings**: Choose whether to show privacy settings to users. 
   - **End user license agreement (EULA)**: Choose whether to show the EULA to users.
   - **User account type**: Choose whether the user's account type is an **Administrator** or **Standard** user.
The AutoPilot deployment profile is created and available to assign to devices.

### Assign an AutoPilot deployment profile
After you create AutoPilot deployment profiles, you can assign a profile to selected devices or a deployment group. 

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device enrollment**.
4. On the **Windows enrollment** blade, choose **Devices**.
5. Click **Filter** to filter the list of devices. For example, you can select a specific deployment group to only list the devices in that group. Click **Apply** to filter the list and **Reset** to remove the filter. 
6. Select the devices to which you want to assign the deployment profile.
7. Click **Assign profile**, select the AutoPilot profile, and then click **Assign**. 
8. Intune assigns the profile to your selected devices. Click a device to review information about the device. The AutoPilot deployment profile is listed under **Assigned profile**.  

### Assign a different AutoPilot deployment profile to a device
After you've assigned an AutoPilot deployment profile to a device, if you decide to assign a different profile, you can remove the profile and assign a new profile. 

> [!NOTE]
> The new profile will only be assigned if the device has not been started, and gone through the out-of-box experience. Settings from a different profile can't be assigned when another profile has been assigned. Windows would need to be reinstalled on the device for the second profile to be assigned to the device. 

## Next steps
After you configure Windows AutoPilot for registered Windows 10 devices, learn how to manage those devices. For details, see [What is Microsoft Intune device management?](https://docs.microsoft.com/intune/device-management)