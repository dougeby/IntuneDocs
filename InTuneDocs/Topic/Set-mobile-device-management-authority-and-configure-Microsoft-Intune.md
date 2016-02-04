---
title: Set mobile device management authority and configure Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 668d6460-9d34-47a7-8a85-bbe1ed89f8e1
author: NathBarn
---
# Set mobile device management authority and configure Microsoft Intune
Before users  can enroll mobile devices with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], the IT administrator must declare [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] as the *mobile device management authority*, add uses, and set up the Company Portal for users.

## Set MDM authority
The  *mobile device management authority* defines the management service with permission to manage a set of devices.  Solutions for the mobile device management authority include [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], Configuration Manager with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], or Office 365 MDM solutions.

This guidance assumes Intune is used without System Center Configuration Manager integration so the setting should be set to Microsoft Intune.

> [!IMPORTANT]
> Consider carefully whether you want to manage mobile devices using Intune-only (cloud service only) or System Center Configuration Manager with Intune integration (on-premises in conjunction with cloud service). After you set the mobile device management authority to either of these options, it cannot be changed again. If you're unsure of your options, see [Ways to do enterprise mobility](../Topic/Ways-to-do-enterprise-mobility.md).  The Intune service can be used in conjunction with Office 365. You can specify which cloud service manages specific mobile devices in the Office 365 admin center and Intune admin console, respectively.

### <a name="BKMK_Set_MDM_Authority"></a>Set mobile device management authority

1.  In the [Microsoft Intune administration console](http://manage.microsoft.com) click **Admin** &gt; **Mobile Device Management**.

2.  In the **Tasks** list, click **Set Mobile Device Management Authority**. The **Set MDM Authority** dialog box opens.

    ![](../Image/Intune-MDM-Authority.bmp)

3.  Intune requests confirmation that you want Intune as your MDM authority. Check the box and then click **Yes** to use Microsoft Intune to manage mobile devices.

4.  Now that Intune is the MDM authority, you can enable device enrollment for devices:

    -   [Enable iOS management](https://technet.microsoft.com/library/dn408185.aspx)

    -   [Enable Android management](https://technet.microsoft.com/library/dn764960.aspx)

    -   [Enable Windows Phone management](https://technet.microsoft.com/library/dn764959.aspx)

    -   [Enable Windows management](https://technet.microsoft.com/library/mt346003.aspx)

## Prepare to manage mobile devices with Microsoft Intune
The following steps and configurations let [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] manage devices using the Company Portal.

#### Set up mobile device management with Intune

1.  **Add Intune users**
    The mobile device owner must be added to the account portal before devices can be enrolled. Log in to the [Office 365 admin center](http://go.microsoft.com/fwlink/p/?LinkId=698854), click **Add users**, and select an option:

    -   **User**: To add a single user select **New** &gt; **User** and enter **Details**, **Assign roles**, **Set user location**, and then assign the user to a **Group**.

    -   **Bulk add**: Create a .csv file (see samples files provided) and import it into the account portal. Specify roles, location, and group, and then create the accounts. Sample and blank .csv files can be downloaded from the account portal.

    You can also enable Active Directory or Azure Active Directory synchronization. For more information about integrating other Azure Active Directory users with Intune, see [Directory synchronization roadmap](http://go.microsoft.com/fwlink/?LinkId=511540) or click **Other ways to add users** in the account portal.

2.  **Create groups**  (Optional)
    Groups in Intune provide great flexibility in managing your devices and users. You can set up groups to suit your organizational needs such as by geographic location, department, hardware characteristics, or operating system, or whether devices are user-owned or company-owned.   See [Use groups to manage users and devices with Microsoft Intune](../Topic/Use-groups-to-manage-users-and-devices-with-Microsoft-Intune.md).

    Policies are deployed to groups making group hierarchies a key design considerations. A group’s parent group cannot be changed once the group is created, so the design of your groups hierarchy from the start.

    Key considerations:

    -   **Keep hierarchies simple** - If your organization doesn't require complex hierarchies for targeting devices with policy, use the default groups

    -   **Think top-down** - Use **All Users** and **All devices** as parent groups if you'll want to apply policy applicable to all members

    -   **Ownership** - If your organization has both corporate-owned (COD) and user-owned (BYOD) devices, you can create groups to target these categories separately by making them child groups of **All Users** and **All Groups**

    -   **Use Active Directory** - If you have connected Azure Active Directory (AAD), you can use security groups to refine policy deployment by geography, department, or users known to use certain devices

    -   **No dynamic operating system groups** - Groups cannot dynamically target device operating system. You must use AD or AAD Security groups to define users of device types.

    You can create and manage groups after device enrollment. Creating groups beforehand lets you organize devices and target policy as they come into management.

3.  **Add policies for devices** (Optional)
    Policies are groups of settings that control features on devices. Most MDM policies are platform specific. You create policies using templates  containing recommended or customized settings, and then deploy them to groups. See [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

    Key considerations:

    -   **Naming conventions** - Name policies to reflect the policy's scope, purpose, and platform to simplify management

    -   **Ownership** - Create policy appropriate for privately owned (BYOD) or company-owned (CO) devices

    -   **Types of policy** - You can use:

        -   [Configuration policies](https://technet.microsoft.com/library/dn743712.aspx) - Set platform-specific management of device settings

        -   [Compliance, policies](https://technet.microsoft.com/library/dn705843.aspx) - Monitor and remediate  compliance issues for devices

        -   [Conditional access policies](https://technet.microsoft.com/library/dn818907.aspx) - Use with compliance issues to enable access to company resources like email and SharePoint

    -   **Conflict monitoring** - As devices enroll, you can use reports to ensure policies are performing as expected

    You can create and manage policies after device enrollment. Creating policy beforehand enrolling devices lets you target policy as they come into management.

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
    You can publish terms and conditions that your users will see when they first use the company portal from any device, whether or not that device is already enrolled. Users will have to accept those terms to access the portal. When you update the terms and conditions significantly and want users to see and accept them, you can mark the new terms and conditions as a new version, and users will go through the same process the next time they visit the portal.

    In the [Microsoft Intune administration console](http://manage.microsoft.com) click **Policy** &gt; **Terms and Conditions**, and then click **Add** to create a new terms and conditions policy. Specify the following information on the **Create Terms and Conditions** page.

    -   **Name**

    -   **Description** (optional)

    -   **Title**

    -   **Text for terms**

    -   **Text to explain what it means if the user accepts**

    Click **Save**, then select the policy and click **Manage Deployment**. In the **Manage Deployment** dialog box, select the user groups to deploy the policy to, and then click **OK**.

    You can see [details about  terms and conditions](https://technet.microsoft.com/library/mt405893.aspx).  You can also see which users have accepted the terms and conditions by using the [Terms and conditions reports](https://technet.microsoft.com/library/dn646977.aspx).

7.  **Tell users how to get access to company resources with the company portal**
    [What to tell your end users about using Microsoft Intune](../Topic/What-to-tell-your-end-users-about-using-Microsoft-Intune.md)

## Next steps: Enable device enrollment
Now that Intune is your MDM authority and you've configured , you can enable device enrollment for devices:

-   [Enable iOS management](https://technet.microsoft.com/library/dn408185.aspx)

-   [Enable Android management](https://technet.microsoft.com/library/dn764960.aspx)

-   [Enable Windows Phone management](https://technet.microsoft.com/library/dn764959.aspx)

-   [Enable Windows management](https://technet.microsoft.com/library/mt346003.aspx)

## See Also
[Get ready to enroll devices in Microsoft Intune](../Topic/Get-ready-to-enroll-devices-in-Microsoft-Intune.md)

