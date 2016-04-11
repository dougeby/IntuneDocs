
---
title: Device is missing a required certificate
ms.reviewer: na
ms.custom: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:
author:
---

# <a name="BKMK_andr_cert_missing"></a>Your device is missing a required certificate
If your device isn’t enrolled in Intune, and it’s missing a certificate that usually comes installed on your phone, you won’t be able to sign in to the Android Company Portal app. When you try to sign in, you’ll see the following message:

![andr-cert-install-cert-missing](./media/andr-cert_install-1-cert_missing.png)

To resolve this issue and get the required certificate:

1.  In a browser, navigate to this [Digicert certificate page](https://www.digicert.com/digicert-root-certificates.htm).

2.  Find and download the Baltimore CyberTrust Root certificate (https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt).

3.  Drag down from the top to open your notifications, and tap **BaltimoreCyberTrustRoot.crt** in the list of notifications.

4.  In the **Name the Certificate** dialog, accept the default certificate name.

5. Ensure that **Credential Use** is set to **Used for VPN and apps**, and then tap **OK**.

   	![andr-cert-install-add-cert-name](./media/andr-cert_install-2-add_cert_name.png)

6. Close the web browser and the Company Portal app.

7. Reopen the Company Portal app. You should now be able to sign in to the Company Portal app. If you need help, contact your IT administrator.