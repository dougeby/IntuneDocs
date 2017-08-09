---
# required metadata
title: Get data from the Data Warehouse API with a REST client 
description: Retrieve data from the Intune Data Warehouse using a RESTful API.
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: D6D15039-4036-446C-A58F-A5E18175720A

# optional metadata
#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---

# Get data from the Intune Data Warehouse API with a REST client

You can access the Intune Data Warehouse data model through RESTful endpoints. To gain access to your data, your client must authorize with Microsoft Azure Active Directory (Azure AD) using OAuth 2.0. You first set up a native app in Azure, grant permissions to the Intune DataWare House API. Your local client gets authorization, and then can communicate with the Data Warehouse endpoints through the native app.

In this topic we will look at using both Postman, a general-purpose REST tool, and creating an HTTP client in C# to retrieve data form the data warehouse. For more information about postman, see the [Postman](https://www.getpostman.com) site.

The steps to set up a client to get data from the  Data Warehouse API require you to:

 -  Create a client app as a native app in Azure
 -  Grant the client app access to the web app
 -  Create a REST client to get the data

Use the following steps to learn how to authorize and use Postman as a client. Postman is a commonly usd tool troubleshooting and developing REST clients to work with APIs. This topic also includes a C# code sample. The sample provides an example for authorizing a client and getting data from the API.

## Create a native app in Azure

Create a native app in Azure. This native app is the client app. The client
running on your local machine references the Intune Data Warehouse API when the local client requests credentials. 

1.  Click **New app registration**.

![Intune Data Warehouse API](\media\reports-get_rest_data_client_overview.png)

2.  Fill out the app details
 Type a friendly name, such as `Intune Data Warehouse Client`, for the Name.
    -  Select **Native** for the Application type.
    -  Type a URL for the Sign-on URL. The Sign-on URL will depend on the specific scenario, however If you plan on using Postman, type 
     `https://www.getpostman.com/oauth2/callback`. You will use the callback in the client authentication when authenticating to Azure AD.
3.  Click **Create**.
4.  Note the **Application ID** of this app. You will use the ID in the next section.
5.  If you plan on using Postman, add a key. They key is used as the client secret with authentication to Azure AD. To add a key:
    -  Click **Keys** under **API Access** In the Settings blade for the app.
    -  Type a name of your key such as `Client-Secret` for the Description.
    -  Select **1 year** for the Duration.
    -  Click **Save**. Copy the value of your key. You won’t be able to retrieve the key after you close the Settings blade for the Keys.

## Grant the native app access to the web app

You now have an app defined in Azure. Grant access from the native to the Intune Data Warehouse API.

1.  Click the native app. You named the app something such as `Intune Data Warehouse Client`.
2.  Click **Required permissions** from the Settings blade
3.  Click **Add** in the Required permissions blade.
4.  Click **Select an API**.
5.  Search for the web app name. It is named `Microsoft Intune API'.
6.  Click on the app in the list.
7.  Click **Select**.
8.  Check the **Delegated Permissions** box.

![Enable access](\media\reports-get_rest_data_client_access.png)

9.  Click **Select**.
10.  Click **Done**.
11.  Click **Grant Permissions** in the Required permissions blade.
12.  Click **Yes**.

## Get data from the Intune Data Warehouse API with Postman

You can work with the Intune Data Warehouse API with a generic REST client such as Postman. Postman can  provide insight into the features of the API, the underlying OData data model, and troubleshoot your  connection to the API resources. In this section, you can find information about generating an Auth2.0 token for your local client. The client will need the token to authenticate with Azure AD and access the API resources.

### Information you will need to make the call

You need the following information to make a REST call using Postman:

| Attribute        | Description                                                                                                                                                                          | Example                                                                                       |
|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| Callback URL     | Set this as the callback URL in your app settings page.                                                                                                                              | https://www.getpostman.com/oauth2/callback                                                    |
| Token Name       | A string used to pass the credentials to the Azure app. The process generates your token so you can make a call to the Data Warehouse API.                          | Bearer                                                                                        |
| Auth URL         | You can find the your tenant ID in Azure. To find the ID,  open the Portal, choose Active Directory > Properties. Use the Directory ID number. The format looks like XXXXXXX-XXXX-XXXX-XXX-XXXXXXXXXX | https://login.microsoftonline.com/common/oauth2/authorize?resource={URL for your Tenant} |
| Access Token URL | Use the same ID number as the Auth URL.                                                                                                                                              | https://login.microsoftonline.com/common/oauth2/token |
| Client ID        | You created, and noted this when creating the native app in Azure.                                                                                               | 4184c61a-e324-4f51-83d7-022b6a81b991                                                          |
| Client Secret    | You created and noted it when adding a key the client app in Azure.                                                                                              | JZoRZGPmN9xwsUnfX9UW877dkV5Fn/qQClhr7SuyMUQ=                                                  |
| Scope (Optional) | Blank.                                                                                                                                                                               | You can leave this blank.                                                                     |
| Grant Type       | The token is an authorization code.                                                                                                                                                  | Authorization code                                                                            |

You need the endpoint. In this example, we are going to retrieve data from the **dates** entity. The  **dates** entity has the following format:
`https://fef.{aus}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`. You will use your tenant management URL. You used the tenant management URL when creating your web app.

### Make the REST call

To get a new access token for Postman, you must add the Azure AD authorization URL, add your Client ID, and Client Secret. Postman will load the authorization page where you will type your credentials.

Add the information used to request the token.

