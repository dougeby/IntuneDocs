---
# required metadata

title: Sideload apps for Windows and Windows Phone 
description: Learn how to sign line of business apps so you can use Intune to deploy them.
keywords:
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 06/07/2017
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: e44f1756-52e1-4ed5-bf7d-0e80363a8674

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer:
#ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---
# Sign line-of-business apps so they can be deployed to Windows devices with Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

As an Intune administrator, you can deploy line-of-business (LOB) apps to Windows and Windows 10 Mobile devices, including the Company Portal app. To deploy .appx or .xap apps to Windows 10 and Windows 10 mobile devices, or to deploy any LOB app to Windows 8.1 or Windows Phone 8.1 devices, you must get a **Symantec Enterprise Mobile Code Signing Certificate**. Only the Symantec certificate is trusted for these apps for the respective Windows devices. You can use your own certificate authority for Windows 10 apps and "universal" apps. This certificate is required in order to:

-   Sign the Company Portal app for deployment to Windows PCs, Windows 10 Mobile devices, and Windows Phone devices

-   Sign company line-of-business apps so Intune can deploy them to Windows devices

The steps below will help you get the required certificate and sign the apps. You will need to register as a Microsoft developer, and then purchase a Symantec certificate.


1. **Register as a Microsoft developer**<br>
   [Register as a Microsoft developer](http://go.microsoft.com/fwlink/?LinkId=268442) using the corporate account information you used when logging in to purchase your company account. This request will need to be authorized by a company officer before you receive a code-signing certificate.

2. **Get a company Symantec certificate**<br>
  Purchase a certificate from the [Symantec website](http://go.microsoft.com/fwlink/?LinkId=268441) using your Symantec ID. After you purchase the certificate, the corporate approver whom you designated when you registered as a Microsoft developer will receive an email asking for approval of the certificate request. For more information about the Symantec certificate requirement, see the [Why Windows Phone requires a Symantec certificate?](https://technet.microsoft.com/library/dn764959.aspx#BKMK_Symantec) Windows device enrollment FAQ.

3.  **Import certificates**<br>
    Once the request has been approved, you will receive an email containing instructions for importing certificates. Follow the instructions in the email to import the certificates.

4.  **Verify certificates imported**<br>
    To verify that the certificates have been imported correctly, go to the **Certificates** snap-in, right-click **Certificates**, and select **Find Certificates**. In the **Contains** field, enter “Symantec”, and click **Find Now**. The certificates you imported should appear in the results.

    ![Find the Symantec certificate](./media/wit.gif)

5. **Export a signing certificate**<br>
    Having verified that the certificates are present, you can export the .pfx file to sign the company portal. Select the Symantec certificate with **Intended purpose** “code-signing.” Right-click the code-signing certificate and select **Export**.

    ![Export the signing certificate](./media/wit-walk-cert2.gif)

    In the **Certificate Export Wizard**, select **Yes, export the private key** and then click **Next**. **Select Personal Information Exchange –PKCS #12 (.PFX)** and check **Include all the certificates in the certification path if possible**. Complete the wizard. For more information, see [How to Export a Certificate with the Private Key](http://go.microsoft.com/fwlink/?LinkID=203031).

6.  **Upload the app to Intune**<br>
    Upload the signed app file and your code-signing certificate to make the app available to your end users.

    1.  In the Azure portal, click **Administration** &gt; **Windows Phone**.

    2.  Click the **Upload Signed App File** and sign in with your Intune Administrator ID.

    3.  Add the certificate (.pfx) file that you exported to **Code-signing certificate** and create a password for the certificate.

    4.  Complete the wizard.

## Example: Download, sign, and deploy the Company Portal app for Windows devices

You can deploy the Company Portal app to Windows devices, including Windows Phone and Windows 10 Mobile devices, with Intune instead of installing from the Microsoft Store. You must download the Company Portal app and sign it with your certificate.  This is only necessary if your users won't use the Company Store and you want to deploy the Company Portal to Windows Phone 8.1 devices.


1.  **Download the Company Portal**

    To deploy the Company Portal app using Intune, you can download the [Microsoft Intune Company Portal App for Windows Phone 8.1](http://go.microsoft.com/fwlink/?LinkId=615799) from the Download Center and run the self-extracting (.exe) file. This file contains two files:

    -   CompanyPortal.appx– The Company Portal installation app for Windows Phone 8.1

    -   WinPhoneCompanyPortal.ps1 – A PowerShell script you can use to sign the Company Portal app file so it can be deployed to Windows Phone 8.1 devices

    Alternatively, you can download the Windows Phone 8.1 Company Portal (offline licensed package) or the Windows 10 Company Portal (offline licensed package) from the [Microsoft Store for Business](http://businessstore.microsoft.com/). The Company Portal app will need to be acquired with an offline license and the appropriate package downloaded for offline use. Windows 8 and Windows Phone 8 platform listings in the selection refer to their 8.1 counterparts. For details about how to do this with Intune, see [Manage apps you purchased from the Microsoft Store for Business](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune).

2.  **Download the Windows Phone SDK**
    Download the Windows Phone SDK 8.0](http://go.microsoft.com/fwlink/?LinkId=615570) and install the SDK to your computer. This SDK is needed to generate an application enrollment token.

3.  **Generate an AETX file**
    Generate an application enrollment token (.aetx) file from the Symantec PFX file using AETGenerator.exe, part of Windows Phone SDK 8.0. For instructions on how to create an AETX file, see [How to generate an application enrollment token for Windows Phone](https://msdn.microsoft.com/library/windows/apps/jj735576.aspx)

4.  **Download the Windows SDK for Windows 8.1**
    Download and install the [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=613525) (http://go.microsoft.com/fwlink/?LinkId=613525). Note that the PowerShell script included with the Company Portal app uses the default install location, `${env:ProgramFiles(x86)}\Windows Kits\8.1`. If you install elsewhere, you must include the location in a cmdlet parameter.

5.  **Code-sign the app using PowerShell**
    As an administrator, open **Windows PowerShell** on the host computer installed with the Windows SDK, the Symantec Enterprise Mobile Code Signing Certificate, navigate to the Sign-WinPhoneCompanyPortal.ps1 file and run the script.

    **Example 1**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -AetxPath 'C:\signing\cert.aetx'
    ```
    This example signs the CompanyPortal.appx at C:\temp\ and produces the CompanyPortalEnterpriseSigned.appx. It would use PFX password 1234 and read the publisher ID from the PFX file. It reads the enterprise ID from the cert.aetx file as well.

    **Example 2**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -PublisherId 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1' -EnterpriseId 1000000001
    ```
    This example signs the CompanyPortal.appx at C:\temp\ and produces the CompanyPortalEnterpriseSigned.appx. It would use PFX password 1234 and use the publisher ID specified.

    **Parameters:**

    -   `-InputAppx` – The local path to the CompanyPortal.appx file in single quotes. For example 'C:\temp\CompanyPortal.appx'

    -   `-OutputAppx` – The local path and file name for the signed Company Portal app in single quotes. For example, 'C:\temp\CompanyPortalEnterpriseSigned.appx'

    -   `-PfxFilePath` – The local path and file name for the exported PFX file of the Symantec certificate. For example, 'C:\signing\cert.pfx'

    -   `-PfxPassword` – The password used to sign the PFX file in single quotes. For example '1234'

    -   `-AetxPath` – The local path to the .aetx file which is used for reading the enterprise ID if the 'EnterpriseId' argument is not defined. Either this argument or EnterpriseId must be provided. For example 'C:\signing\cert.aetx'

    -   `-PublisherId` - The Publisher ID of the enterprise. If absent, the 'Subject' field of the Symantec Enterprise Mobile Code Signing Certificate is used. For example, 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1'

    -   `-SdkPath` - The path to the root folder of the Windows SDK for Windows 8.1. This argument is optional and defaults to ${env:ProgramFiles(x86)}\Windows Kits\8.1.

    -   `-EnterpriseId` - The enterprise ID. Either this argument or 'AetxPath' must be provided. If this argument is not provided, the enterprise ID is read from the AETX file. For example, 1000000001

6.  Deploy the Windows Phone 8.1 Company Portal (SSP.appx) app. For guidance, see [How to add Windows Phone line-of-business (LOB) apps](lob-apps-windows-phone.md) ([classic portal](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune)).

## How to renew the Symantec enterprise code-signing certificate

The Symantec certificate used to deploy Windows and Windows Phone mobile apps must be renewed periodically.

1.  Look for a renewal email sent from Symantec approximately 14 days prior to certificate expiration. This email contains directions from Symantec about renewing your enterprise certificate.

    For additional information about Symantec certificates, visit [www.symantec.com](http://www.symantec.com) or call 1-877-438-8776 or 1-650-426-3400.

2.  Go to the website (example: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) and login with the Symantec Publisher ID and email addressed associated with the certificate. Remember to use the same machine for starting the renewal that you’ll use to download the certificate.

3.  Once the renewal is approved and paid for, download the certificate.

### How to install the updated certificate for line-of-business (LOB) apps

1.  Sign the latest version of your line-of-business app.

2.  Open the Azure portal and go to **Admin** &gt; **Mobile Device Management** &gt; **Windows Phone** and click **Upload Signed App**.

3.  Upload the newly signed Company Portal. You’ll need the newly signed SSP.xap and the new .PFX file you received from Symantec or the Application enrollment token that was created with this new .PFX file.

4.  When the upload is complete, remove the old Company Portal version in the **Software**  workspace.

5.  Sign all new and any updated enterprise line-of-business apps using the new certificate. Existing applications do not need to be resigned and redeployed.

## Manually deploy Windows 10 Company Portal app
You can manually deploy the Windows 10 Company Portal app directly from Intune, even if you haven’t integrated Intune with the Microsoft Store for Business.

 > [!NOTE]
 > This option will require deploying manual updates each time an app update is released.

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
  ![The Windows app dependency for this software installer was not found in the application folder. You can continue to create and deploy this application but it will not run until the missing Windows app dependency is provided.](./media/Win10CP-error-message.png)
6. Return to Intune, then upload the Company Portal app as a new app. Deploy it as a required app to the desired set of target users.  

See [Deploying an appxbundle with dependencies via Microsoft Intune MDM](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) for more information about how Intune handles dependencies for Universal apps.  

### How do I update the Company Portal on my users’ devices if they have already installed the older apps from the store?
If your users have already installed the Windows 8.1 or Windows Phone 8.1 Company Portal apps from the Store, then they should be automatically updated to the new version with no action required from you or your user. If the update does not happen, ask your users to check that they have enabled autoupdates for Store apps on their devices.   

### How do I upgrade my sideloaded Windows 8.1 Company Portal app to the Windows 10 Company Portal app?
Our recommended migration path is to delete the deployment for the Windows 8.1 Company Portal app by setting the deployment action to “Uninstall”. Once this is done, the Windows 10 Company Portal app can be deployed using any of the above options.  

If you need to sideload the app and deployed the Windows 8.1 Company Portal without signing it with the Symantec Certificate, follow the steps in the Deploy directly via Intune section above to complete the upgrade.

If you need to sideload the app and you signed and deployed the Windows 8.1 Company Portal with the Symantec code-signing certificate, follow the steps in the section below.  

### How do I upgrade my signed and sideloaded Windows Phone 8.1 Company Portal app or Windows 8.1 Company Portal app to the Windows 10 Company Portal app?
Our recommended migration path is to delete the existing deployment for the Windows Phone 8.1 Company Portal app or the Windows 8.1 Company Portal app by setting the deployment action to “Uninstall”. Once this is done, the Windows 10 Company Portal app can be deployed normally.  

Otherwise, the Windows 10 Company Portal app needs to be appropriately updated and signed to ensure that the upgrade path is respected.  

If the Windows 10 Company Portal app is signed and deployed in this way, you will need to repeat this process for each new app update when it is available in the store. The app will not automatically update when the store is updated.  

Here’s how you sign and deploy the app in this way:

1. Download the Microsoft Intune Windows 10 Company Portal App Signing Script from [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript).  This script requires the Windows SDK for Windows 10 to be installed on the host computer. To download the Windows SDK for Windows 10, visit [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296).
2. Download the Windows 10 Company Portal app from the Microsoft Store for Business, as detailed above.  
3. Run the script with the input parameters detailed in the script header to sign the Windows 10 Company Portal app (extracted below). Dependencies do not need to be passed into the script. These are only required when the app is being uploaded to the Intune Admin Console.

|Parameter | Description|
| ------------- | ------------- |
|InputWin10AppxBundle |The path to where the source appxbundle file is located. |
|OutputWin10AppxBundle |The output path for the signed appxbundle file. |
|Win81Appx | The path to where the Windows 8.1 or Windows Phone 8.1 Company Portal (.APPX) file is located.|
|PfxFilePath |The path to Symantec Enterprise Mobile Code Signing Certificate (.PFX) file. |
|PfxPassword| The password of the Symantec Enterprise Mobile Code Signing Certificate. |
|PublisherId |The Publisher ID of the enterprise. If absent, the 'Subject' field of the Symantec Enterprise Mobile Code Signing Certificate is used.|
|SdkPath | The path to the root folder of the Windows SDK for Windows 10. This argument is optional and defaults to ${env:ProgramFiles(x86)}\Windows Kits\10|
The script will output the signed version of the Windows 10 Company Portal app when it has finished running. You can then deploy the signed version of the app as an LOB app via Intune, which will upgrade the currently deployed versions to this new app.  
