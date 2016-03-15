---
title: MD Conversion - Manage Internet access using managed browser policies with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 3837a995-65e5-49a1-9bec-98fe5bd5ffb4
---
# MD Conversion - Manage Internet access using managed browser policies with Microsoft Intune
The managed browser is a web browsing application that you can deploy in your organization using [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)]. A managed browser policy configures an allow list or a block list that restricts the web sites that users of the managed browser can visit.

Because this app is a managed app, you can also apply mobile application management policies to the app, such as controlling the use of cut, copy and paste, preventing screen captures, and also ensuring that links to content that users click only open in other managed apps. For details, see [Configure and deploy mobile application management policies in the Microsoft Intune console](../Topic/Configure-and-deploy-mobile-application-management-policies-in-the-Microsoft-Intune-console.md).

> [!IMPORTANT]
> If users install the managed browser themselves on an iOS device with a version less than iOS 9, it will not be managed by any policies you create. To ensure that the browser is managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], they must uninstall the app before you can deploy it to them as a managed app. On iOS 9 and later, if the user installs the managed browser themselves they will be prompted to allow it to become managed by policy.

You can create managed browser policies for the following device types:

-   Devices that run Android 4 and later

-   Devices that run iOS 7.1 and later

The [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] Managed Browser supports opening web content from [Microsoft apps you can use with Microsoft Intune mobile application management policies](../Topic/Microsoft-apps-you-can-use-with-Microsoft-Intune-mobile-application-management-policies.md).

## Create a managed browser policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Add Policy**.

2.  Configure one of the following **Software** policy types:

    -   **Managed Browser Policy (Android 4 and later)**

    -   **Managed Browser Policy (iOS 7.1 and later)**

    For more information about how to create and deploy policies, see the [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md) topic.

