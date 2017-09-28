---
# required metadata

title: Enroll Windows devices using Windows AutoPilot Deployment Program
description: "Learn how to enroll new Windows 10 devices using Windows AutoPilot Deployment program."
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

# Enroll Windows devices using Windows AutoPilot Deployment Program
The Windows AutoPilot Deployment Program simplifies device set up for IT Admins. With Microsoft Intune, you can create and then assign an *AutoPilot deployment profile* to your new Windows 10 devices. When people in your organization run the out-of-box experience (OOBE) on the device, the profile configures Windows based on the AutoPilot deployment profile you assigned to the device. When you use Intune to manage AutoPilot profiles, you can monitor the AutoPilot progress of new devices through Intune enrollment, and then continue to manage policies, profiles, apps, etc. on the devices after they are automatically enrolled. For an overview of benefits, scenarios, and prerequisites, see [Overview of Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-10-auto-pilot). 

## Prerequisites

- [Devices must be registered to your organization](https://docs.microsoft.com/windows/deployment/windows-10-auto-pilot#registering-devices-to-your-organization)
- [Windows automatic enrollment enabled] (https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Azure Active Directory Premium subscription](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->


## Synchronize devices
Synchronize your registered devices into Intune so that you can configure them.

1. Sign into the [Azure portal](https://portal.azure.com/).
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device enrollment**.
4. On the **Windows enrollment** blade, in the **AutoPilot deployment profiles** section, choose **Devices**.
5. Click **Sync** to import the devices from the Microsoft Store for Business. You might have to refresh the view for the devices to display. 

## Create an AutoPilot deployment profile
AutoPilot deployment profiles have two main parts. There are default settings that can't be changed, and optional settings that you can include. After you synchronize devices, create an AutoPilot deployment profile in Intune.
1. Sign into the [Azure portal](https://portal.azure.com/)
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device enrollment**.
4. On the **Windows enrollment** blade, in the **AutoPilot deployment profiles** section,choose **Deployment Profiles**.
5. Click **Create Profile**, and choose a name and optional description. 
6. For **Join type**, select **Azure AD joined**.​
7. For **Out-of-box experience (OOBE)**, configure the following options, and then click **OK**: 
   - **Privacy settings**: Choose whether to show privacy settings to users. 
   - **End user license agreement (EULA)**: Choose whether to show the EULA to users.
   - **User account type**: Choose whether the user's account type is an **Administrator** or **Standard** user.
   > [!Note]    
   > The following settings are configured with all AutoPilot deployment profiles:
   > - Skip Cortana, OneDrive, and OEM registration setup pages
   > - Automatically set up for work or school
   > - Sign in experience with company or school brand 

The AutoPilot deployment profile is created and available to assign to devices.

## Assign an AutoPilot deployment profile
After you create AutoPilot deployment profiles, you can assign a profile to selected devices. 

1. Sign into the [Azure portal](https://portal.azure.com/)
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device enrollment**.
4. On the **Windows enrollment** blade, in the **AutoPilot deployment profile** section, choose **Devices**.
5. Select the devices to which you want to assign the deployment profile. You can filter on the **Status** column to easily find devices without an assigned assigned. 
6. Click **Assign profile**, select the AutoPilot profile, and then click **Assign**. 
7. Intune assigns the profile to your selected devices. Click a device to review information about the device. The AutoPilot deployment profile is listed under **Assigned profile**.  

## Assign a different AutoPilot deployment profile to a device
After you've assigned an AutoPilot deployment profile to a device, if you decide to assign a different profile, assign the new profile to the device.  

> [!NOTE]
> The new profile will be assigned to the device, but if the device has already gone through the OOBE, it won’t be applied to the device until after the device has been reset.

## Next steps
After you configure Windows AutoPilot for registered Windows 10 devices, learn how to manage those devices. For details, see [What is Microsoft Intune device management?](https://docs.microsoft.com/intune/device-management)