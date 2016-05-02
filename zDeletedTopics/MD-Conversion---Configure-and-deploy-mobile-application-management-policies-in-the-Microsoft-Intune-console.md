---
title: MD Conversion - Configure and deploy mobile application management policies in the Microsoft Intune console
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f14385ef-f49f-4d43-9fa4-4355a4d94d3f
---
# MD Conversion - Configure and deploy mobile application management policies in the Microsoft Intune console
Mobile application management policies in [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] let you modify the functionality of apps that you deploy to help bring them into line with your company compliance and security policies. For example, you can restrict cut, copy and paste operations within a managed app, or configure an app to open all web links inside a managed browser.

Mobile application management policies support:

-   Devices that run Android 4 and later.

-   Devices that run iOS 7 and later.

> [!TIP]
> Mobile application management policies support devices that are enrolled with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].
> 
> If you are looking for information about how to create app management policies for devices that are not managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], see [Configure data loss prevention app policies with Microsoft Intune](../Topic/Configure-data-loss-prevention-app-policies-with-Microsoft-Intune.md).

Unlike other [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policies, you do not deploy a mobile application management policy directly. Instead, you associate the policy with the app that you want to restrict. When the app is deployed and installed on devices, the settings you specify will take effect.

To apply restrictions to an app, the app must incorporate the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] App Software Development Kit (SDK). There are two methods of obtaining this type of app:

-   **Use a policy managed app** – Has the App SDK built-in. To add this type of app, you specify a link to the app from an app store such as the iTunes store or Google Play. No further processing is required for this type of app. See a list of [Microsoft apps you can use with Microsoft Intune mobile application management policies](../Topic/Microsoft-apps-you-can-use-with-Microsoft-Intune-mobile-application-management-policies.md).

-   **Use a ‘wrapped’ app** - Apps that are repackaged to include the App SDK by using the **Microsoft Intune App Wrapping Tool**. This tool is typically used to process company apps that were created in-house. It cannot be used to process apps that were downloaded from the app store. See [Prepare iOS apps for mobile application management with the Microsoft Intune App Wrapping Tool](../Topic/Prepare-iOS-apps-for-mobile-application-management-with-the-Microsoft-Intune-App-Wrapping-Tool.md) and [Prepare Android apps for mobile application management with the Microsoft Intune App Wrapping Tool](../Topic/Prepare-Android-apps-for-mobile-application-management-with-the-Microsoft-Intune-App-Wrapping-Tool.md).

Some managed apps, like the Outlook app for iOS and Android support **multi-identity**. This means that [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] only applies management settings to corporate accounts or data in the app.

For example, using the Outlook app:

-   If the user configures a corporate, and a personal email account, [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] only applies management settings to the corporate account and does not manage the personal account.

-   If the device is retired, or unenrolled, only the corporate Outlook data is removed from the device.

-   The corporate account used must be the same account that was used to enroll the device with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

