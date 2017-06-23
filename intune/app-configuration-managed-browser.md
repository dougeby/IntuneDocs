---
# required metadata

title: Manage web access with the Managed Browser app 
titleSuffix: "Intune on Azure"
description: Deploy the Managed Browser application to restrict web browsing and the transfer of web data to other apps."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1feca24f-9212-4d5d-afa9-7c171c5e8525

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: maxles
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Manage Internet access using Managed browser policies with Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The Managed Browser is a web browsing app available that you can download from public app stores for use in your organization. With Intune, the Managed Browser can be used to access corporate sites and SaaS apps with Single Sign-On via the MyApps service, while keeping web data protected. Additionally, the Managed Browser can be pre-configured with a list of URLs and domains to restrict which sites the user can navigate to in the corporate context.

Because this app has integration with the Intune SDK, you can also apply app protection policies to it. These policies might include controlling the use of cut, copy, and paste, preventing screen captures, and ensuring that links to content that users select open only in other managed apps. For details, see [What are app protection policies?](/intune/app-protection-policy).
You can apply these settings to devices that are enrolled with Intune, enrolled with another device management product, and also to devices that are not managed at all.

>[!IMPORTANT]
>The Managed Browser app only retrieves and applies Intune app protection policies when another app on the device has retrieved an app protection policy.<br><br> 

If users install the Managed Browser from the app store and Intune does not manage it, it can be used as a basic web browser, with support for Single Sign-On through the Microsoft MyApps site. Users will be taken directly to the MyApps site, where they can see all of their provisioned SaaS applications.
While the Managed Browser is not managed by Intune, it will not be able to access data from other Intune-managed applications. 

The Managed Browser does not support the Secure Sockets Layer version 3 (SSLv3) cryptographic protocol.

You can create Managed Browser policies for the following device types:

-   Devices that run Android 4 and later

-   Devices that run iOS 8.0 and later

The Intune Managed Browser supports opening web content from [Microsoft Intune application partners](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx).

## Create a Managed Browser app configuration

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune App Protection**.
3. On the **Settings** blade of the Intune mobile application management dashboard, choose **App configuration**.
4. On the **App Configuration** blade, choose **Add Config**.
5. On the **Add app configuration** blade, enter a **Name**, and optional **Description** for the app configuration settings.
5. Choose **Select required apps** and then, on the **Targeted apps** blade, choose the **Managed Browser** for iOS, for Android, or for both.
6. Choose **OK** to return to the **Add app configuration** blade.
7. Choose **Define configuration**. On the **Configuration** blade, you define key and value pairs to supply configurations for the Managed Browser.
Use the sections later in this topic to learn about the different key and value pairs you can define.
8. When you are done, click **OK**.
9. On the **Add app configuration** blade, choose **Create**.
10. The new configuration is created, and displayed on the **App configuration** blade.


## Assign the configuration settings you created

You assign the settings to Azure AD groups of users. If that user has the Managed Browser app installed, then the app will be managed by the settings you specified.

1. On the **Settings** blade of the Intune mobile application management dashboard, choose **App configuration**.
2. From the list of app configurations, select the one you want to assign.
3. On the next blade, choose **User Groups**.
4. On the **User groups** blade, select the Azure AD group to which you want to assign the app configuration, and then choose **OK**.


## How to configure Application Proxy settings for the Managed Browser

Together, the Intune Managed Browser and [Azure AD Application Proxy]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) can be used to support the following scenarios for end users of iOS and Android devices:

- A user downloads and signs in to the Microsoft Outlook app.  Intune app protection policies are automatically applied, encrypting saved data and blocking the user from transferring corporate files to unmanaged apps or locations on the device. 
When the user then clicks a link to an intranet site in Outlook, you can specify that the link opens in the Managed Browser app, rather than another browser.
The Managed Browser recognizes that this intranet site has been exposed to the user through the Application Proxy. The user is automatically routed through the Application Proxy, to authenticate with any applicable multi-factor authentication and conditional access before reaching the intranet site. 
This site, which could previously not be found while the user was remote, is now accessible and the link in Outlook works as expected.  

- A remote user opens the Managed Browser application and navigates to an intranet site using the internal URL. The Managed Browser recognizes that this intranet site has been exposed to the user via the Application Proxy. The user is automatically routed through the Application Proxy, to authenticate with any applicable multi-factor authentication and conditional access before reaching the intranet site.
This site, which could previously not be found while the user was remote, is now accessible.  

### Before you start

- Ensure that your internal applications published through Azure AD Application Proxy.
- To configure Application Proxy and publish applications, see the [setup documentation]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started#how-to-get-started). 
- You must be using minimum version 1.2.0 of the Managed Browser app.
- Users of the Managed Browser app have an [Intune app protection policy]( app-protection-policy.md) assigned to the app. 

#### Step 1: Enable automatic redirection to the Managed Browser from Outlook
Outlook must be configured with an app protection policy with the setting **Restrict web content to display in the Managed Browser** enabled.

#### Step 2: Assign an app configuration policy assigned for the Managed Browser.
This procedure configures the Managed Browser app to use app proxy redirection. Using the procedure to create a Managed Browser app configuration, supply the following key and value pair:

##### Key

