---
# required metadata

title: Get an Apple MDM Push certificate | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn the steps for getting an Apple MDM Push certificate."
keywords:
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Get an Apple MDM Push certificate

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune enables mobile device management (MDM) of iPads, iPhones, and Mac OS X devices and gives users access to company email and apps. An Apple Push Notification service (APNs) certificate is required for Intune to manage iOS and Mac devices. After you add the certificate to Intune, your users can install the Company Portal app to enroll their devices, or you can set up corporate-owned iOS device management.

**To get the MDM Push certificate:**<br>
Open the **Enrollment** blade, choose **Apple MDM Push Certificate**, and then follow the numbered steps in the Azure portal, which are shown below.

**Step 1. Download the Intune certificate signing request required to create an Apple MDM push certificate.**<br>
Select **Download your CSR** to download and save the .csr file locally. The .csr file is used to request a trust relationship certificate from the Apple Push Certificates Portal.

**Step 2. Create an Apple MDM push certificate.**<br>
Select **Create your MDM push Certificate** to go to the Apple Push Certificates Portal. Sign in with your company Apple ID to create the push certificate certificate by using the .csr file. After choosing **Upload** on Apple's Push Certificate Portal, you will receive a .json file. Do use this file for the push certificate. Complete the download, return to the Apple Push Certificates Portal for Certificates for Third-Party Servers, and then choose **Download**. Download the push certficate (.pem file), and save the file locally.
Note

**Step 3. Enter the Apple ID used to create your Apple MDM push certificate. **

**Step 4. Browse to your Apple MDM push certificate to upload.**<br>
Go to the certificate (.pem) file, choose **Open**, and then choose **Upload**. With the push certificate, Intune can enroll and manage iOS devices by pushing policy to enrolled mobile devices.
