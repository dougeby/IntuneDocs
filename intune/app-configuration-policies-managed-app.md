---
# required metadata

title: Add app configuration policies for managed apps without device enrollment | Microsoft Docs 
titlesuffix: "Azure portal"
description: Learn how to use app configuration policies to provide configuration data to an iOS app when it is run."
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/15/2106/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: DFCD9BDB-376A-48FF-8A3B-E62FEA9DA939

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Add app configuration policies for managed apps without device enrollment

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Summary

1. Sign in to the Azure portal.
2. Choose **More Services** > **Monitoring + Management** + **Intune**.
3. Choose **Mobile apps** > **App configuration polices** in the Manager group.
4. Click **Add**.
5. Type the configuration policy Name.
6. Type the configuration policy Description.
7. Select Manage apps for device enrollment type.
8. Select Associated App to choose the app for which you want to define a configuration policy. Select the app from the list of apps that you have approved and synchronized with Intune.
9. For each configuration settings supported by the app, type the **Name** and **Value**, and click the ellipse (…). Intune App SDK-enabled apps support configurations in key-value pairs. Consult the documentation for each app to learn more about which key-value configurations are supported.


## Properties using Tokens

Intune supports the following data types in a property list:

- &lt;integer&gt;
- &lt;real&gt;
- &lt;string&gt;
- &lt;array&gt;
- &lt;dict&gt;
- &lt;true /&gt; or &lt;false /&gt;

For more information about data types, see [About Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) in the iOS Developer Library.

Additionally, Intune supports the following token types in the property list:
- \{\{userprincipalname\}\} - (Example: **John@contoso.com**)
- \{\{mail\}\} - (Example: **John@contoso.com**)
- \{\{partialupn\}\} - (Example: **John**)
- \{\{accountid\}\} - (Example: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} - (Example: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} - (Example: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} - (Example: **John Doe**)
- \{\{serialnumber\}\} - (Example: **F4KN99ZUG5V2**) for iOS devices
- \{\{serialnumberlast4digits\}\} - (Example: **G5V2**) for iOS devices

The \{\{ and \}\} characters are used by token types only and must not be used for other purposes.

## Next steps

Continue to [assign](apps-deploy.md) and [monitor](apps-monitor.md) the app as usual.