---
title: Use groups to manage users and devices with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: eb9b01ce-9b9b-4c2a-bf99-3879c0bdaba5
author: Nbigman
---
# Use groups to manage users and devices with Microsoft Intune
**Groups** in [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] give you great flexibility for managing your devices and users. You can set up groups to suit your organizational needs (for example, by geographic location, department, or hardware characteristics).

Additionally, you can filter groups to allow your IT admins permissions to only perform operations on the groups you specify. For more information, see [Use filtered group views to help secure and manage users and devices](../Topic/Use_groups_to_manage_users_and_devices_with_Microsoft_Intune.md#BKMK_Filter) in this topic.

To create and manage groups, you use the **Groups** workspace in the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)]. The **Groups Overview** page contains status summaries that help you identify and prioritize issues that require your attention for:

-   Alerts

-   Software updates

-   [!INCLUDE[epshort](../Token/epshort_md.md)]

-   Policy

-   Software management

Additionally, a hierarchical view of your groups is shown that lets you view status summaries and identify and resolve problems for members of a selected group.

[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] provides nine built-in groups that you cannot edit or delete:

-   **All Users**

    -   **Ungrouped Users**

-   **All Devices**

    -   **All Computers**

    -   **All Mobile Devices**

        -   **All Direct Managed Devices**

        -   **All Exchange ActiveSync Managed Devices**

    -   **All Corporate-owned Devices**

    -   **Ungrouped Devices**

## Group memberships

-   A group can contain either users or devices, but not both.

    -   **Device groups:** This includes both computers and mobile devices. Before you can add a computer to a group, it must be enrolled. Before you can add a mobile device to a group, your environment must be configured to support mobile devices, and the devices must be enrolled, or discovered from Exchange ActiveSync.

    -   **User groups:** A group can contain users from security groups, which are groups that synchronize from your Active Directory. If you do not use Active Directory synchronization, you can manually create these groups.

-   A device or a user can belong to more than one group.

-   A group can include and exclude members based on the following membership rules:

    -   **Criteria Membership:** These are dynamic rules that [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] runs to include or exclude members.  These criteria use security groups and other information synchronized from your local Active Directory. When the security group or data that is synchronized changes, the group membership can change.

    -   **Direct Membership:** These are static rules that explicitly add or exclude members. The membership list is static.

-   Active Directory Domain Services (AD DS) is not required to create user groups or device groups that include users or computers, but for device groups to include mobile devices, your environment must be configured to support mobile devices.

    Additionally, the devices must be discovered and added to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

## Group relationships

-   Every group you create must have a parent group and you cannot change a group’s parent group once the group is created.

-   When adding users or devices to a child group:

    -   Child groups are always subsets of the parent group.

    -   New members you add to a child group are automatically added to that group’s parent group.

    -   You cannot add a member to a child group when that member is excluded from the parent group.

-   The membership of a parent group defines the available membership for the child group.

-   When you delete a parent group, all child groups are deleted.

-   You can deploy content and policies to a parent group while excluding deployment to child groups.

-   You can add a specific user or device to a child group that is not a member of the parent group. If you do so, the new group member will be added to the parent group.

    However, you cannot add a member to a child group that is excluded from the parent group.

-   Group membership is recursive. For example:

    -   **Pat** is a member of only one group, the **Laptop Users** security group.

    -   The **Laptop Users** group is a member of the **Approved Users** security group.

    -   You create a group in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] that uses a dynamic membership query that includes the members of the **Approved Users** group. The result is that your [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] user group includes **Pat**.

> [!TIP]
> When you're creating your groups consider how you will apply policy. For example, you may have policies specific to device operating systems, and policies specific to different roles in your organization, or to Organizational Units you've already defined in Active Directory. Some consider it useful to have device groups specific to iOS, Android, and Windows, as well as user groups for each organizational role.
> 
> You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your company. Then create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.
> 
> Be careful naming your policies so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.
> 
> Each time you create a restrictive policy you'll want to communicate it to your users, so after you create the more general groups and policies pay attention to how you create smaller groups so that you can reduce unnecessary communication.

## How to create Microsoft Intune groups

### <a name="BKMK_CreateDevGroup"></a>To create a device group

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Groups** &gt; **Overview** &gt; **Create Group**.

2.  Specify a name and optional description for the group, select a device group as the parent group, then click **Next**.

3.  On the **Define Membership Criteria** page, select the type of devices the group will include. Additional options to configure the group depend on the type of devices you select:

    -   **Computer:** Specify whether to include all members of the parent group, the Organizational Units you want to include or exclude and the domains you want to include or exclude. The OU and domain information for a computer is obtained from inventory.

    -   **Mobile:** Specify to include only mobile devices that are managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], those managed by Exchange ActiveSync, or both.

    -   **All devices:** This option includes all devices with no exclusions based on criteria.

4.  On the **Define Direct Membership** page, include or exclude individual devices you specify by clicking **Browse**. If you use the option to select devices that are not in the parent group you specified, those devices are automatically added to the parent group.

