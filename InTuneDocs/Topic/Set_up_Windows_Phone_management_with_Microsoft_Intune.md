---
title: Set up Windows Phone management with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 61e9b6c3-8795-49b0-8ab2-a9a05ee3ea1f
author: NathBarn
---
# Set up Windows Phone management with Microsoft Intune
Before you can manage Windows Phone mobile devices with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], you have to set up management requirements. Creating a DNS CNAME helps users connect to the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] company portal. Windows Phone 8.0 requires a Symantec certificate to establish an encrypted IP connection between devices and [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. Depending upon how users access the company portal, Windows Phone 8.1 might also. A certificate is also required to sign line-of-business apps.

-   **Windows Phone 8.1** - Requires a certificate only if:

    -   Users won't download the company portal from the Store

    -   You'll deploy  line-of-business (AKA "sideloaded") apps

-   **Windows Phone 8** - Required

![](../Image/WPCertReqs.png)

## Prepare to manage Windows Phone mobile devices with Intune
Setup requirements for Window Phone mobile device management depend upon how you'll manage devices.  Setting two CNAMEs in your company's DNS registration makes enrollment easier for uses. If your users will download the Company Portal app from the Store, then once you've configured DNS settings you just need to set up the Company Portal and inform users how to enroll.  For Windows Phone 8.0, or Windows Phone 8.1 where you'll deploy the Company Portal, you'll need a Symntec certificate to code-sign the app.

#### Set up Windows Phone enrollment with Intune

1.  **Set up Intune**
    If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](https://technet.microsoft.com/library/mt346013.aspx) as **Microsoft Intune** and setting up MDM.

2.  **Set a DNS alias for the enrollment server address** (optional)

    A DNS alias (CNAME record type) makes it easier users to enroll their devices by automatically populating the server name during enrollment.

    ###### Verify and create DNS CNAME

    1.  In the [Intune administration console](http://manage.microsoft.com), click **Administration** &gt; **Mobile Device Management** &gt; **Windows Phone**.

    2.  Type the URL of the verified domain of the company website in the **Specify a verified domain name** box and then click **Test Auto-Detection**.

    3.  Create CNAME resource records for your company’s domain. The CNAME resource records must contain the following information:

        |TYPE|Host Hame|Points to|TTL|
        |--------|-------------|-------------|-------|
        |CNAME|enterpriseenrollment.company_domain.com|enterpriseenrollment.manage.microsoft.com |1 Hour|
        |CNAME|enterpriseregistration.company_domain.com|enterpriseregistration.windows.net|1 Hour|
        For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to manage.microsoft.com. If there is more than one verified domain, create a CNAME record for each domain.

        -   `manage.microsoft.com` – Supports a redirect to the Intune service with domain recognition from the email’s domain name

        -   `enterpriseregistration.windows.net` – Supports workplace join for mobile devices. It also supports conditional access for Windows 8.1

    ![](../Image/Windows_Phone_Enrollment.bmp)

3.  **Certificate management to support app signing**
    [Required for Windows Phone 8.0 and Windows Phone 8.1 that won’t access the Windows Phone Store and/or need line-of-business apps.]

    To support the Company Portal app for Windows Phone 8.0 and to deploy company apps to Windows Phone 8.1 you must get a **Symantec Enterprise Mobile Code Signing Certificate**. You cannot use a certificate issued by your own certification authority because only the Symantec certificate is trusted by Windows Phone devices. This certificate is required in order to:

    -   Sign the Company Portal app for deployment to [!INCLUDE[winphone8_client_1](../Token/winphone8_client_1_md.md)] for enrollment and phone management

    -   Sign company line-of-business apps so [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] can deploy them to Windows Phones

    For more information, see [Frequently Asked Questions about Windows Phone Mobile Device Management](https://technet.microsoft.com/en-us/library/dn764959.aspx#BKMK_FAQ).

    The steps below will help you get the required certificates and sign the company portal app. You will need a Windows Phone Dev Center account and then you will need to purchase a Symantec certificate.

    ##### <a name="BKMK_CodeSign"></a>To get a certificate and code-sign the Company Portal

    1.  **Join the Windows Phone Dev Center**
        Join the [Windows Phone Dev Center](http://go.microsoft.com/fwlink/?LinkId=268442) using corporate account information when logging in to purchase your company account. This request will need to be authorized by a company officer before you receive a code-signing certificate.

    2.  **Get a company Symantec certificate**
        Purchase a certificate from the [Symantec website](http://go.microsoft.com/fwlink/?LinkId=268441) using your Symantec ID. After you purchase the certificate, the corporate approver whom you designated in your Windows Phone Dev Center account will receive an email asking for approval of the certificate request. For more information about the Symantec certificate requirement, see the [Why Windows Phone requires a Symantec certificate?](https://technet.microsoft.com/en-us/library/dn764959.aspx#BKMK_Symantec) Windows device enrollment FAQ.

    3.  **Import certificates**
        Once the request has been approved, you will receive an email containing instructions for importing certificates. Follow the instructions in the email to import the certificates.

    4.  **Verify certificates imported**
        To verify that the certificates have been imported correctly, go to the **Certificates** snap-in, right-click **Certificates**, and select **Find Certificates**. In the **Contains** field, enter “Symantec”, and click **Find Now**. The certificates you imported should appear in the results.

        ![](../Image/wit_.gif)

    5.  **Export a signing certificate**
        Having verified that the certificates are present, you can export the .pfx file to sign the company portal. Select the Symantec certificate with **Intended purpose** “code-signing.” Right-click the code-signing certificate and select **Export**.

        ![](../Image/wit_walk_cert2.gif)

        In the **Certificate Export Wizard**, select **Yes, export the private key** and then click **Next**. **Select Personal Information Exchange –PKCS #12 (.PFX)** and check **Include all the certificates in the certification path if possible**. Complete the wizard. For more information, see [How to Export a Certificate with the Private Key](http://go.microsoft.com/fwlink/?LinkID=203031).

    6.  **Download and sign the Company Portal app**

        Support for Windows Phone enrollment requires the Windows Phone 8.0 Company Portal app be signed and uploaded to Intune.

        ###### Windows Phone 8.0: Download and sign the Company Portal app

        1.  **Download the Company Portal**
            Download the [Intune Company Portal for Windows Phone](http://go.microsoft.com/fwlink/?LinkId=268440) from the Download Center. The default installation location is `C:\Program Files (x86)\Microsoft Corporation\Windows Intune Company Portal for Windows Phone`.

        2.  **Download the Windows Phone 8.0 SDK**
            Download the [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=615570).

        3.  **Code-sign the Company Portal app**
            Use the XAPSignTool app downloaded with the SDK to sign the company portal with the .pfx file you created from the Symantec certificate. For more information, see [How to sign a company app by using XapSignTool](http://go.microsoft.com/fwlink/?LinkID=280195).

    7.  **Upload the Company Portal app to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]**
        Upload the signed Company Portal app file and your code-signing certificate to make the app available to your end users.

        1.  In the [Intune administration console](http://manage.microsoft.com) click **Administration** &gt; **Windows Phone**.

        2.  Click the **Upload Signed App File** and sign in with your [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] Administrator ID.

        3.  On the **Software setup** page for **Specify the location of the software setup files**, browse to the code-signed Company Portal app location (.xap for Windows Phone 8.0 or .appx for Windows Phone 8.1).

            If you are evaluating [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] and uploading a code-signed app file in a trial [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] account, uncheck the **Use the Company Portal App file signed by the sample Symantec code-signed certificate** checkbox.

        4.  Add the certificate (.pfx) file that you exported to **Code-signing certificate** and create a password for the certificate.

        5.  On the **Software description** page, complete the fields remembering that users see this information on their devices when viewing details about the app in the Company Portal.

        6.  Complete the wizard. Users who enroll a Windows Phone 8.0 device will now get the Company Portal app on their devices during enrollment. Windows Phone 8.1 users can install the Company Portal app from the store version of the Company Portal.  If Windows Phone 8.1 devices are blocked from the Windows Phone Store or you want to deploy the Company Portal app using Intune, you must download and sign the Windows Phone 8.1 Company Portal (SSP.appx) app.

4.  **Tell users how to get access to company resources with the company portal**
    Your users will need to know how to enroll their devices and what to expect once they're brought into management. [What to tell your end users about using Microsoft Intune](../Topic/What_to_tell_your_end_users_about_using_Microsoft_Intune.md)

### Deploy the Windows Phone 8.1 Company Portal app
You can deploy the Company Portal app to Windows Phone 8.1 devices with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] instead of installing from the Windows Phone Store. You must still enable Windows Phone device enrollment with the steps above using the Symantec certificate. You must then download the Windows Phone 8.1 Company Portal app and sign it with your Symantec certificate.  This is only necessary if your users won't use the Company Store and you want to deploy the Company Portal to Windows Phone 8.1 devices.

#### <a name="BKMK_WP81appx"></a>Steps to download and sign the Windows Phone 8.1 Company Portal app for deployment with Intune

1.  **Download the Company Portal**

    Download the [Microsoft Intune Company Portal App for Windows Phone 8.1](http://go.microsoft.com/fwlink/?LinkId=615799) from the Download Center and run the self-extracting (.exe) file. This file contains two files:

    -   CompanyPortal.appx– The Company Portal installation app for Windows Phone 8.1

    -   WinPhoneCompanyPortal.ps1 – A PowerShell script you can use to sign the Company Portal app file so it can be deployed to Windows Phone 8.1 devices

2.  **Download the Windows Phone SDK**
    Download the [Windows Phone SDK 8.0](http://go.microsoft.com/fwlink/?LinkId=615570) (http://go.microsoft.com/fwlink/?LinkId=268439) and install the SDK to your computer. This SDK is needed to generate an application enrollment token.

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

6.  Deploy the Windows Phone 8.1 Company Portal (SSP.appx) app.

    > [!IMPORTANT]
    > The ssp.xap and the Company Portal from the store can both be installed at the same time, which can be confusing for users. To have all users using the ssp.xap, create a blocked app for the store version of the Company Portal. To have all Windows Phone 8.1 devices to use only the store version of the Company Portal, you have three choices:
    > 
    > -   If you won’t sideload apps and don’t need to support Windows Phone 8.0, don’t upload the signed ssp.xap.
    > -   If sideloaded apps are needed, and if there are no Windows Phone 8 devices enrolling, change the automatically created ssp.xap deployment from “available” to “uninstall.”
    > -   If sideloaded apps need to be installed and Windows Phone 8.0 devices need to enroll and receive the ssp.xap, create a new software deployment of the ssp.xap and deploy it with the **uninstall** action. Windows Phone 8.0 devices don’t support forced install or uninstall of apps, so they will ignore the deployment. Windows Phone 8.1 devices support the uninstall action and will remove the ssp.xap.

## Renew your Symantec enterprise code-signing certificate for Windows devices
The Symantec certificate used to manage certain Windows and Windows Phone mobile devices must be renewed periodically. For Windows Phone 8.0 devices, a signed Company Portal app and the code-signing certificate are needed for device enrollment. Later Windows Phone devices can use the company portal app downloaded from the store. A code-signing certificate is also be required for deploying line-of-business apps.

#### How to renew the Symantec enterprise code-signing certificate

1.  Look for a renewal email sent from Symantec approximately 14 days prior to certificate expiration. This email contains directions from Symantec about renewing your enterprise certificate.

    For additional information about Symantec certificates, visit [www.symantec.com](http://www.symantec.com) or call 1-877-438-8776 or 1-650-426-3400.

2.  Go to the website (example: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) and login with the Symantec Publisher ID and email addressed associated with the certificate. Remember to use the same machine for starting the renewal that you’ll use to download the certificate.

3.  Once the renewal is approved and paid for, download the certificate.

#### How to install the updated certificate for Windows Phone 8.0

1.  Download and sign the latest Windows Phone Company Portal located here: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Open your Intune Administration Console ([https://admin.manage.microsoft.com](https://admin.manage.microsoft.com)) and go to **Admin**, **Mobile Device Management** &gt; **Windows Phone** and click **Upload Signed App**.

3.  Upload the newly signed Company Portal. You’ll need the newly signed SSP.xap and the new .PFX file you received from Symantec or the application enrollment token that was created with this new .PFX file.

4.  When the upload is complete, remove the old Company Portal version in the **Software** workspace in the Intune Management Console.

5.  Sign all enterprise line-of-business apps again using the same certificate and upload and replace existing applications.

Providing a signed SSP.xap file is currently the only way to provide the updated code signing certificate. To support signed line-of-business apps, you must sign and upload a Company Portal app even though your users will install the Company Portal app from the store.

#### How to install the updated certificate for Windows Phone 8.1 and later devices

1.  Download and sign the latest Windows Phone Company Portal from the Download Center located here: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Open your [Intune Administration Console](https://admin.manage.microsoft.com) (https://admin.manage.microsoft.com) and go to **Admin** &gt; **Mobile Device Management** &gt; **Windows Phone** and click **Upload Signed App**.

3.  Upload the newly signed Company Portal. You’ll need the newly signed SSP.xap and the new .PFX file you received from Symantec or the Application enrollment token that was created with this new .PFX file.

4.  When the upload is complete, remove the old Company Portal version in the **Software**  workspace.

5.  Sign all new and any updated enterprise line-of-business apps using the new certificate. Existing applications do not need to be resigned and redeployed.

## <a name="BKMK_FAQ"></a>Frequently asked questions about mobile device management for Microsoft Intune including management with Configuration Manager 2012

### <a name="BKMK_Symantec"></a>Why does Windows Phone require a Symantec certificate for management?
Windows Phone controls how you can install apps. Any user with a Microsoft account can install apps from the Windows Phone store, or companies can install or sideload their internally developed line of business (LOB) apps using a special process described in the Windows Phone documentation. When installing LOB apps, Windows Phones trust only one special type of certificate issued by Symantec. You cannot use any other commercially or privately generated certificate. This requirement is true for all mobile device management solutions, not just Intune.

The Symantec certificate creates an application enrollment token (AET). The AET can be installed on a device when the device enrolls for mobile device management, or it can be installed out-of-band from a secure website or from an email attachment. Administrators must sign every LOB app with the Symantec certificate, using the tools provided in the [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=268439). When users attempt to install LOB apps, the Windows Phone operating system checks the signature in the AET against the signature on the app. If the signatures match, the installation is allowed to proceed. If the AET cannot be verified, installation fails. There are several reasons the AET might not be verified:

-   The AET was never installed on the device

-   The AET has expired

-   The AET was not created using the same Symantec certificate used to sign the app

Windows Phone does not require that the AET be present during MDM enrollment, but prior to the November 2014 release, Intune required the AET and a signed ssp.xap because there was no other way to install the AET and ssp.xap except during enrollment.

### How is the AET created for Intune users?
When administrators upload the .pfx file for their Symantec certificate, Intune automatically creates the AET and deploys it to enrolled Windows Phones. It is not necessary for Intune admins to use the AET Generator tool in the Windows Phone SDK.

> [!IMPORTANT]
> Intune does not support manually creating the AET and deploying it out-of-band.

### What changes happened to reduce the requirement for a Symantec certificate?
For the November 2014 release, Intune made changes to allow for scenarios where companies do not have a Symantec certificate.

-   The Company Portal for Windows Phone 8.1 is available to install from the store, so it needn’t be signed with a Symantec certificate and validated against an AET. Instead, the app is validated as part of the store publishing process.

-   Windows Phone 8.1 devices can enroll with or without an AET on the phone. If an AET is available, it will be installed the first time the device synchronizes with Intune. If there is no AET, the device can still be managed by Intune, and users can install the Company Portal from the store and use most features of the Company Portal without a Symantec certificate to sign apps.

There are no changes to the Symantec requirement for Windows Phone 8 devices. Windows Phone 8 devices must have the signed ssp.xap and the AET present during enrollment or they will be blocked from enrolling.

### What functionality is supported if a Windows Phone 8.1 device is enrolled but there is no Symantec certificate?
If a Windows Phone 8.1 device is enrolled but there’s no Symantec certificate, you can:

-   Create policies and push them to the device

-   Configure contact information for the IT department that will shows in the Company Portal

-   Create deep links to the store and deploy them to the Company Portal

-   Create links to web pages and deploy them to the Company Portal

-   Create terms and conditions that must be accepted by users before they can use the Company Portal

The one thing you cannot do without a Symantec certificate is deploy LOB apps.

> [!IMPORTANT]
> The Intune Software Publisher does not verify that apps are signed when you upload them. If you deploy unsigned apps, they will fail when users try to install them.

### What can users do if they have the Company Portal but there is no Symantec certificate?
Windows Phone 8.1 devices don’t have to be enrolled before users install the Company Portal from the store. If the device is not enrolled, users are prompted to enroll. Touching the prompt in the Company Portal takes users directly to **Settings / Workplace** where they can enroll their devices.

Even without enrolling the device, uses can perform the following actions with the Company Portal installed from the store:

-   Accept or decline any terms and conditions configured by the admin. If users decline the terms and conditions, the Company Portal closes.

-   View the contact information for the IT department

-   View any enrolled devices including iOS, Android, and Windows devices

-   Use deep links to apps in the store

-   Use web links to open web pages

With the device enrolled, users can view the device in the **My Devices** list. Once enrolled, the device is subject to any deployed Intune policies. Devices must be enrolled to get the AET and install LOB apps. An unenrolled device trying to install an LOB app will be directed to enroll.

The only thing users cannot do if the company does not have a Symantec certificate is install LOB apps deployed by the admin.

### Our company already has a certificate and has been enrolling Windows Phone 8.1 devices. Do I have to do anything different now that the Company Portal is available in the store?
The current ssp.xap from the Download Center still works on Windows Phone 8.1 devices. You can continue to direct users to enroll and get the company portal during installation.

### What are the advantages and disadvantages of users getting the Company Portal from the store?
Advantages:

-   Users get deep links and web links, even if the Windows Phone 8.1 device isn’t enrolled

-   When Microsoft updates the Company Portal, the store app updates automatically without your downloading, signing, and redeploying the ssp.xap

-   Documentation for Windows Phone 8.1, iOS, Android, and Windows users is consistent: “Go to the store and install the Company Portal.”

-   Users see the app as it installs and get enrollment instructions when it opens

Disadvantages:

-   Users see a checkbox to install a “**company hub**” but nothing directs them to the Company Portal in the device’s app list

-   Users aren’t required to accept custom terms and conditions until they open the Company Portal

In the following circumstances, you can continue directing users to enroll and have the ssp.xap installed during enrollment:

-   If the company blocks access to the store from Windows Phones, users must get the ssp.xap installed during enrollment.

-   If users do not have Microsoft accounts configured on their Windows Phones, they will not be able to install the Company Portal from the store.

-   If the existing documentation for Windows Phone enrollment tells them to go to Settings, Workplace first, it may take a while to update the docs and direct users to the store.

### What’s the difference between the ssp.xap on the Download Center and the app in the store?

-   The Company Portal in the store does not have to be signed by a Symantec certificate to be installed

-   The Company Portal in the store presents the terms and conditions to the user but the ssp.xap on the Download Center doesn’t

-   The Company Portal in the store is an .appx instead of a .xap

### Can I get the Company Portal file and push it to my users instead of sending them to the store?
Yes. The Company Portal app can be downloaded for the following operating systems from the Download Center:

-   Windows Phone 8.1: [http://go.microsoft.com/fwlink/?LinkId=615799](http://go.microsoft.com/fwlink/?LinkId=615799)

-   Windows Phone 8.0 : [http://go.microsoft.com/fwlink/?LinkId=268440](http://go.microsoft.com/fwlink/?LinkId=268440)

-   Windows 8.1: [http://go.microsoft.com/fwlink/?LinkId=615800](http://go.microsoft.com/fwlink/?LinkId=615800)

### Can companies still use the Support Tool for Windows Intune Trial Management of Windows Phone if they don’t have a Symantec certificate, and still have users install the Company Portal from the store?
Yes. If you need to do a proof of concept that includes installation of LOB apps, the trial management tool works with the store version of the company portal. Because the AET from the Symantec certificate is no longer required to enroll Windows Phone 8.1 devices, however, companies can test app installation using deep links to apps in the store.

The Support Tool for Windows Intune Trial Management of Windows Phone is only for trial subscriptions of Intune.

> [!IMPORTANT]
> Only use the trial management tool testing. Devices enrolled with the AET from the trial management tool must unenroll and reenroll if the Symantec certificate for the trial management tool is no longer available, or if the company obtains its own Symantec certificate for signing apps.

### Can companies start without any Symantec certificate and then add one later, even after Windows Phone 8.1 devices have enrolled?
Yes. Even if Windows Phone 8.1 devices have already enrolled, you can get a Symantec certificate, sign the ssp.xap, and upload it and the pfx file. Intune will then generate the AET. Windows Phone 8.1 devices will get the AET the next time they sync, up to eight hours. Allow at least eight hours before deploying line of business apps after uploading the xap and pfx.

## See Also
[Get ready to enroll devices in Microsoft Intune](../Topic/Get_ready_to_enroll_devices_in_Microsoft_Intune.md)