**com.microsoft.intune.mam.managedbrowser.AppProxyRedirection**

 
##### Value

**true**


## How to configure the homepage for the Managed Browser

This setting allows you to configure the homepage that users see when they start the Managed Browser or create a new tab. Using the procedure to create a Managed Browser app configuration, supply the following key and value pair:

### Key

**com.microsoft.intune.mam.managedbrowser.homepage**

### Value

Specify a valid URL. Incorrect URLs will be blocked as a security measure.

Example: **https://www.bing.com**


## How to configure bookmarks for the Managed Browser

This setting allows you to configure a set of bookmarks that will be available to users of the Managed Browser.

- These bookmarks cannot be deleted or modified by users
- These bookmarks will display at the top of the list. Any bookmarks that users create will be displayed below these bookmarks.

Using the procedure to create a Managed Browser app configuration, supply the following key and value pair:

### Key

**com.microsoft.intune.mam.managedbrowser.bookmarks**

### Value

The value for this configuration is a list of bookmarks. Each bookmark consists of the bookmark title, and the bookmark URL. Seperate the title, and URL with the **|** character.

Example: **Microsoft Bing|https://www.bing.com**

To configure multiple bookmarks, sperate each pair with the double character, **||** 

Example: **Bing|https://www.bing.com||Contoso|https://www.contoso.com**

## How to specify allowed and blocked URLs for the Managed Browser

Using the procedure to create a Managed Browser app configuration, supply the following key and value pair:

### Key

Choose from:

- To specify allowed URLs (only these URLs are allowed; no other sites can be accessed): **com.microsoft.intune.mam.managedbrowser.AllowListURLs**
- To specify blocked URLs (all other sites can be accessed): **com.microsoft.intune.mam.managedbrowser.BlockListURLs**

>[!IMPORTANT]
>Do not specify both keys. If both keys are targeted to the same user, the allow key will be used, as it's the most restrictive option.
>Additionally, make sure not to block important pages like your company websites.

### Value

The corresponding value for the key is a list of URLs. You enter all the URLs you want to allow or block as a single value, separated by a pipe **|** character.

Examples: 

- **URL1|URL2|URL3**
- **http://*.contoso.com/*|https://*.bing.com/*|https://expenses.contoso.com**

### URL format for allowed and blocked URLs
Use the following information to learn about the allowed formats and wildcards that you can use when specifying URLs in the allowed and blocked lists:

-   You can use the wildcard symbol (**&#42;**) according to the rules in the following permitted patterns list.

-   Ensure that you prefix all URLs with **http** or **https** when entering them into the list.

-   You can specify port numbers in the address. If you do not specify a port number, the values used will be:

    -   Port 80 for http

    -   Port 443 for https

    Using wildcards for the port number is not supported. For example, **http&colon;//www&period;contoso&period;com:*;** and **http&colon;//www&period;contoso&period;com: /*;** are not supported.

-   Use the following table to learn about the permitted patterns that you can use when you specify URLs:

|URL|Details|Matches|Does not match|
    |-------|---------------|-----------|------------------|
    |http://www.contoso.com|Matches a single page|www.contoso.com|host.contoso.com<br /><br />www.contoso.com/images<br /><br />contoso.com/|
    |http://contoso.com|Matches a single page|contoso.com/|host.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com|
    |http://www.contoso.com/&#42;|Matches all URLs that begin with www.contoso.com|www.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com/videos/tvshows|host.contoso.com<br /><br />host.contoso.com/images|
    |http://&#42;.contoso.com/&#42;|Matches all subdomains under contoso.com|developer.contoso.com/resources<br /><br />news.contoso.com/images<br /><br />news.contoso.com/videos|contoso.host.com|
    |http://www.contoso.com/images|Matches a single folder|www.contoso.com/images|www.contoso.com/images/dogs|
    |http://www.contoso.com:80|Matches a single page, by using a port number|http://www.contoso.com:80||
    |https://www.contoso.com|Matches a single, secure page|https://www.contoso.com|http://www.contoso.com|
    |http://www.contoso.com/images/&#42;|Matches a single folder and all subfolders|www.contoso.com/images/dogs<br /><br />www.contoso.com/images/cats|www.contoso.com/videos|

-   The following are examples of some of the inputs that you cannot specify:

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

## Security and privacy for the Managed Browser

-   On iOS devices, websites that users visit that have an expired or untrusted certificate cannot be opened.

-   The Managed Browser does not use settings that users make for the built-in browser on their devices. This is because the Managed Browser does not have access to these settings.

-   If you configure the option **Require simple PIN for access** or **Require corporate credentials for access** in a mobile application management policy associated with the Managed Browser, and a user selects the help link on the authentication page, they can then browse any Internet sites regardless of whether they were added to a block list in the Managed Browser policy.

-   The Managed Browser can block access to sites only when they are accessed directly. It cannot block access when intermediate services (such as a translation service) are used to access the site.

-   To allow authentication, and to ensure that the Intune documentation can be accessed,**&#42;.microsoft.com** is exempt from the allow or block list settings. It is always allowed.

### Turn off usage data
Microsoft automatically collects anonymous data about the performance and use of the Managed Browser to improve Microsoft products and services. Users can turn off data collection by using the **Usage Data** setting on their devices. You have no control over the collection of this data.