> [!TIP]
> If you are using [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] with [!INCLUDE[cmshort](../Token/cmshort_md.md)], see [How to Control Apps Using Mobile Application Management Policies in Configuration Manager](https://technet.microsoft.com/library/mt131414.aspx).

## Create and deploy an app with a mobile application management policy

-   **Step 1:** Get the link to a policy managed app, or create a wrapped app.

-   **Step 2:** Publish the app to your cloud storage space.

-   **Step 3:** Create a mobile application management policy.

-   **Step 4:** Deploy the app, selecting the option to associate the app with a mobile application management policy.

-   **Step 5:** Monitor the app deployment.

## **Step 1:** Obtain the link to a policy managed app, or create a wrapped app

-   **To obtain a link to a policy managed app** - From the app store, find, and note the URL of the policy managed app you want to deploy.

    For example, the URL of the Microsoft Word for iPad app is **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**

-   **To create a wrapped app** - Use the information in the topics [Prepare iOS apps for mobile application management with the Microsoft Intune App Wrapping Tool](../Topic/Prepare-iOS-apps-for-mobile-application-management-with-the-Microsoft-Intune-App-Wrapping-Tool.md) and [Prepare Android apps for mobile application management with the Microsoft Intune App Wrapping Tool](../Topic/Prepare-Android-apps-for-mobile-application-management-with-the-Microsoft-Intune-App-Wrapping-Tool.md) to create a wrapped app.

    The tool creates a processed app that you will use when you publish the app to your cloud storage space.

## **Step 2:** Publish the app to your cloud storage space
When you publish a managed app, the procedures differ depending on whether you are publishing a policy managed app, or an app that was processed using the Microsoft Intune App Wrapping Tool for iOS.

#### To publish a policy managed app

1.  When you are ready to upload the app to your cloud storage space, follow the instructions in [Publish mobile device software to Microsoft Intune cloud storage](../Topic/Deploy-apps-to-mobile-devices-in-Microsoft-Intune---deleted.md#BKMK_PublishSoftware).

2.  For iOS apps, select **Managed iOS App from the App Store**, under **Select how this software is made available to devices**.

    For Android apps, select **External link**.

3.  Under **Specify the URL**, enter the URL to the policy managed app that you noted earlier.

After the upload completes, you will see **Yes** for **App Management Policies** on the **Software Properties** page for the uploaded app.

Once you have verified that the app is uploaded successfully, continue to Step 3.

#### To publish an app that was processed using the Microsoft Intune App Wrapping Tool

1.  When you are ready to upload the app to your cloud storage space, follow the instructions in [Publish mobile device software to Microsoft Intune cloud storage](../Topic/Deploy-apps-to-mobile-devices-in-Microsoft-Intune---deleted.md#BKMK_PublishSoftware).

2.  Select **Software Installer**, under **Select how this software is made available to devices**.

3.  Select **App package for iOS (&#42;.ipa file)** under **Software installer file type**.

After the upload completes, you will see **Yes** for **App Management Policies** on the **Software Properties** page for the uploaded app.

Once you have verified that the app is uploaded successfully, continue to Step 3.

## <a name="bkmk_step3"></a>**Step 3:** Create a mobile application management policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Overview** &gt; **Add Policy**.

2.  Configure and deploy one of the following **Software** policies, depending on the device type you want to configure apps for:

    -   **Mobile Application Management Policy (Android 4 and later)**

    -   **Mobile Application Management Policy (iOS 7 and later)**

    You can use recommended settings or customize the settings. For details, see [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

3.  Configure the following values as required. The options might differ depending on the device type for which you are configuring the policy.

    |Value|More information|
    |---------|--------------------|
    |**Name**|Specify a name for this policy.|
    |**Description**|Optionally, specify a description for this policy.|
    |**Restrict web content to display in a corporate managed browser**|When this setting is enabled, any links in the app will be opened in the Managed Browser. You must have deployed this app to devices in order for this option to work.|
    |**Prevent Android backups** or **Prevent iTunes and iCloud backups**|Disables the backup of any information from the app.|
    |**Allow app to transfer data to other apps**|Specifies the apps that this app can send data to. You can choose to not allow data transfer to any app, only allow transfer to other managed apps, or to allow transfer to any app. This setting does not control use of the **Open In** feature on mobile devices.<br /><br />For example, when you do not allow data transfer, you restrict data transfer to services like SMS messaging, assigning images to contacts, and posting to Facebook or Twitter.<br /><br />For iOS devices, to prevent document transfer between managed and unmanaged apps, you must also configure and deploy a mobile device security policy that disables the setting **Allow managed documents in other unmanaged apps** If you select to only allow transfer to other managed apps, the Intune PDF and image viewers (if deployed) will be used to open content of the respective types..<br /><br />Additionally, if you set this option to **Policy Managed Apps** or **None**, the iOS 9 feature that allows Spotlight Search to search data within apps will be blocked.|
    |**Allow app to receive data from other apps**|Specifies the apps that this app can receive data from. You can choose to not allow data transfer from any app, only allow transfer from other managed apps, or allow transfer from any app<br /><br />For iOS apps that support multi-identity (where [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] only applies management settings to corporate accounts or data in the app), fpr an enrolled device with a mobile application management policy applied, when a user accesses data from an app that is not managed by a mobile application management policy, the data will be treated as corporate data and protected by the policy.|
    |**Prevent “Save As”**|Disables use of the **Save As** option to save data to personal cloud storage locations (such as OneDrive Personal or Dropbox) in any app that uses this policy.|
    |**Restrict cut, copy and paste with other apps**|Specifies how cut, copy, and paste operations can be used with the app. Choose from:<br /><br />**Blocked** – Do not allow cut, copy, and paste operations between this app and other apps.<br /><br />**Policy Managed Apps** – Only allow cut, copy, and paste operations between this app and other managed apps.<br /><br />**Policy Managed Apps with Paste In** – Allow data cut or copied from this app only to be pasted into other managed apps. Allow data cut or copied from any app to be pasted into this app.<br /><br />**Any App** – No restrictions to cut, copy, and paste operations to, or from this app.<br /><br />To copy and paste data between managed apps, both apps must have either the **Policy Managed Apps** or **Policy Managed Apps with Paste In** settings configured.|
    |**Require simple PIN for access**|Requires the user to enter a PIN number which they specify to use this app. The user will be asked to set this up the first time they run the app.|
    |**Number of attempts before PIN reset**|Specify the number of PIN entry attempts which can be made before the user must reset the PIN.|
    |**Require corporate credentials for access**|Requires that the user must enter their corporate logon information before they can access the app.|
    |**Require device compliance with corporate policy for access**|Only allows the app to be used when the device is not jailbroken or rooted.|
    |**Recheck the access requirements after (minutes)**|In the **Timeout** field, specify the time period before the access requirements for the app are rechecked after the app is launched.|
    |**Offline grace period**|If the device is offline, specify the time period before the access requirements for the app are rechecked.|
    |**Encrypt app data**|Specifies that all data associated with this app will be encrypted, including data stored externally, such as SD cards.<br /><br />**Encryption for iOS**<br /><br />For apps that are associated with an [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] mobile application management policy, data is encrypted at rest using device level encryption provided by the OS. This is enabled through device PIN policy that must be set by the IT admin. When a PIN is required, the data will be encrypted per the settings in the mobile application management policy. As stated in Apple documentation, [the modules used by iOS 7 are FIPS 140-2 certified](http://support.apple.com/en-us/HT202739).<br /><br />**Encryption for Android**<br /><br />For apps that are associated with an [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] mobile application management policy, encryption is provided by Microsoft. Data is encrypted synchronously during file I/O operations according to the setting in the mobile application management policy. Managed apps on Android use AES-128 encryption in CBC mode utilizing the platform cryptography libraries. The encryption method is not FIPS 140-2 certified. Content on the device storage will always be encrypted.|
    |**Block screen capture** (Android devices only)|Specifies that the screen capture capabilities of the device are blocked when using this app.|

4.  When you are finished, click **Save Policy**.

The new policy displays in the **Configuration Policies** node of the **Policy** workspace.

## **Step 4:** Associate the app with a mobile application management policy, then deploy the app.
Deploy the app, ensuring that you select the mobile application management policy on the **Mobile App Management** page to associate the policy with the app.

For details, see [Deploy apps to mobile devices in Microsoft Intune - deleted](../Topic/Deploy-apps-to-mobile-devices-in-Microsoft-Intune---deleted.md).

> [!IMPORTANT]
> For devices that run operating systems earlier than iOS 7.1, associated policies will not be removed when the app is uninstalled.
> 
> If the device is unenrolled from [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], polices are not removed from the apps; any apps that had policies applied will retain the policy settings even after the app is uninstalled and reinstalled.

### What to do when an app is already deployed on devices
There might be situations where you deploy an app and one of the targeted users or devices already has an unmanaged version of the app installed, for example, the user installed Microsoft Word from the app store.

In this case, you must ask the user to manually uninstall the unmanaged version so that the managed version you configured can be installed.

However, for devices that run iOS 9 and later, [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] will automatically ask the user for permission to take over management of the existing app. If they agree, then the app will become managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] and any mobile application management policies you associated with the app will also be applied .

> [!TIP]
> If the device is in supervised mode, [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] will take over management of the existing app without asking the users permission.

## **Step 5:** Monitor the app deployment.
Once you have created and deployed an app associated with a mobile application management policy, use the following procedures to monitor the app and resolve any policy conflicts.

#### To view the status of the deployment

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Groups** &gt; **Overview**.

2.  Perform one of the following steps:

    -   Click **All Users**, then double-click on the user whose devices you want to examine. One the **User Properties** page, click **Devices**, then double-click the device you want to examine.

    -   Click **All Devices** &gt; **All Mobile Devices**. On the **Device Group Properties** page, click **Devices**, then double-click the device you want to examine.

3.  From the **Mobile Device Properties** page, click **Policy** to see a list of the mobile application management policies that have been deployed to the device.

4.  Select the mobile application management policy whose status you want to view. You can view details of the policy in the bottom pane and expand its node to display its settings.

5.  Under the **Status** column of each of the mobile application management policies, **Conforms**, **Conforms (Pending)**, or **Error** will be displayed. If the selected policy has one or more settings in conflict, **Error** will be displayed in this field.

6.  Once you have identified a conflict, you can revise conflicting policy settings to use the same setting, or deploy only one policy to the app and user.

### <a name="BKMK_Conf"></a>How policy conflicts are resolved
When there is a mobile application management policy conflict on the first deployment to the user or device, the specific setting value in conflict will be removed from the policy deployed to the app, and the app will use a built-in conflict value.

When there is a mobile app management policy conflict on later deployments to the app or user, the specific setting value in conflict will not be updated on the mobile app management policy deployed to the app, and the app will use the existing value for that setting.

In cases where the device or user receives two conflicting policies, the following behavior applies:

-   If a policy has already been deployed to the device, the existing policy settings are not overwritten.

-   If no policy has already been deployed to the device, and two conflicting settings are deployed, the default setting built into the device is used.

## See Also
[Protect data and devices with Microsoft Intune](../Topic/Protect-data-and-devices-with-Microsoft-Intune.md)
[Deploy and configure apps with Microsoft Intune](../Topic/Deploy-and-configure-apps-with-Microsoft-Intune.md)