1.	Download Postman if you do not already have it installed. To download Postman, see [www.getpostman](https://www.getpostman.com).
2.	Open Postman. Choose the HTTP verb **GET**.
3.	Paste the endpoint URL into the address. It should look something like: 
`https://fef.msua06.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`.
4.	Choose the **Authorization** tab, and select **OAuth 2.0** from the Type list.
5.	Click **Get New Access Token**.
6.	Verify that you have already added the Callback URL to your app in Azure. The callback URL is `https://www.getpostman.com/oauth2/callback`.
7.	Type `Bearer` for the Token Name.
8.	Add the **Auth URL**. It should look something like: 
`https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com/'
9.	Add the **Access Token URL**. It should look something like: 
`https://login.microsoftonline.com/common/oauth2/token`
10.	Add the **Client ID** from the native app that you created in Azure and named `Intune Data Warehouse Client`. It should look something like: `4184c61a-e324-4f51-83d7-022b6a81b991`
11.	Add the **Client Secret** that you defined as a key when creating your native app in Azure. It should look something like: `F360R69M0MS72OB6YAqTyXO9MsXZx/OJTgAE2HB4k2k=`
12.	Select **Authorization Code**, and Request access token locally.

![Information for the token](media\reports-postman_getnewtoken.png)

Type your credentials in the Active AD authorization page.

1.	Click **Request Token**.
2.	Type your credentials in the authorization window for your client. The list of Existing Tokens in Postman now contains the token named `Bearer.`
3.	Choose the token. Select **Header** for Add token to.
4.	Click **Use Token**. The list of headers contains the new key value of Authorization and the value `Bearer <your-authorization-token>`

Send the call to the endpoint using Postman

1.	Click **Send**.
2.	The return data appears in the Postman response body.

![Postman 200OK](media\reports-postman_200OK.png)

## Create a REST client (C#) to get data from the Intune Data Warehouse

The following sample contains a simple REST client. The code uses the **httpClient** class from the .Net library. Once the client gains credentials to Azure AD, the client constructs a GET REST call to retrieve the dates entity from the Data Warehouse API.

[!Note]  
You can access the following code [sample on GitHub](https://github.com/Microsoft/Intune-Data-Warehouse/blob/master/Samples/CSharp/Program.cs). Refer to the GitHub repo for the latest changes and updates to the sample.

1.  Open **Microsoft Visual Studio**.
2.  Choose **File** > **New Project**. Expand **Visual C#**, and choose **Console App (.Net Framework)**. 
3.  Name the project ` IntuneDataWarehouseSamples`, browse to where you would like to save the project, and then click **OK**.
3.  Right-click the name of the solution in the Solution Explorer, and then select **Manage NuGet Packages for Solution**. Click **Browse**, and then type `Microsoft.IdentityModel.Clients.ActiveDirectory' in the search box.
4. Choose the package, select the **IntuneDataWarehouseSamples** project under Manage Packages for Your Solution, and then click **Install**. 
5. Click **I Accept** to accept the NuGet package license.
6. Open `Program.cs` from the Solution Explorer.

    ![Project in Visual Studio](\media\reports-get_rest_data_in.png)

7.  Replace the code in Program.cs with the following code:  
    ```csharp
namespace IntuneDataWarehouseSamples
{
    using System;
    using System.Net.Http;
    using System.Net.Http.Headers;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;

    class Program
    {
     static void Main(string[] args)
  {
   /**
    * TODO: Replace the below values with your own.
    * emailAddress - The email address of the user that you will authenticate as.
    *
    * password  - The password for the above email address.
    *    This is inline only for simplicity in this sample. We do not 
    *    recommend storing passwords in plaintext.
    *
    * applicationId - The application ID of the native app that was created in AAD.
    *     For more details, refer to these docs: TODO: ** ADD DOC LINK **
    *
    * warehouseUrl   - The data warehouse URL for your tenant. This can be found in 
    *      the Azure portal. TODO: ** ADD DOC LINK **
    * 
    * collectionName - The name of the warehouse entity collection you would like to 
    *      access.
    */
   var emailAddress = "intuneadmin@yourcompany.com";
   var password = "password_of(intuneadmin@yourcompany.com)";
   var applicationId = "8d699e29-3b54-4c6a-91cc-e537b4680fed";
   var warehouseUrl = "https://fef.msua01.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta";
   var collectionName = "dates";

   var adalContext = new AuthenticationContext("https://login.windows.net/common/oauth2/token");
   AuthenticationResult authResult = adalContext.AcquireTokenAsync(
    resource: "https://api.manage.microsoft.com/",
    clientId: applicationId,
    userCredential: new UserPasswordCredential(emailAddress, password)).Result;

   var httpClient = new HttpClient();
   httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue("Bearer", authResult.AccessToken);

   var uriBuilder = new UriBuilder(warehouseUrl);
   uriBuilder.Path += "/" + collectionName;

   HttpResponseMessage response = httpClient.GetAsync(uriBuilder.Uri).Result;

   Console.Write(response.Content.ReadAsStringAsync().Result);
   Console.ReadKey();
  }
    }
    ```
8.  Update the `TODO`s in the code sample.
8.  Press **Ctrl + F5** to build and execute the Intune.DataWarehouseAPIClient client in Debug mode.

![Date entity retrieved in JSON format.](\media\reports-get_rest_data_output.png)

9.  Review the console output. The output contains data in a JSON format pulled from the **dates** entity in your Intune tenant.

## Next steps

You can find details on authorization, the API URL structure, and OData endpoints in the [Use the Intune Data Warehouse API](reports-api-url.md). 

You can also refer to the Intune Data Warehouse Data Model to find the data entities contained in the API. For more information, see [Intune Data Warehouse API Data Model](reports-ref-data-model.md)