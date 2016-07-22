---
# required metadata

title: Troubleshoot conditional access| Microsoft Intune
description: What to do when your users fail to get access to resources through Intune conditional access. 
keywords:
author: nbigman
manager: arob98
ms.date: 07/21/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 433fc32c-ca9c-4bad-9616-852c72faf996

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Troubleshoot conditional access

This topic describes what to do when your users fail to get access to resources through Intune conditional access. 

### The basics for success in conditional access

In order to conditional access to work, you need the following conditions:

-	The device must be managed by Intune.
-	The user must be registered with Azure Active Directory (AAD)
-	The device must be compliant with the compliance policies you configured in Intune. 
-	EAS must be activated on the device if the user is retrieving mail through the device's native mail client rather than through Outlook.

These conditions can be viewed for each device in the Azure Management Portal and in the device inventory report.





Typically, a user is trying to access email or SharePoint and receives a prompt to enroll. That prompt will lead the user to the company portal. Here are possible explanations for this behavior, and suggested solutions:

## Modern auth scenarios

### Enrollment issues

 -  The device isn't enrolled, so enrollment will resolve the issue.
 -  The user enrolled the device, but the workplace join failed. The user should update the enrollment from the company portal. 
 
### Compliance issues

 -  The device is not compliant with Intune policy. Common issues are encryption and password requirements. The user will be redirected to the company portal, where they can configure their device to be compliant.
 -  For iOS devices, an existing email profile created by the user will block the deployment of a compliant profile (created by the Intune administrator) from Intune. This is a common problem as iOS users will typically create an email profile, then enroll. The company portal will inform the user that they are not compliant due to their manually-configured email profile, and will prompt the user to remove that profile.The user should remove their email profile so that the Intune profile can be deployed. To prevent the problem instruct your users to enroll without installing an email profile and to allow Intune to deploy the profile.  
 -  It may take some time for compliance information to be registered for a device. Wait a few minutes and try again.

### Policy issues

When you create a compliance policy and link it to an email policy, both policies have to be deployed to the same user, so be careful when planning which policies are deployed to which groups. Users that have only one policy applied are likely to find that their devices are not compliant.


## Exchange ActiveSync scenarios


- An Android device that is enrolled and compliant may still get a quarantine notice when trying to access corporate resources. Before choosing the link that says **Begin**, the user should ensure that the company portal was not open when they tried to access the resources. The users should close the company portal, try again to access the resources, and then choose the **Begin** link.

- A retired device may continue to have access for several hours after retirement. This is because Exchange caches access rights for 6 hours. Consider other means of protecting data on retired devices in this scenario.
- Possible issue, can’t patch the EASID to AAD. A common cause of this issue is throttling, so wait a few minutes and try again. 

## Collecting OWA mailbox logs

If your Exchange connectivity issues persist after you troubleshoot your deployment, collect the OWA mailbox logs before contacting Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

1. Log on through OWA and choose the settings (gear) symbol next to your name in the upper right corner. 
2. Choose **Options**
3. Choose **Phone** (may say **Mobile Devices**) in the  column on the left side.
4. From the top menu, choose **Mobile Devices**. 
5. Choose your device from the list and then choose **Start Logging**. 
6. When prompted, choose **Yes** on the pop-up dialog. 
7. Perform the action that caused the issue, so that you can reproduce it. 
8. Wait 1-2 minutes then go back to the phone list in OWA (make sure your phone is selected in the list) and from the top menu choose **Retrieve Log**. 
9. You should now have an email from yourself with an attachment. When you open a support ticket, provide the contents of the email to Microsoft Support.


### Next steps
If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