3.  Use the following table to help you configure the managed browser policy settings:

    |Setting name|More information|
    |----------------|--------------------|
    |**Name**|Enter a unique name for the managed browser policy to help you identify it in the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console.|
    |**Description**|Provide a description that gives an overview of the managed browser policy and other relevant information that helps you to locate it.|
    |**Enable an allow list or block list to restrict the URLs the Managed Browser can open**|Select one of the following options:<br /><br />**Allow the managed browser to open only the URLs listed below** – Specify a list of URLs that the managed browser can open.<br /><br />**Block the managed browser from opening the URLs listed below** – Specify a list of URLs that the managed browser will be blocked from opening.<br /><br />For more information about the URL formats you can specify, see [URL format for allowed and blocked URLs](../Topic/Manage-Internet-access-using-managed-browser-policies-with-Microsoft-Intune.md#BKMK_URLs) in this topic.|

4.  When you are finished, click **Save Policy**.

The new policy displays in the **Configuration Policies** node of the **Policy** workspace.

## Create a software deployment for the managed browser app
After you have created the managed browser policy, you can then create a software deployment for the managed browser app, and associate it with the managed browser policy you created.

> [!IMPORTANT]
> Managed browser policies are not deployed in the same way as other [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] polices. This type of policy must be associated with the managed browser software package.

Deploy the app, ensuring that you select the managed browser policy on the **Mobile App Management** page to associate the policy with the app.

For more information about how to deploy apps, see [Deploy apps to mobile devices in Microsoft Intune - deleted](../Topic/Deploy-apps-to-mobile-devices-in-Microsoft-Intune---deleted.md).

## Security and privacy for the managed browser

-   On iOS devices, web sites that users visit that have an expired or untrusted certificate cannot be opened.

-   Settings that users make for the built-in browser on their devices are not used by the managed browser. This is because the managed browser does not have access to these settings.

-   If you configure the options **Require simple PIN for access** or **Require corporate credentials for access** in a mobile application management policy associated with the managed browser and a user clicks the help link on the authentication page, they can then browse any Internet sites regardless of whether they were added to a block list in the managed browser policy.

-   The managed browser can only block access to sites when they are accessed directly. It cannot block access when intermediate services (such as a translation service) are used to access the site.

-   To allow authentication, and to ensure that [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] documentation can be accessed,**&#42;.microsoft.com** is exempt from the allow or block list settings – it is always allowed.

### Turn off usage data
Microsoft automatically collects anonymous data about the performance and use of the managed browser to improve Microsoft products and services, but users can turn off data collection by using the **Usage Data** setting on their device. You have no control over the collection of this data.

## Reference information

### <a name="BKMK_URLs"></a>URL format for allowed and blocked URLs
Use the following information to learn about the allowed formats and wildcards you can use when specifying URLs in the allowed and blocked lists.

-   You can use the wildcard symbol ‘**&#42;**’ according to the rules in the permitted patterns list below.

-   Ensure that you prefix all URLs with **http** or **https** when entering them into the list.

-   You can specify port numbers in the address. If you do not specify a port number, the values used will be:

    -   Port 80 for http

    -   Port 443 for https

    Using wildcards for the port number is not supported, for example, **http://www.contoso.com:&#42;** and **http://www.contoso.com: /&#42;**

-   Use the following table to learn about the permitted patterns you can use when you specify URLs:

    |URL|Description|Matches|Does not match|
    |-------|---------------|-----------|------------------|
    |http://www.contoso.com|Matches a single page|www.contoso.com|host.contoso.com<br /><br />www.contoso.com/images<br /><br />contoso.com/|
    |http://contoso.com|Matches a single page|contoso.com/|host.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com|
    |http://www.contoso.com/&#42;|Matches all URLs beginning with www.contoso.com|www.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com/videos/tvshows|host.contoso.com<br /><br />host.contoso.com/images|
    |http://&#42;.contoso.com/&#42;|Matches all sub-domains under contoso.com|developer.contoso.com/resources<br /><br />news.contoso.com/images<br /><br />news.contoso.com/videos|contoso.host.com|
    |http://www.contoso.com/images|Matches a single folder|www.contoso.com/images|www.contoso.com/images/dogs|
    |http://www.contoso.com:80|Matches a single page, using a port number|http://www.contoso.com:80||
    |https://www.contoso.com|Matches a single, secure page|https://www.contoso.com|http://www.contoso.com|
    |http://www.contoso.com/images/&#42;|Matches a single folder and all subfolders|www.contoso.com/images/dogs<br /><br />www.contoso.com/images/cats|www.contoso.com/videos|

-   The following are examples of some of the inputs you cannot specify:

    -   &#42;.com

    -   &#42;.contoso/&#42;

    -   www.contoso.com/&#42;images

    -   www.contoso.com/&#42;images&#42;pigs

    -   www.contoso.com/page&#42;

    -   IP addresses

    -   https://&#42;

    -   http://&#42;

    -   http://www.contoso.com:&#42;

    -   http://www.contoso.com: /&#42;

### How conflicts between the allow and block list are resolved
If multiple managed browser policies are deployed to a device and the settings conflict, both the mode (allow or block) and the URL lists are evaluated for conflicts. In case of a conflict, the following behavior applies:

-   If the modes in each policy are the same, but the URL lists are different, the URLs will not be enforced on the device.

-   If the modes in each policy are different, but the URL lists are the same, the URLs will not be enforced on the device.

-   If a device is receiving managed browser policies for the first time and two policies conflict, the URLs will not be enforced on the device. Use the **Policy Conflicts** node of the **Policy** workspace to view the conflicts.

-   If a device has already received a managed browser policy and a second policy is deployed with conflicting settings, the original settings remain on the device. Use the **Policy Conflicts** node of the **Policy** workspace to view the conflicts.

## See Also
[Enable access to company resources with Microsoft Intune - deleted](../Topic/Enable-access-to-company-resources-with-Microsoft-Intune---deleted.md)

