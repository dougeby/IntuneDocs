---
# required metadata

title: Manage web access with the Managed Browser app 
titlesuffix: "Azure portal"
description: Deploy the Managed Browser application to restrict web browsing and the transfer of web data to other apps."
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/10/2017
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

# Manage Internet access using Managed Browser policies with Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The Managed Browser is a web browsing app that you can download from public app stores for use in your organization. When configured with Intune, the Managed Browser can be:
- Used to access corporate sites and SaaS apps with Single Sign-On via the MyApps service, while keeping web data protected.
- Pre-configured with a list of URLs and domains to restrict which sites the user can navigate to in the corporate context.
- Pre-configured with a homepage, and bookmarks you specify.

Because this app has integration with the Intune SDK, you can also apply app protection policies to it, including:
- Controlling the use of cut, copy, and paste
- Preventing screen captures
- Ensuring that links to content that users select open only in other managed apps.

For details, see [What are app protection policies?](/intune/app-protection-policy)

You can apply these settings to devices that are enrolled with Intune, enrolled with another device management product, or to devices that are not managed.

If users install the Managed Browser from the app store and Intune does not manage it, it can be used as a basic web browser, with support for Single Sign-On through the Microsoft MyApps site. Users are taken directly to the MyApps site, where they can see all of their provisioned SaaS applications.
While the Managed Browser is not managed by Intune, it cannot access data from other Intune-managed applications. 

The Managed Browser does not support the Secure Sockets Layer version 3 (SSLv3) cryptographic protocol.

You can create Managed Browser policies for the following device types:

-   Devices that run Android 4 and later

-   Devices that run iOS 8.0 and later

>[!IMPORTANT]
>As of October 2017, the Intune Managed Browser app on Android app supports only devices running Android 4.4 and later. The Intune Managed Browser app on iOS will support only devices running iOS 9.0 and later.
>Earlier versions of Android and iOS will be able to continue using the Managed Browser, but will be unable to install new versions of the app and might not be able to access all of the app capabilities. We encourage you to update these devices to a supported operating system version.


The Intune Managed Browser supports opening web content from [Microsoft Intune application partners](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx).

## Create a Managed Browser app configuration

1.	Sign into the Azure portal.
2.	Choose **More Services** > **Monitoring + Management** > **Intune**.
3.	On the **Mobile apps** blade of the Manage list, choose **App configuration policies**.
4.	On the **App Configuration policies** blade, choose **Add**.
5.	On the **Add app configuration** blade, enter a **Name**, and optional **Description** for the app configuration settings.
6.	For **Device enrollment** type, choose **Managed devices** or **Managed apps**.
7.	Choose **Select the required apps** and then, on the **Targeted apps** blade, choose the **Managed Browser** for iOS, for Android, or for both.
8.	Choose **OK** to return to the **Add app configuration** blade.
9.	Choose **Configuration Settings**. On the **Configuration** blade, you define key and value pairs to supply configurations for the Managed Browser. Use the sections later in this article to learn about the different key and value pairs you can define.
10.	When you are done, choose **OK**.
11.	On the **Add app configuration** blade, choose **Create**.
12.	The new configuration is created, and displayed on the **App configuration** blade.

>[!IMPORTANT]
>Currently, the Managed Browser relies on auto-enrollment. For app configurations to apply, another application on the device must already be managed by Intune app protection policies.

## Assign the configuration settings you created

You assign the settings to Azure AD groups of users. If that user has the Managed Browser app installed, then the app is managed by the settings you specified.

1. On the **Settings** blade of the Intune mobile application management dashboard, choose **App configuration**.
2. From the list of app configurations, select the one you want to assign.
3. On the next blade, choose **User Groups**.
4. On the **User groups** blade, select the Azure AD group to which you want to assign the app configuration, and then choose **OK**.


## How to configure Application Proxy settings for the Managed Browser

The Intune Managed Browser and [Azure AD Application Proxy]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) can be used together to support the following scenarios for users of iOS and Android devices:

- A user downloads and signs in to the Microsoft Outlook app. Intune app protection policies are automatically applied. They encrypt saved data and block the user from transferring corporate files to unmanaged apps or locations on the device. When the user then clicks a link to an intranet site in Outlook, you can specify that the link opens in the Managed Browser app, rather than another browser. The Managed Browser recognizes that this intranet site has been exposed to the user through the Application Proxy. The user is automatically routed through the Application Proxy, to authenticate with any applicable multi-factor authentication, and conditional access before reaching the intranet site. This site, which could previously not be found while the user was remote, is now accessible and the link in Outlook works as expected.
- A remote user opens the Managed Browser application and navigates to an intranet site using the internal URL. The Managed Browser recognizes that this intranet site has been exposed to the user via the Application Proxy. The user is automatically routed through the Application Proxy, to authenticate with any applicable multi-factor authentication, and conditional access before reaching the intranet site. This site, which could previously not be found while the user was remote, is now accessible.

### Before you start

- Set up your internal applications through the Azure AD Application Proxy.
	- To configure Application Proxy and publish applications, see the [setup documentation]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started#how-to-get-started). 
	- You must be using minimum version 1.2.0 of the Managed Browser app.
	- Users of the Managed Browser app have an [Intune app protection policy]( app-protection-policy.md) assigned to the app.

