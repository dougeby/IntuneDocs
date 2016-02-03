---
title: Resolve GPO and Microsoft Intune policy conflicts
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b
author: robstackmsft
---
# Resolve GPO and Microsoft Intune policy conflicts
[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] uses policies that help you manage settings on the computers you manage. For example, you could use a policy to control settings for the Windows Firewall on computers. Many of the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] settings are similar to settings you might configure with Windows Group Policy. However, it is possible that, at times, the two methods might conflict with one another.

When conflicts happen, domain-level Group Policy takes precedence over [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policy, unless the computer can’t logon to the domain. In this case, [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policy is applied to the client computer.

## <a name="BKMK_plan"></a>What to do if you are using Group Policy
Check that any policies you apply are not being managed by Group Policy. To help prevent conflicts, you could employ one or more of the following methods:

-   Move your computers to an Active Directory organizational unit (OU) that does not have Group Policy settings applied before you install the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client. You can also block Group Policy inheritance on OUs that contain computers enrolled in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to which you do not want to apply Group Policy settings.

-   Use a WMI filter, or security filter to restrict Group Policy Objects only to computers that are not managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. For information and examples of how to do this, see the [How to filter existing Group Policy Objects to avoid Conflicts with Microsoft Intune policy](../Topic/Resolve_GPO_and_Microsoft_Intune_policy_conflicts.md#BKMK_Filter) below.

-   Disable or remove the Group Policy Objects that conflict with the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policies.

For more information about Active Directory and Windows Group Policy, see your Windows Server Documentation.

### <a name="BKMK_Filter"></a>How to filter existing Group Policy Objects to avoid Conflicts with Microsoft Intune policy
If you have identified Group Policy Objects (GPOs) with settings that conflict with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policies, you can use either of the following filtering methods to restrict those GPOs only to computers that are not managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

#### Use WMI filters.
WMI filters selectively apply GPOs to computers that satisfy the conditions of a query. To apply a WMI filter, deploy a WMI class instance to all computers in the enterprise before you enroll any computers in the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service.

##### <a name="BKMK_filters"></a>To apply WMI filters to a GPO

1.  Create a management object file by copying and pasting the following into a text file, and then saving it to a convenient location as **WIT.mof**. The file contains the WMI class instance that you deploy to computers that you want to enroll in the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service.

    ```
    //Beginning of MOF file.
    #pragma classflags("forceupdate")
    #pragma namespace ("\\\\.\\Root")
    instance of __Namespace
    {
       Name = "WindowsIntune";
    };

    #pragma namespace ("\\\\.\\Root\\WindowsIntune")
    [ 
       Description("This class defines Microsoft Intune common properties")
    ]
    class WindowsIntune_ManagedNode
    {
       [ read, Description("This defines whether Microsoft Intune Policy is enabled"): DisableOverride ToSubClass ]
       boolean WindowsIntunePolicyEnabled;
       [ read, key, Description("This property defines the version." "Example: 1.0"): ToSubClass ]
       string Version;
    };

    instance of WindowsIntune_ManagedNode
    {
       Version = "1.0";
       WindowsIntunePolicyEnabled = 1;
    };
    ```

2.  Use either a startup script or Group Policy to deploy the file. The following is the deployment command for the startup script. The WMI class instance must be deployed before you enroll client computers in the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service.

    **C:/Windows/System32/Wbem/MOFCOMP &lt;path to MOF file&gt;\wit.mof**

3.  Run either of the following commands to create the WMI filters, depending on whether the GPO you want to filter applies to computers that are managed by using [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] or to computers that are not managed by using [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

    -   For GPOs that apply to computers that are not managed by using [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], use the following:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    -   For GPOs that apply to computers that are managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], use the following:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4.  Edit the GPO in the Group Policy Management console to apply the WMI filter that you created in the previous step.

    -   For GPOs that should apply only to computers that you want to manage by using [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], apply the filter **WindowsIntunePolicyEnabled=1**.

    -   For GPOs that should apply only to computers that you do not want to manage by using [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], apply the filter **WindowsIntunePolicyEnabled=0**.

For more information about how to apply WMI filters in Group Policy, see the blog post [Security Filtering, WMI Filtering, and Item-level Targeting in Group Policy Preferences](http://go.microsoft.com/fwlink/?LinkId=177883).

#### Use security group filters
Group Policy lets you apply GPOs to only those security groups specified in the **Security Filtering** area of the Group Policy Management console for a selected GPO. By default, GPOs apply to **Authenticated Users**.

-   In the **Active Directory Users and Computers** snap-in, create a new security group that contains computers and user accounts that you do not want to manage by using [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. For example, you could name the group **Not In [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)]**.

-   In the Group Policy Management console, on the **Delegation** tab for the selected GPO, right-click the new security group to delegate appropriate **Read** and **Apply Group Policy** permissions to both users and computers in the security group. (**Apply Group Policy** permissions are available on the **Advanced** dialog box.)

-   Then apply the new security group filter to a selected GPO, and remove the **Authenticated Users** default filter.

The new security group must be maintained as enrollment in the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service changes.

## See Also
[Manage Windows PCs with Microsoft Intune](../Topic/Manage_Windows_PCs_with_Microsoft_Intune.md)

