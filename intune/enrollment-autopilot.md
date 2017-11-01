---
# required metadata

title: Enroll Windows devices using Windows AutoPilot Deployment Program
description: "Learn how to enroll new Windows 10 devices using Windows AutoPilot Deployment program."
keywords:
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 10/04/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944

---

# Enroll Windows devices using Windows AutoPilot Deployment Program
The Windows AutoPilot Deployment Program simplifies device provisioning. Today, it takes a lot of time building and maintaining customized operating system images. You might also spend a lot of time applying these custom operating system images to new devices to prepare them for use before giving them to your end users. With Microsoft Intune and AutoPilot, you can give new devices to your end users without the need to build, maintain, and apply custom operating system images to the devices. When you use Intune to manage AutoPilot devices, you can manage policies, profiles, apps, etc. on the devices after they are enrolled. For an overview of benefits, scenarios, and prerequisites, see [Overview of Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-10-auto-pilot).

## Prerequisites
- [Devices must be registered to your organization](https://docs.microsoft.com/windows/deployment/windows-10-auto-pilot#registering-devices-to-your-organization)
- [Windows automatic enrollment enabled](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Azure Active Directory Premium subscription](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## Synchronize devices
Synchronize your registered devices into Intune so that you can configure them.

1. Sign into [Azure](https://portal.azure.com/).
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device enrollment**.
4. On the **Windows enrollment** blade, in the **Windows AutoPilot Deployment Program** section, choose **Devices**.
5. Click **Sync** to import your registered devices. A message displays that the synchronization is in progress.
6. Refresh the view to see the new devices. The process might take a few minutes to complete, depending on how many devices are being synchronized.  

## Create an AutoPilot deployment profile
AutoPilot deployment profiles are used to configure the AutoPilot devices.
1. Sign into the [Azure](https://portal.azure.com/). 
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device enrollment**.
4. On the **Windows enrollment** blade, in the **Windows AutoPilot Deployment Program** section, choose **Deployment Profiles**.
5. Click **Create Profile**, and choose a name and optional description. 
6. For **Join type**, select **Azure AD joined**.​
7. For **Out-of-box experience (OOBE)**, configure the following options, and then click **OK**: 
   - **Privacy settings**: Choose whether to show privacy settings to users. 
   - **End-user license agreement (EULA)**: Choose whether to show the EULA to users.
   - **User account type**: Choose whether the user's account type is an **Administrator** or **Standard** user.

     > [!Note]    
     > This setting does not apply to Global Administrator or Company Administrator accounts. These accounts cannot be standard users because they have access to all administrative features in Azure AD.
8. Click **Create** to create the profile. The AutoPilot deployment profile is now available to assign to devices.
     
> [!Note]    
> The following settings are configured with all AutoPilot deployment profiles:
> - Skip Cortana, OneDrive, and OEM registration setup pages
> - Automatically set up for work or school
> - Sign in experience with company or school brand    

## Assign an AutoPilot deployment profile
After you create AutoPilot deployment profiles, you can assign them to selected devices.

1. Sign into the [Azure](https://portal.azure.com/). 
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device enrollment**.
4. On the **Windows enrollment** blade, in the **Windows AutoPilot Deployment Program** section, choose **Devices**.
5. Select the devices to which you want to assign the deployment profile. You can filter on the **Status** column to easily find devices without an assigned profile. 
6. Click **Assign profile**, select the AutoPilot deployment profile, and then click **Assign**. A message displays that the assignment is in progress.
7. Refresh the view to see that the profile has been assigned to the devices. The process might take a few minutes to complete, depending on how many devices you selected. 

> [!Note]
> The new profile is assigned to the device. However, the profile won’t be applied to devices that have already enrolled in Intune until after the device has been reset and reenrolled.

### Assign a different AutoPilot deployment profile
After you've assigned an AutoPilot deployment profile to a device, if you decide to assign a different profile, assign the new profile to the device.  

## Edit an AutoPilot deployment profile 
After you've created an AutoPilot deployment profile, you can edit certain parts of the deployment profile.   
1. Sign into the [Azure](https://portal.azure.com/). 
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device enrollment**.
4. On the **Windows enrollment** blade, in the **Windows AutoPilot Deployment Program** section, choose **Deployment Profiles**. 
5. Select the profile you would like to edit. 
6. Click **Properties** on the left to change the name or description of the deployment profile. Click **Save** after you make changes. 
7. Click **Settings** to make changes to the OOBE settings. Click **Save** after you make changes. 

> [!NOTE]
> The updated profile is assigned to devices. However, the updated profile won't be applied to a device that has already enrolled in Intune until after the device is reset and reenrolled. 

## Using AutoPilot in other portals
If you are not interested in mobile device management, you have the ability to use AutoPilot in Microsoft Store for Business, for example. While using other portals is an option, we recommend that you only use Intune to manage your AutoPilot deployments. If you use Intune and another portal, Intune isn't able to:
- Display changes to profiles created in Intune, but edited in another portal
- Synchronize profiles created in another portal
- Display changes to profile assignments done in another portal
- Synchronize profile assignments done in another portal

## Next steps
After you configure Windows AutoPilot for registered Windows 10 devices, learn how to manage those devices. For details, see [What is Microsoft Intune device management?](https://docs.microsoft.com/intune/device-management)