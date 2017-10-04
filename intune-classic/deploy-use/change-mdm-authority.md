---
# required metadata

title: "Change your MDM authority to Configuration Manager (hybrid MDM)"
description: "Learn how to change the MDM authority from Intune standalone to Configuration Manager (hybrid MDM)."
keywords:
author: dougeby
manager: angrobe
ms.date: 05/21/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f1b4bce3-7932-4a0d-aa92-6dacc7060f42

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---
# Change the MDM authority
Beginning in Configuration Manager version 1610, you can change your MDM authority without having to contact Microsoft Support, and without having to unenroll and reenroll your existing managed devices. This topic provides the steps to change an existing Microsoft Intune tenant configured from Intune and with the MDM authority set to **Microsoft Intune** (standalone) to **Configuration Manager** (hybrid MDM) without having to unenroll and reenroll existing managed devices.

> [!Note]    
> If you want to change an existing Microsoft Intune tenant configured from the Configuration Manager console (hybrid) and with the MDM authority set to **Configuration Manager** (hybrid) to **Microsoft Intune** standalone, see [Change the MDM authority from Configuration Manager (hybrid MDM) to Intune standalone](https://docs.microsoft.com/sccm/mdm/deploy-use/change-mdm-authority). 


### Key Considerations
After you switch to the new MDM authority, there will likely be transition time (up to eight hours) before the device checks in and synchronizes with the service. You will be required to configure settings in the new MDM authority (hybrid) to ensure that enrolled devices will continue to be managed and protected after the change. Note the following:
- Devices must connect with the service after the change so that the settings from the new MDM authority (Intune standalone) will replace the existing settings on the device.
- After you change the MDM authority, some of the basic settings (such as profiles) from the previous MDM authority (Intune standalone) will remain on the device for up to 7 days or until the device connects to the service for the first time. It is recommended that you configure apps and settings (policies, profiles, apps, etc.) in the new MDM authority (hybrid) as soon as possible and deploy the settings to the user groups that contains users who have existing enrolled devices. As soon as a device connects to the service after the change in MDM authority, it will receive the new settings from the new MDM authority and prevent gaps in management and protection.
- When when the same device categories exist in both Intune and Configuration Manager, any device category assignments for devices are not carried over after you switch to the new MDM authority. To continue using device categories, migrated devices have to be manually added to the appropriate collections after the MDM authority is changed and the devices display in the Configuration Manager console.
- Devices that don't have associated users (typically when you have iOS Device Enrollment Program or bulk enrollment scenarios) are not migrated to the new MDM authority. For those devices, you need to call support for assistance to move them to the new MDM authority.

### Prepare to change the MDM authority to Configuration Manager (hybrid)
Review the following information to prepare for the change to the MDM authority:
- You must have Configuration Manager version 1610 or higher for the option to change the MDM authority to be available.
- It can take up to eight hours for a device to connect to the service after you change to the new MDM authority.
- Create a Configuration Manager user collection with all users currently managed by Intune Standalone that you will use when you set up the Intune subscription in the Configuration Manager console. This will help ensure that the user and their devices will have a Configuration Manager license assigned and be managed in the hybrid environment after the change to the MDM authority.
- Make sure that the IT Admin user is in this user collection too.  
- Before the change, the MDM Authority will show as **Set to Microsoft Intune** (standalone) in the Intune administration console.
- The MDM authority should display **Set to Microsoft Intune** (standalone tenant) in the Microsoft Intune administration console prior to the change in MDM authority.
    > [!NOTE]    
    > If your MDM authority displays **Managed by Intune and Office 365**, then your Office 365 managed MDM devices will no longer be managed when you change your MDM authority to **Configuration Manager** (hybrid). We recommend that you license those users for Intune or Enterprise Mobility Suite before you change the MDM authority.   

- In the [Microsoft Intune administration console](http://manage.microsoft.com), remove the Device Enrollment Manager role. For details, see [Delete a device enrollment manager from Intune](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune#delete-a-device-enrollment-manager-from-intune).
- Turn off any device group mappings that are configured. For details, see [Categorize devices with device group mapping in Microsoft Intune](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune).
- There should be no noticeable impact to end users during the change in MDM authority. However, you might want to communicate this change to users to make sure that their devices are powered on and that they connect with the service soon after the change. This ensures that as many devices as possible connect and register with the service through the new authority as soon as possible.
- If you are using Intune standalone to manage iOS devices prior to the change in MDM authority, you must make sure that the same Apple Push Notification service (APNs) certificate that was previously used in Intune is renewed and used to set up the tenant again in Configuration Manager (hybrid).    

    > [!IMPORTANT]  
    > If a different APNs certificate is used for hybrid, then ALL previously enrolled iOS devices become unenrolled and you have to go through the process to reenroll them. Prior to making the MDM authority change, make sure that you know exactly what APNs certificate was used to manage iOS devices in Intune. Find the same certificate listed in Apple Push Certificates Portal (https://identity.apple.com) and make sure the user whose Apple ID was used to create the original APNs certificate is identified and available to renew the same APNs certificate as part of the change to the new MDM authority.  

### Change the MDM authority to Configuration Manager
The process to change the MDM authority to Configuration Manager (hybrid) includes the following high-level steps:  
- In the Configuration Manager console, add the Microsoft Intune subscription.
- Configure the Apple APNs certificate by using the same APNs certificate that you renewed.
- In the Configuration Manager console, configure and deploy new settings and apps from the new MDM authority (hybrid).
- The next time devices connect to the service, it synchronizes and receives the new settings from the new MDM authority.

#### To change the MDM authority to Configuration Manager
1. In the Configuration Manager console, go to **Administration** &gt; **Overview** &gt; **Cloud Services** &gt; **Microsoft Intune Subscription**, and select to add an Intune subscription.
2. Sign-in to the Intune tenant that you originally used when you set the MDM authority in Intune, and click **Next**.
3. Select **Change my MDM Authority to Configuration Manager**, and click **Next**.
4. Select the user collection to contain all of the users that will continue to be managed by the new hybrid MDM authority.
5. Click **Next** and complete the wizard. The MDM authority is now changed to **Configuration Manager**.
6. Login to the [Microsoft Intune administration console](http://manage.microsoft.com) using the same Intune tenant and confirm that the MDM authority has been changed to **Set to Configuration Manager**.


### Enable iOS enrollment
When you have iOS devices, you must configure the APNs certificate in Configuration Manager.

#### To enable iOS enrollment and configure the APNs certificate

1. **Download a certificate signing request**

    1. In the Configuration Manager console, go to **Administration** &gt; **Cloud Services** &gt; **Microsoft Intune Subscriptions**, and select **Create APNs certificate request** to open the **Request Apple Push Notification Service Certificate Signing Request** dialog box.  
    2. **Browse** to the path to save the new certificate signing request (.csr) file. Save the certificate signing request (.csr) file locally.  
    3. Click **Download**. The new Microsoft Intune .csr file downloads and is saved by Configuration Manager.   

    > [!IMPORTANT]
    > You must download a new certificate signing request. Do not use an existing file or it will fail.  

2.  Go to the [Apple Push Certificates Portal](http://go.microsoft.com/fwlink/?LinkId=269844), and sign-in with the **same** Apple ID that was used to previously create and renew the APNs certificate that you used in Intune standalone.

    ![Apple Push Certificates Portal sign-in page](../media/mdm-change-apns-portal.png)

3. Select the APNs certificate that you used in Intune standalone, and then click **Renew**.

    ![Renew APNs dialog box](../media/mdm-change-renew-apns.png)

4. Select the APNs certificate signing request (.csr) file that you downloaded locally, and then click **Upload**.

    ![Apple Push Certificates Portal sign-in page](../media/mdm-change-renew-apns-upload.png)
 
5. Select the same APNs, and then click **Download**. Download the APNs (.pem) certificate, and save the file locally.  

    ![Apple Push Certificates Portal sign-in page](../media/mdm-change-renew-apns-download.png)

6. Upload the renewed APNs certificate to the hybrid tenant using the same Apple ID as before.

    1.  In the Configuration Manager console, go to **Administration** &gt; **Cloud Services** &gt; **Microsoft Intune Subscription**, and choose **Configure Platforms** &gt; **iOS**.  
    2.  In the **Microsoft Intune Subscription Properties** dialog box, select the **APNs Certificate** tab and click to select the **Enable iOS and MAC OS X (MDM) enrollment** checkbox.  
    3.  Click **Browse**, and go to the APNs certificate (.cer) file downloaded from Apple. Configuration Manager displays the APNs certificate information. Click **OK** to save the APNs certificate to Intune.  

        ![Intune Subscription properties page - iOS](../media/mdm-change-subscription-properties-ios.png)

### Enable Android enrollment
1. In the Configuration Manager console, go to **Administration** &gt; **Cloud Services** &gt; **Microsoft Intune Subscription**, and choose **Configure Platforms** &gt; **Android**.  
2. Select **Enable Android enrollment** and click **OK**.

### Enable Windows enrollment
1. In the Configuration Manager console, go to **Administration** &gt; **Cloud Services** &gt; **Microsoft Intune Subscription**, and choose **Configure Platforms** &gt; **Windows**.  
2. Select **Enable Windows enrollment** and click **OK**.

### Enable Windows Phone enrollment
1. In the Configuration Manager console, go to **Administration** &gt; **Cloud Services** &gt; **Microsoft Intune Subscription**, and choose **Configure Platforms** &gt; **Windows Phone**.  
2. Select the platform that you want to enable, and click **OK**.


### Next steps
After the change in MDM authority is complete, review the following steps:
- When the Intune service detects that a tenant’s MDM authority has changed, it will send out a notification message to all the enrolled devices to check in and synchronize with the service (this is outside of the regularly scheduled check in). Therefore, after the MDM authority for the tenant has been changed from Intune standalone to hybrid, all the devices that are powered on and online will connect with the service, receive the new MDM authority, and be managed by hybrid going forward. There will be no interruption to the management and protection of these devices.
- Even for devices that are powered on and online during (or shortly after) the change in MDM authority, there will be a delay of up to eight hours (depending on the timing of the next scheduled regular check in) before devices are registered with the service under the new MDM authority.    

  > [!IMPORTANT]    
  > Between the time when you change the MDM authority and when the renewed APNs certificate is uploaded to the new authority, new device enrollments and device check in for iOS devices will fail. Therefore, it is important that you review and upload the APNs certificate to the new authority as soon as possible after the change in MDM authority.

- Users can quickly change to the new MDM authority by manually starting a check in from the device to the service. Users can easily do this by using the Company Portal app and initiating a device compliance check.
- To validate that things are working correctly after devices have checked-in and synchronized with the service after the change in MDM authority, look for the devices the Configuration Manager console. The devices that were previously managed by Intune will now be displayed as managed devices in the Configuration Manager console.    
- There is an interim period when a device is offline during the change in MDM authority and when that device checks in to the service. To help ensure that the device remains protected and functional during this interim period, the following will remain on the device for up to 7 days (or until the device connects with the new MDM authority and receives new settings that will overwrite the existing ones):
    - E-mail profile
    - VPN profile
    - Cert profile
    - Wi-Fi profile
    - Configuration profiles
- After you change to the new MDM authority, the compliance data in the Microsoft Intune administration console can take up to a week to accurately report. However, the compliance states in Azure Active Directory and on the device will be accurate so the device will still be protected.
- Make sure the new settings that are intended to overwrite existing settings have the same name as the previous ones to ensure that the old settings are overwritten. Otherwise, the devices might end up with redundant profiles and policies.    

  > [!TIP]    
  > As a best practice, you should create all management settings and configurations, as well as deployments, shortly after the change to the MDM authority has completed. This will help ensure that devices are protected and actively managed during the interim period.

-  After you change the MDM authority, perform the following steps to validate that new devices are enrolled successfully to the new authority:   
    - Enroll a new device
    - Make sure the newly enrolled device shows up in the Configuration Manager console.
    - Perform an action, such as Remote Lock, from the administration console to the device. If it is successful, the device is being managed by the new MDM authority.
- If you have issues with specific devices, you can unenroll and reenroll the devices to get them connected to the new authority and managed as quickly as possible.