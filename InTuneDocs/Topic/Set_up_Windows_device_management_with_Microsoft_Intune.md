---
title: Set up Windows device management with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
author: NathBarn
---
# Set up Windows device management with Microsoft Intune
You can use  [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to manage desktops, laptops, and other devices running Windows as mobile devices. You may also want to [Set up Windows Phone management with Microsoft Intune](../Topic/Set_up_Windows_Phone_management_with_Microsoft_Intune.md) or [manage computers with Intune client software](http://technet.microsoft.com/library/dn646959.aspx) using the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client.

## Prepare to manage Windows devices with Intune
To access resources managed with[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] users can enroll their Windows computers as mobile devices.  Creating a DNS CNAME helps users connect to the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] company portal without entering a server name. If you want to deploy the company portal with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], you will need to enable sideloading with a sideloading key.   Users can also download and install the company portal from the Store or use software included in Windows. Complete the following steps to set up Windows device management with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

#### Set up Windows device management

1.  **Set up Intune**
    If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](https://technet.microsoft.com/library/mt346013.aspx) as **Microsoft Intune** and setting up MDM.

2.  **Set a DNS alias for the enrollment server address** (optional)

    A DNS alias (CNAME record type) makes it easier for users to enroll their devices by automatically populating the server name during enrollment.

    ###### Verify and create DNS CNAME

    1.  In the [Intune administration console](http://manage.microsoft.com), click **Administration** &gt; **Mobile Device Management** &gt; **Windows Phone**.

    2.  Type the URL of the verified domain of the company website in the **Specify a verified domain name** box and then click **Test Auto-Detection**.

    3.  Create CNAME resource records for your company’s domain. The CNAME resource records must contain the following information:

        |TYPE|Host Hame|Points to|TTL|
        |--------|-------------|-------------|-------|
        |CNAME|enterpriseenrollment.company_domain.com|manage.microsoft.com|1 Hour|
        |CNAME|enterpriseregistration.company_domain.com|enterpriseregistration.windows.net|1 Hour|
        For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to manage.microsoft.com. If there is more than one verified domain, create a CNAME record for each domain.

        -   `manage.microsoft.com` – Supports a redirect to the Intune service with domain recognition from the email’s domain name

        -   `enterpriseregistration.windows.net` – Supports workplace join for mobile devices. It also supports conditional access for Windows 8.1

    ![](../Image/Windows_Device_Enrollment.bmp)

3.  **Enable sideloading apps** (Optional)
    For Windows RT 8.1,  Windows 8.1, and  Windows 10 devices, the Company Portal app can be installed from the Windows Store. When not installed directly from the Windows Store, installation of the Company Portal app requires sideloading keys on target computers. See [http://go.microsoft.com/fwlink/?LinkID=290705](http://go.microsoft.com/fwlink/?LinkID=290705) for details on how to deploy sideloading keys. Although sideloaded apps do not have to be certified by the Windows Store or installed through the Windows Store, they can only be installed on sideloading-enabled devices. For more information on acquiring sideloading keys, see [Microsoft Volume Licensing](http://go.microsoft.com/fwlink/?LinkId=264711).

    ###### To code-sign apps for Windows devices

    1.  In the [Intune administration console](http://manage.microsoft.com) click **Administration** &gt; **Mobile Device Management** &gt; **Windows** &gt; **Add Sideloading Key**.

    2.  In the **Add Sideloading Key** dialog box, enter a name, the sideloading product activation key, the number of total activations, and an optional description, and then click **OK**.

    3.  Download the Microsoft Intune Company Portal App for Windows 8.1 from the Download Center [http://go.microsoft.com/fwlink/?LinkId=615800](http://go.microsoft.com/fwlink/?LinkId=615800). Run the downloaded file to extract CompanyPortal.appx file and place it in a network-accessible shared folder.

    4.  Run **Windows PowerShell** as an administrator and then enter the following cmdlet:

        ```
        Powershell add-appxpackage –path '‹path›'
        ```

    5.  Verify that the **Company Portal** tile is available on in the app list on the target computer (on Windows 8.1 or Windows RT 8.1 devices a tile will be created on the Start screen automatically)

4.  **Tell users how to get access to company resources with the company portal**
    Your users will need to know how to enroll their devices and what to expect once they're brought into management. [What to tell your end users about using Microsoft Intune](../Topic/What_to_tell_your_end_users_about_using_Microsoft_Intune.md)

## See Also
[Get ready to enroll devices in Microsoft Intune](../Topic/Get_ready_to_enroll_devices_in_Microsoft_Intune.md)

