---
# required metadata

title: How to add Windows store apps to IntunetitleSuffix: "Azure portal"
description: Learn about adding Windows store apps to Intune."
keywords:
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# How to add Windows store apps to Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Manage apps**.
4. In the **Mobile apps** workload, choose **Manage** > **Apps**.
5. Above the list of apps, choose **Add**.
6. In the **Add App** blade, choose **App Information**.
7. In the **Edit App** blade, configure the following information. Once you are done, click **Add**. Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:
	- **App Name** - Enter the name of the app as it will be displayed in the company portal. Make sure all app names that you use are unique. If the same app name exists twice, only one of the apps will be displayed to users in the company portal.
	- **App Description** - Enter a description for the app. This will be displayed to users in the company portal.
	- **Publisher** - Enter the name of the publisher of the app.
	- **App store URL** - Enter the app store URL of the app you want to create.
	- **Minimum Operating System** - From the list, choose the minimum operating system version on which the app can be installed. If you assign the app to a device with an earlier operating system, it will not be installed.
	- **Category (optional)** - Select one or more of the built-in app categories, or a category you created. This will make it easier for users to find the app when they browse the company portal.
	- **Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.
	- **Information URL** - Optionally, enter the URL of a website that contains information about this app. The URL will be displayed to users in the company portal.
	- **Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app. The URL will be displayed to users in the company portal.
	- **Developer** - Optionally, enter the name of the app developer.
	- **Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.
	- **Notes** - Enter any notes you would like to associate with this app.
	- **Upload Icon** - Upload an icon that will be associated with the app. This is the icon that will be displayed with the app when users browse the company portal.
8. When you are done, on the **Add App** blade, choose **Save**.

The app you have created will be displayed in the apps list where you can assign it to the groups you choose. For help, see [How to assign apps to groups](apps-deploy.md).

## Manually assign Windows 10 Company Portal app
End users can install the Company Portal app from the Microsoft Store to manage devices and install apps. If, however, your business needs require that you assign the Company Portal app, you can manually assign the Windows 10 Company Portal app directly from Intune, even if you haven’t integrated Intune with the Microsoft Store for Business.

 > [!NOTE]
 > This option will require assigning manual updates each time an app update is released.

1. Log in to your account in the [Microsoft Store for Business](https://www.microsoft.com/business-store) and acquire the **offline license** version of the Company Portal app.  
2. Once the app has been acquired, select the app in the **Inventory** page.  
3. Select **Windows 10 all devices** as the **Platform**, then the appropriate **Architecture** and download. An app license file is not needed for this app.
![Image of Windows 10 all devices and Architecture X86 Package details for Download](./media/Win10CP-all-devices.png)
4. Download all the packages under “Required Frameworks”. This must be done for x86, x64 and ARM architectures – resulting in a total of 9 packages as shown below.

![Image of dependency files to Download ](./media/Win10CP-dependent-files.png)
5. Before uploading the Company Portal app to Intune, create a folder (e.g., C:&#92;Company Portal) with the packages structured in the following way:
  1. Place the Company Portal package into C:\Company Portal. Create a Dependencies subfolder in this location as well.  
  ![Image of Dependencies folder saved with APPXBUN file](./media/Win10CP-Dependencies-save.png)
  2. Place the nine dependencies packages in the Dependencies folder.  
  If the dependencies are not placed in this format, Intune will not be able to recognize and upload them during the package upload, causing the upload to fail with the following error.  
  ![The Windows app dependency for this software installer was not found in the application folder. You can continue to create and assign this application but it will not run until the missing Windows app dependency is provided.](./media/Win10CP-error-message.png)
6. Return to Intune, then upload the Company Portal app as a new app. Assign it as a required app to the desired set of target users.  

See [Deploying an appxbundle with dependencies via Microsoft Intune MDM](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) for more information about how Intune handles dependencies for Universal apps.  

### How do I update the Company Portal on my users’ devices if they have already installed the older apps from the store?
If your users have already installed the Windows 8.1 or Windows Phone 8.1 Company Portal apps from the Store, then they should be automatically updated to the new version with no action required from you or your user. If the update does not happen, ask your users to check that they have enabled autoupdates for Store apps on their devices.   

### How do I upgrade my sideloaded Windows 8.1 Company Portal app to the Windows 10 Company Portal app?
Our recommended migration path is to delete the assignment for the Windows 8.1 Company Portal app by setting the assignment action to “Uninstall”. Once this is done, the Windows 10 Company Portal app can be assigned using any of the above options.  

If you need to sideload the app and assigned the Windows 8.1 Company Portal without signing it with the Symantec Certificate, follow the steps in the Assign directly via Intune section above to complete the upgrade.

If you need to sideload the app and you signed and assigned the Windows 8.1 Company Portal with the Symantec code-signing certificate, follow the steps in the section below.  

### How do I upgrade my signed and sideloaded Windows Phone 8.1 Company Portal app or Windows 8.1 Company Portal app to the Windows 10 Company Portal app?
Our recommended migration path is to delete the existing assignment for the Windows Phone 8.1 Company Portal app or the Windows 8.1 Company Portal app by setting the assignment action to “Uninstall”. Once this is done, the Windows 10 Company Portal app can be assigned normally.  

Otherwise, the Windows 10 Company Portal app needs to be appropriately updated and signed to ensure that the upgrade path is respected.  

If the Windows 10 Company Portal app is signed and assigned in this way, you will need to repeat this process for each new app update when it is available in the store. The app will not automatically update when the store is updated.  

Here’s how you sign and assign the app in this way:

1. Download the Microsoft Intune Windows 10 Company Portal App Signing Script from [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript).  This script requires the Windows SDK for Windows 10 to be installed on the host computer. To download the Windows SDK for Windows 10, visit [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296).
2. Download the Windows 10 Company Portal app from the Microsoft Store for Business, as detailed above.  
3. Run the script with the input parameters detailed in the script header to sign the Windows 10 Company Portal app (extracted below). Dependencies do not need to be passed into the script. These are only required when the app is being uploaded to the Intune Admin Console.

|Parameter | Description|
| ------------- | ------------- |
|InputWin10AppxBundle |The path to where the source appxbundle file is located |
|OutputWin10AppxBundle |The output path for the signed appxbundle file.  Win81Appx The path to where the Windows 8.1 or Windows Phone 8.1 Company Portal (.APPX) file is located.|
|PfxFilePath |The path to Symantec Enterprise Mobile Code Signing Certificate (.PFX) file. |
|PfxPassword| The password of the Symantec Enterprise Mobile Code Signing Certificate. |
|PublisherId |The Publisher ID of the enterprise. If absent, the 'Subject' field of the Symantec Enterprise Mobile Code Signing Certificate is used.|
|SdkPath | The path to the root folder of the Windows SDK for Windows 10. This argument is optional and defaults to ${env:ProgramFiles(x86)}\Windows Kits\10|
The script will output the signed version of the Windows 10 Company Portal app when it has finished running. You can then assign the signed version of the app as an LOB app via Intune, which will upgrade the currently assigned versions to this new app.  
