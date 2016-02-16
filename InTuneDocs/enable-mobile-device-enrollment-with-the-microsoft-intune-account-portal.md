---
title: Enable mobile device enrollment with the Microsoft Intune Account Portal
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 3adf63cd-34b6-4641-aa88-766bb59dd853
author: NathBarn
robots: noindex,nofollow
---
# Enable mobile device enrollment with the Microsoft Intune Account Portal
Intune supports “bring your own device” (BYOD) by letting users enroll their devices through the Microsoft Intune **Account Portal**. Before you can enroll devices, you must configure Intune for mobile device management. If you haven’t already, set up management for each device platforms in your organization:

-   [iOS management](http://technet.microsoft.com/library/dn408185.aspx)

-   [Android management](http://technet.microsoft.com/library/dn764960.aspx)

-   [Windows management](http://technet.microsoft.com/library/dn764959.aspx)

## Enable mobile device enrollment with the Intune Account Portal

1.  **Add Intune users**
    The mobile device owner must be added to the Microsoft Intune Account Portal before devices can be enrolled. Log in to the [Microsoft Intune Account Portal](http://account.manage.microsoft.com), click **Add users**, and select an option:

    -   **User**: To add a single user select **New** &gt; **User** and enter **Details**, **Assign roles**, **Set user location**, and then assign the user to a **Group**.

    -   **Bulk add**: Create a .csv file (see samples files provided) and import it into the Intune Account Portal. Specify roles, location, and group, and then create the accounts. Sample and blank .csv files can be downloaded from the Microsoft Intune Account Portal.

    You can also enable Active Directory or Azure Active Directory synchronization. For more information about integrating other Azure Active Directory users with Intune, see [Directory synchronization roadmap](http://go.microsoft.com/fwlink/?LinkId=511540) or click **Other ways to add users** in the Intune Account Portal.

2.  **Create groups**  (Optional)
    Groups give flexibility for managing devices and users. You can set up groups to suit your organizational needs by geographic location, department, or hardware characteristics, for example.   See [Use groups to manage users and devices with Microsoft Intune](../Topic/Use-groups-to-manage-users-and-devices-with-Microsoft-Intune.md).

3.  **Add policies for devices** (Optional)
    Policies are groups of settings that control features on devices. Most MDM policies are platform specific. You create policies using templates  containing recommended or customized settings, and then deploy them to groups. See [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

4.  **Set device enrollment limit** (Optional) 
    To limit the number of mobile devices a user can enroll, log in to the [Microsoft Intune administration console](http://manage.microsoft.com), click **Admin** &gt; **Mobile Device Management** &gt; **Enrollment rules**. Select the maximum number of devices a user can enroll and then click **Save**.

5.  **Set Company Portal settings** 
     You can customize the Intune Company Portal for your company. In the [Microsoft Intune administration console](http://manage.microsoft.com) click **Admin** &gt; **Company Portal**. Configure the following

    -   **Company Name**

    -   **IT department contact name**

    -   **IT department phone number**

    -   **Additional information**

    -   **Company privacy statement URL**

    -   **Support website URL (not displayed)**

    -   **Website name**

6.  **Set Terms and Conditions**
    You can publish terms and conditions that your users see when they first use the company portal from any device. In the [Microsoft Intune administration console](http://manage.microsoft.com) click **Company Portal** &gt; **Terms and Conditions**.

### <a name="BKMK_TermsAndConditions"></a>About Terms and Conditions
You can publish terms and conditions that your users will see when they first use the company portal from any device, whether or not that device is already enrolled. Users will have to accept those terms to access the portal. When you update the terms and conditions significantly and want users to see and accept them, you can mark the new terms and conditions as a new version, and users will go through the same process the next time they visit the portal.

Terms and conditions apply to users, not to devices, so users will only have to accept each version once to visit the company portal from any of their devices.

#### Terms and conditions reports
**Terms and Conditions** reports show which users accepted your terms and conditions, the most recent version number they accepted, and the date they accepted that version. Export the report to keep an archive of when users accepted previous versions. See [Understand Microsoft Intune operations by using reports](../Topic/Understand-Microsoft-Intune-operations-by-using-reports.md).

### How users enroll their mobile devices
Once you’ve set up enrollment, you can invite users to enroll their devices. For guidance helping users to enroll their personal devices, download [Microsoft Intune Enrollment Instructions](http://go.microsoft.com/fwlink/?LinkID=534864).  You can also refer to [What to tell your end users about using Microsoft Intune](../Topic/What-to-tell-your-end-users-about-using-Microsoft-Intune.md).

General instructions:

1.  Users enroll and manage their mobile devices with the Company Portal app. Users can also use the Company Portal website to enroll devices.

    -   **Android** - Users install the **Company Portal** app from Microsoft Corporation available on [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612).

    -   **iOS** - Users install the **Company Portal** app from Microsoft Corporation available in the App Store. Users can then view their **Devices** to enroll their phones.

    -   **Windows Phone 8.1**- Users install the **Company Portal** app from Microsoft Corporation available in the Windows Phone store. If a signed company portal app was distributed, users can also go **Settings** &gt; **Workplace** &gt; **Add account**, sign in, and then tap **Install company app or Hub** to install the Company Portal.

    -   **Windows Phone 8.0**  - Users click **system settings** &gt; **company apps**, and sign in using their user ID. The Company Portal app is deployed to users’ phones.

    -   **Windows 8.1 and Windows RT 8.1** - Users download the **Company Portal** app from the Windows Store. If a signed company portal app was distributed, users can also go to **PC Settings** &gt; **Network** &gt; **Workplace**, sign in, mark the **Allow apps and services from IT admin** checkbox, and click **Join**.

    -   **Windows RT** - Click **Start**, and type “System Configuration”, and click the dialog box to open the **Company Apps**.

2.  When users open the Company Portal they’ll be asked for credentials. If you didn’t create a public domain CNAME, Windows and Windows Phone users are prompted for the server address and must type “manage.microsoft.com”. Windows Phone 8.1 and iOS phone users can then view their **Enrolled Devices** to enroll their phone.

3.  When a user first enrolls, or if you’ve required acceptance of a new version of terms and conditions, users must accept the terms and conditions. The device is enrolled whether they accept the terms or not. If they accept, they can continue to the portal. If they decline they are asked to confirm that they want to decline, and are then provided with a link to instructions on how to unenroll. They are not automatically unenrolled, and until they unenroll you can still manage the device.

    At this point the process differs for devices that have not yet been enrolled, depending on the operating system of the device.

    -   For Windows devices and Windows Phone 8.1, the Company Portal will remind the user to enroll. Windows Phone 8.1 will have a link to enrollment settings, and Windows will have a link to help content that describes how to enroll.

    -   For iOS and Android devices, the user is led through the enrollment process. Users will still see a message from Microsoft about the impact of enrolling.

> [!CAUTION]
> Windows and Windows Phone users might find the enrollment interface and enroll without seeing your terms and conditions. Advise your users to start at the Windows Store or Windows Phone Store to increase exposure and acceptance of your terms and conditions.

**Once devices are enrolled you can:**

-   [Understand your devices with inventory in Microsoft Intune](../Topic/Understand-your-devices-with-inventory-in-Microsoft-Intune.md)

-   [Enable access to company resources with Microsoft Intune - deleted](../Topic/Enable-access-to-company-resources-with-Microsoft-Intune---deleted.md)

-   [Deploy apps to mobile devices in Microsoft Intune - deleted](../Topic/Deploy-apps-to-mobile-devices-in-Microsoft-Intune---deleted.md)

-   [Manage settings and features on your devices with Microsoft Intune policies](../Topic/Manage-settings-and-features-on-your-devices-with-Microsoft-Intune-policies.md)

-   [Help protect your data with remote wipe, remote lock, or passcode reset using Microsoft Intune](../Topic/Help-protect-your-data-with-remote-wipe,-remote-lock,-or-passcode-reset-using-Microsoft-Intune.md)

## See Also
[Get ready to enroll devices in Microsoft Intune](../Topic/Get-ready-to-enroll-devices-in-Microsoft-Intune.md)
[Enroll corporate-owned devices with the Device Enrollment Manager in Microsoft Intune](../Topic/Enroll-corporate-owned-devices-with-the-Device-Enrollment-Manager-in-Microsoft-Intune.md)
[How to buy Intune](http://technet.microsoft.com/library/dn646949.aspx)

