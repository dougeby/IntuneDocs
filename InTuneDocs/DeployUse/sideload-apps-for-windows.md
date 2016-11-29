---
# required metadata

title: Sideload apps for Windows and Windows Phone | Microsoft Intune
description: Learn how to sign line of business apps so you can use Intune to deploy them.
keywords:
author: robstackmsft
manager: angrobe
ms.date: 11/28/2016
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
#ms.custom:

---
# Sign line-of-business apps so they can be deployed to Windows devices with Intune

As an Intune administrator, you can deploy line-of-business (LOB) apps to Windows and Windows 10 Mobile devices, including the Company Portal app. To deploy .appx or .xap apps to Windows 10 and Windows 10 mobile devices, or to deploy any LOB app to Windows 8.1 or Windows Phone 8.1 devices, you must get a **Symantec Enterprise Mobile Code Signing Certificate**. Only the Symantec certificate is trusted for these apps for the respective Windows devices. You can use your own certificate authority for Windows 10 apps and "universal" apps. This certificate is required in order to:

-   Sign the Company Portal app for deployment to Windows PCs, Windows 10 Mobile devices, and Windows Phone devices

-   Sign company line-of-business apps so Intune can deploy them to Windows devices

The steps below will help you get the required certificate and sign the apps. You will need a Windows Phone Dev Center account and then you will need to purchase a Symantec certificate.


1. **Join the Windows Phone Dev Center**<br>
   Join the [Windows Phone Dev Center](http://go.microsoft.com/fwlink/?LinkId=268442) using corporate account information when logging in to purchase your company account. This request will need to be authorized by a company officer before you receive a code-signing certificate.

2. **Get a company Symantec certificate**<br>
  Purchase a certificate from the [Symantec website](http://go.microsoft.com/fwlink/?LinkId=268441) using your Symantec ID. After you purchase the certificate, the corporate approver whom you designated in your Windows Phone Dev Center account will receive an email asking for approval of the certificate request. For more information about the Symantec certificate requirement, see the [Why Windows Phone requires a Symantec certificate?](https://technet.microsoft.com/en-us/library/dn764959.aspx#BKMK_Symantec) Windows device enrollment FAQ.

3.  **Import certificates**<br>
    Once the request has been approved, you will receive an email containing instructions for importing certificates. Follow the instructions in the email to import the certificates.

4.  **Verify certificates imported**<br>
    To verify that the certificates have been imported correctly, go to the **Certificates** snap-in, right-click **Certificates**, and select **Find Certificates**. In the **Contains** field, enter “Symantec”, and click **Find Now**. The certificates you imported should appear in the results.

    ![Find the Symantec certificate](../media/wit.gif)

5. **Export a signing certificate**<br>
    Having verified that the certificates are present, you can export the .pfx file to sign the company portal. Select the Symantec certificate with **Intended purpose** “code-signing.” Right-click the code-signing certificate and select **Export**.

    ![Export the signing certificate](../media/wit-walk-cert2.gif)

    In the **Certificate Export Wizard**, select **Yes, export the private key** and then click **Next**. **Select Personal Information Exchange –PKCS #12 (.PFX)** and check **Include all the certificates in the certification path if possible**. Complete the wizard. For more information, see [How to Export a Certificate with the Private Key](http://go.microsoft.com/fwlink/?LinkID=203031).

6.  **Upload the app to Intune**<br>
    Upload the signed app file and your code-signing certificate to make the app available to your end users.

    1.  In the [Intune administration console](http://manage.microsoft.com) click **Administration** &gt; **Windows Phone**.

    2.  Click the **Upload Signed App File** and sign in with your Intune Administrator ID.

    3.  Add the certificate (.pfx) file that you exported to **Code-signing certificate** and create a password for the certificate.

    4.  Complete the wizard.

## Example: Download, sign, and deploy the Company Portal app for Windows devices

You can deploy the Company Portal app to Windows devices, including Windows Phone and Windows 10 Mobile devices, with Intune instead of installing from the Windows Store. You must download the Company Portal app and sign it with your certificate.  This is only necessary if your users won't use the Company Store and you want to deploy the Company Portal to Windows Phone 8.1 devices.


1.  **Download the Company Portal**

    To deploy the Company Portal app using Intune, you can download the [Microsoft Intune Company Portal App for Windows Phone 8.1](http://go.microsoft.com/fwlink/?LinkId=615799) from the Download Center and run the self-extracting (.exe) file. This file contains two files:

    -   CompanyPortal.appx– The Company Portal installation app for Windows Phone 8.1

    -   WinPhoneCompanyPortal.ps1 – A PowerShell script you can use to sign the Company Portal app file so it can be deployed to Windows Phone 8.1 devices

    Alternatively, you can download the Windows Phone 8.1 Company Portal (offline licensed package) or the Windows 10 Company Portal (offline licensed package) from the [Windows Store for Business](http://businessstore.microsoft.com/). The Company Portal app will need to be acquired with an offline license and the appropriate package downloaded for offline use. Windows 8 and Windows Phone 8 platform listings in the selection refer to their 8.1 counterparts. For details about how to do this with Intune, see [Manage apps you purchased from the Windows Store for Business](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md).

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

6.  Deploy the Windows Phone 8.1 Company Portal (SSP.appx) app. For guidance, see [Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md).

## How to renew the Symantec enterprise code-signing certificate

The Symantec certificate used to deploy Windows and Windows Phone mobile apps must be renewed periodically.

1.  Look for a renewal email sent from Symantec approximately 14 days prior to certificate expiration. This email contains directions from Symantec about renewing your enterprise certificate.

    For additional information about Symantec certificates, visit [www.symantec.com](http://www.symantec.com) or call 1-877-438-8776 or 1-650-426-3400.

2.  Go to the website (example: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) and login with the Symantec Publisher ID and email addressed associated with the certificate. Remember to use the same machine for starting the renewal that you’ll use to download the certificate.

3.  Once the renewal is approved and paid for, download the certificate.

### How to install the updated certificate for line-of-business (LOB) apps

1.  Sign the latest version of your line-of-business app.

2.  Open your [Intune Administration Console](https://admin.manage.microsoft.com) (https://admin.manage.microsoft.com) and go to **Admin** &gt; **Mobile Device Management** &gt; **Windows Phone** and click **Upload Signed App**.

3.  Upload the newly signed Company Portal. You’ll need the newly signed SSP.xap and the new .PFX file you received from Symantec or the Application enrollment token that was created with this new .PFX file.

4.  When the upload is complete, remove the old Company Portal version in the **Software**  workspace.

5.  Sign all new and any updated enterprise line-of-business apps using the new certificate. Existing applications do not need to be resigned and redeployed.
