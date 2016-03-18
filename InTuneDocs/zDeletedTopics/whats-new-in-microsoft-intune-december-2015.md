---
title: What's new - December 2015 | Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid:
author: Lindavr
---
# What's new in Microsoft Intune

## December 2015
### Changes and updates to Microsoft Company Portal
The following changes have been made to the Company Portal in this release.

**Android Company Portal app**

The following changes have been made to comply with new Google requirements. On Android 6.0 and above devices, two new messages are displayed to users:
* Allow Company Portal to make and manage phone calls?
* Allow Company Portal to access photos, media, and files on your device?

See the following tables for details about these two messages.



Message text  |Allow Company Portal to make and manage phone calls?  
---------|---------
Meaning of message     |  Enables the user's device phone number and IMEI to be sent to the Intune service and appear in the Admin console on the Hardware page.   </br></br>**NOTE: The Company Portal app never makes or manages phone calls!** The message text is controlled by Google and cannot be changed. </br></br>To see the **Hardware** page, go to **Groups** > **All mobile devices** > **Device**s. Select the user's device, and go to **View Properties** > **Hardware**.    
Where and when message appears  | The message appears when users sign in to the Company Portal app for the first time to start enrolling their device.|         
What happens if users allow access  |  The device's phone number and IMEI will appear on the Hardware page in the Admin console. |         
What happens if users deny access     | They can continue to use the Company Portal app and enroll their device, but the users's device phone number and IMEI will be blank on the Hardware page in the Admin console.       </br></br> The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select so that the message never shows again.</br></br>If users allow but then later deny access, the message appears the next time users sign in to the Company Portal app after enrollment.</br></br>If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Phone**, and then turn on the permission.
More information     |  For your users: [Sign in to the Company Portal](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_signin_cp)  </br></br>For IT Pros: The information in this table is also in [Helping your users understand Company Portal app messages](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   

Message text  |Allow Company Portal to access photos, media, and files on your device?  
---------|---------
Meaning of message     |  Enables the device to write data logs to the device's SD card, which enables logs to be moved by using a USB cable.   </br></br>**NOTE: The Company Portal app never accesses users' photos, media, and files!** The message text is controlled by Google and cannot be changed.     
Where and when message appears  | The message appears when users tap **Send Data** to send data logs to their IT admin.|         
What happens if users allow access  |  The logs will be copied to the SD card. |         
What happens if users deny access     | They can still send data logs, but the logs won't be copied to the device's SD card.       </br></br> The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select so that the message never shows again.</br></br>If users allow but then later deny access, the message appears the next time users try to send logs.</br></br>If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Storage**, and then turn on the permission.
More information     |  For your users: [Send diagnostic data logs to your IT admin using email](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_send_diag_logs)  </br></br>For IT Pros: The information in this table is also in [Helping your users understand Company Portal app messages](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   




**iOS Company Portal app**
* Users can now use Microsoft Outlook or other mail apps to send diagnostic logs to the IT administrator. Previously, only the native app could be used.
* Support has been improved for Apple's Device Enrollment Program (DEP) and corporate-enrolled devices. For details, see [You are asked to identify your device when you're trying to enroll](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device).
* In the user's list of enrolled devices, a green check mark now appears next to the device that the user is currently using. Before this check mark was added, users couldn't tell which enrolled device they were using.

**Windows Company Portal app**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.-->


### See also
* [Start using Microsoft Intune](start-using-microsoft-intune.md)
* [Microsoft Intune TechNet Library](http://go.microsoft.com/fwlink/?LinkID=247636)
* [Microsoft Intune Product Information](http://go.microsoft.com/fwlink/?LinkID=249135)
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
