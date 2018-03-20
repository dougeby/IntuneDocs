---
# required metadata

title: Manually add the Windows 10 Company Portal app
titleSuffix: Microsoft Intune
description: Learn how to manually add the Windows 10 Company Portal app.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bfe1a2d3-f611-4dbb-adef-c0dff4d7b810

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Manually add the Windows 10 Company Portal app using Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

End users can install the Company Portal app from the Microsoft Store to manage devices and install apps. If, however, your business needs require that you assign the Company Portal app, you can manually assign the Windows 10 Company Portal app directly from Intune, even if you haven’t integrated Intune with the Microsoft Store for Business.

 > [!NOTE]
 > This option will require assigning manual updates each time an app update is released.

## Configure settings to show offline apps
1. Go to the [Microsoft Store for Business](https://www.microsoft.com/business-store) and make sure you are signed-in with your admin account.
2. Select the **Manage** tab near the top of the window.
3. Select **Settings** on the left navigation column.
4. Set **Show offline apps** in the **Shopping experience** section to **On**. This will show offline licensed apps in the Microsoft Store for Business.

## Download the offline Company Portal app
1. Search and select the **Company Portal** app.
2. Set the **License type** to **Offline**.
3. Click **Get the app** to acquire and add the offline Company Portal app to your inventory.
4. Click **Manage** on the **Company portal** app page.
5. Select **Windows 10 all devices** as the **Platform**, then select the appropriate **Minimum version**, **Architecture**, and Download app metadata** values. 
6. Click **Download** to save the file to your local machine.

    ![Image of Windows 10 all devices and Architecture X86 package details for Download](./media/Win10CP-all-devices.png)

7. Download all the packages under “Required Frameworks”. This must be done for x86, x64 and ARM architectures – resulting in a total of 12 packages.
8. Before uploading the Company Portal app to Intune, create a folder (for example: C:&#92;Company Portal) with the packages structured in the following way:
  - Place the Company Portal package into C:\Company Portal. Create a Dependencies subfolder in this location as well.  

    ![Image of Dependencies folder saved with APPXBUN file](./media/Win10CP-Dependencies-save.png)

  - Place the dependency packages in the *Dependencies* folder. 

     > [!NOTE]
     > If the dependencies are not placed in the correct format, Intune will not be able to recognize and upload the files during the package upload, causing the upload to fail and display and error.

9. Return to Microsoft Intune in the Azure portal.
10. Upload the Company Portal app as a new app. Assign it as a required app to the desired set of target users.  

See [Deploying an appxbundle with dependencies via Microsoft Intune MDM](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) for more information about how Intune handles dependencies for Universal apps.  

## How do I update the Company Portal on my users’ devices if they have already installed the older apps from the store?
If your users have already installed the Windows 8.1 or Windows Phone 8.1 Company Portal apps from the Store, then they should be automatically updated to the new version with no action required from you or your user. If the update does not happen, ask your users to check that they have enabled autoupdates for Store apps on their devices.   

## How do I upgrade my sideloaded Windows 8.1 Company Portal app to the Windows 10 Company Portal app?
Our recommended migration path is to delete the assignment for the Windows 8.1 Company Portal app by setting the assignment action to "Uninstall". Once this setting made, the Windows 10 Company Portal app can be assigned using any of the above options.  

If you need to sideload the app and assigned the Windows 8.1 Company Portal without signing it with the Symantec Certificate, follow the steps in the Assign directly via Intune section above to complete the upgrade.

If you need to sideload the app and you signed and assigned the Windows 8.1 Company Portal with the Symantec code-signing certificate, follow the steps in the section below.  

## How do I upgrade my signed and sideloaded Windows Phone 8.1 Company Portal app or Windows 8.1 Company Portal app to the Windows 10 Company Portal app?
Our recommended migration path is to delete the existing assignment for the Windows Phone 8.1 Company Portal app or the Windows 8.1 Company Portal app by setting the assignment action to “Uninstall”. Once  setting is made, the Windows 10 Company Portal app can be assigned normally.  

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

## Next steps

- [How to assign apps to groups](apps-deploy.md)