5.  On the **Summary** page, review the actions that will be taken, and then click **Finish**.

The newly created group can be found in the **Groups** list, in the **Groups** workspace, under the parent group. From here, you can also edit or delete the group.

#### To create a user group

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Groups** &gt; **Overview** &gt; **Create Group**.

2.  Specify a name and optional description for the group, select a user group as the parent group, then click **Next**.

3.  On the **Define Membership Criteria** page, specify whether to include all members of the parent group or to start with an empty group.  You can then  include or exclude members based on the **Security groups** of users that you manually configure in the [Office 365 admin center](http://go.microsoft.com/fwlink/?LinkId=698854) or that synchronize from your local Active Directory. If the membership of a security group changes, membership of user groups based on that security group can also change.

    > [!IMPORTANT]
    > Currently, if your group includes members from specific security or manager groups, and you also exclude members from specific groups, the members you initially included will be removed. To create a group that has both included members and excluded members, we recommend that you first create a parent group with the included members, and then create a child to that group in which you list the excluded members. You can then use that child group as appropriate for Intune policies, profiles, and app distribution.

    > [!NOTE]
    > In the Azure Management Portal you can create a group based on the manager that the users report to. The group will be dynamic, changing as employees are added to or removed from that manager's team in Azure Active Directory. The procedure for creating an Azure group based on a manager is described in [Using attributes to create advanced rules](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) in the section called **To configure a group as a “Manager” group**.

4.  On the **Define Direct Membership** page, include or exclude individual users you specify by clicking **Browse**. If you use the option to select users that are not in the parent group you specified, those devices are automatically added to the parent group.

5.  On the **Summary** page, review the actions that will be taken, and then click **Finish**.

The newly created group can be found in the **Groups** list, in the **Groups** workspace, under the parent group. From here, you can also edit or delete the group.

> [!TIP]
> Security groups are a great resource for populating user groups. Since your security groups define who has access to which resources, that can translate well into  [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] user groups. Security groups that are synced from Active Directory to Azure Active Directory, or that are created directly in Azure Active Directory through the Office 365 admin center or the Azure Administration portal, are all available to you for creating user groups in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

## Managing your groups
Once you’ve created your groups you will continue to manage them according to the needs of your organization.

### <a name="BKMK_Filter"></a>Use filtered group views to help secure and manage users and devices
Filtered group views let you restrict which groups each IT admin can manage. This can be useful when:

-   Your IT admins should only be able to deploy items to specific users and devices.

-   You want to display only relevant groups to each IT admin.

You can configure filtered group views for service administrators in the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] administrator console. For details, see [What to know before setting up Microsoft Intune](../Topic/What_to_know_before_setting_up_Microsoft_Intune.md).

After configuring filtered group views for a service administrator, that administrator:

-   Can view and select only the groups you specified when deploying software or policies, or when using reports

-   Does not receive status information on the following pages of the administration console:

    -   **System Overview**

    -   **Groups Overview**

    -   **Endpoint Protection Overview**

    -   **Alerts Overview**

    -   **Software Overview**

    -   **Policy Overview**

##### To configure filtered group views

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Admin** &gt; **Administrator Management** &gt; **Service Administrators**.

2.  Select the service administrator for whom you want to filter groups, and then click **Manage Groups**.

3.  In the **Select the groups that will be visible to this service administrator** dialog box, add the groups that the selected service administrator will be able to access, and then click **OK**.

After you configure the filtered group views, the IT admin will be able to view and select only the groups you selected.

## Other management tasks for groups
You can edit your group to change its name and description and who belongs to the group.

You can delete a group that no longer serves the needs of your organization. Deleting a group does not delete the users that belong to that group.

## Groups and policy
Once you've set up your groups and policies, you'll want to check the practical implications of your design. Here are some helpful tips and information about groups and policy.

You can retrieve a lot of information regarding each device managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. Select any device from a device group and browse through the categories of information at the top of the screen. Select **Policy** . You'll see something like this screenshot of an Android device's policy settings.

![](../Image/Intune_Device_Policy_v.2.jpg)

Each policy has an **Intended Value** and a **Status**. The intended value is what you meant to achieve when assigning the policy. The status is what is actually achieved when all of the policies that apply to the device, as well as the restrictions and requirements of the hardware and the operating system, are considered together.  In the screenshot you can see two clear examples:

-   **Allow simple passwords** is set to **Yes**, as shown in the **Intended Value** column, but its **Status** is **Not applicable**. This is because simple passwords are not supported for Android devices.

-   Similarly, the expanded policy item**Email settings for iOS devices** is not applied to this device, as it is an Android device.

> [!NOTE]
> Remember that when two policies with different levels of restriction apply to the same device or user, the more restrictive policy applies in practice.

## See Also
[Get started with a paid subscription to Microsoft Intune](../Topic/Get_started_with_a_paid_subscription_to_Microsoft_Intune.md)
[How to buy Intune](http://technet.microsoft.com/en-us/library/dn646949.aspx)