#### Step 1: Enable automatic redirection to the Managed Browser from Outlook
Outlook must be configured with an app protection policy that enables the setting **Restrict web content to display in the Managed Browser**.

#### Step 2: Assign an app configuration policy assigned for the Managed Browser.
This procedure configures the Managed Browser app to use app proxy redirection. Using the procedure to create a Managed Browser app configuration, supply the following key and value pair:

|||
|-|-|
|Key|Value|
|**com.microsoft.intune.mam.managedbrowser.AppProxyRedirection**|**true**|


## How to configure the homepage for the Managed Browser

This setting allows you to configure the homepage that users see when they start the Managed Browser or create a new tab. Using the procedure to create a Managed Browser app configuration, supply the following key and value pair:

|||
|-|-|
|Key|Value|
|**com.microsoft.intune.mam.managedbrowser.homepage**|Specify a valid URL. Incorrect URLs are blocked as a security measure.<br>Example: **https://www.bing.com**|


## How to configure bookmarks for the Managed Browser

This setting allows you to configure a set of bookmarks that is available to users of the Managed Browser.

- These bookmarks cannot be deleted or modified by users
- These bookmarks display at the top of the list. Any bookmarks that users create are displayed below these bookmarks.
- If you have enabled App Proxy redirection, you can add App Proxy web apps using either their internal or external URL.

Using the procedure to create a Managed Browser app configuration, supply the following key and value pair:

|||
|-|-|
|Key|Value|
|**com.microsoft.intune.mam.managedbrowser.bookmarks**|The value for this configuration is a list of bookmarks. Each bookmark consists of the bookmark title, and the bookmark URL. Separate the title, and URL with the **&#124;** character.<br><br>Example: **Microsoft Bing&#124;https://www.bing.com**<br><br>To configure multiple bookmarks, separate each pair with the double character, **&#124;&#124;**<br><br>Example: **Bing&#124;https://www.bing.com&#124;&#124;Contoso&#124;https://www.contoso.com**|

## How to specify allowed and blocked URLs for the Managed Browser

Using the procedure to create a Managed Browser app configuration, supply the following key and value pair:

|||
|-|-|
|Key|Value|
|Choose from:<br><br>- Specify allowed URLs (only these URLs are allowed; no other sites can be accessed): **com.microsoft.intune.mam.managedbrowser.AllowListURLs**<br><br>- Specify blocked URLs (all other sites can be accessed): <br><br>**com.microsoft.intune.mam.managedbrowser.BlockListURLs**|The corresponding value for the key is a list of URLs. You enter all the URLs you want to allow or block as a single value, separated by a pipe **&#124;** character.<br><br>Examples:<br><br>-**URL1&#124;URL2&#124;URL3**<br>-**http://*.contoso.com/*&#124;https://*.bing.com/*&#124;https://expenses.contoso.com**|

>[!IMPORTANT]
>Do not specify both keys. If both keys are targeted to the same user, the allow key is used, as it's the most restrictive option.
>Additionally, make sure not to block important pages like your company websites.

### URL format for allowed and blocked URLs
Use the following information to learn about the allowed formats and wildcards that you can use when specifying URLs in the allowed and blocked lists:

-   You can use the wildcard symbol (**&#42;**) according to the rules in the following permitted patterns list:

-   Ensure that you prefix all URLs with **http** or **https** when entering them into the list.

-   You can specify port numbers in the address. If you do not specify a port number, the values used are:

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
|http://www.contoso.com:80|Matches a single page, by using a port number|http://www.contoso.com:80|
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

-   The Managed Browser does not use settings that users make for the built-in browser on their devices. The Managed Browser cannot access to these settings.

-   If you configure the option **Require simple PIN for access** or **Require corporate credentials for access** in an app protection policy associated with the Managed Browser, and a user selects the help link on the authentication page, they can browse any Internet sites regardless of whether they were added to a block list in the policy.

-   The Managed Browser can block access to sites only when they are accessed directly. It does not block access when intermediate services (such as a translation service) are used to access the site.

-   To allow authentication, and access to Intune documentation, **&#42;.microsoft.com** is exempt from the allow or block list settings. It is always allowed.

### Turn off usage data
Microsoft automatically collects anonymous data about the performance and use of the Managed Browser to improve Microsoft products and services. Users can turn off data collection by using the **Usage Data** setting on their devices. You have no control over the collection of this data.


-   On iOS devices, websites that users visit that have an expired or untrusted certificate cannot be opened.
-   The Managed Browser does not use settings that users make for the built-in browser on their devices. The Managed Browser cannot access to these settings.

-   If you configure the option **Require simple PIN for access** or **Require corporate credentials for access** in an app protection policy associated with the Managed Browser, and a user selects the help link on the authentication page, they can browse any Internet sites regardless of whether they were added to a block list in the policy.

-   The Managed Browser can block access to sites only when they are accessed directly. It does not block access when intermediate services (such as a translation service) are used to access the site.

-   To allow authentication, and access to Intune documentation, **&#42;.microsoft.com** is exempt from the allow or block list settings. It is always allowed.

### Turn off usage data
Microsoft automatically collects anonymous data about the performance and use of the Managed Browser to improve Microsoft products and services. Users can turn off data collection by using the **Usage Data** setting on their devices. You have no control over the collection of this data.
