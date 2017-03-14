---
# required metadata

title: Manage devices with Intune
titleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn how to view the devices you manage with Intune, and perform various operations on them."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/14/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: ilwu
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# What is Microsoft Intune device management? 


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

The **Devices** workload gives you insights into the devices you manage, and lets you perform remote tasks on those devices. To access the workload:

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Devices**.

Now, choose one of the following:

- **Overview** Get information about devices you've enrolled, and the operating systems each device runs.
- **Manage** - Choose **All Devices** to see a list of all the devices you manage.
	Select one of those devices in the list to open the <*device name*> **Overview** blade where you can select one of:
	- **Overview**  - See general information about the device including information about it's name, the owner, whether it is a BYOD device, when it last checked-in, and more. 
				
	- **Hardware** - See more detailed information about the device including it's free storage space, model and manufacturer, and more.
	![Managed device hardware inventory](./media/hardware-inventory.png)
	- **Detected Applications** - Displays a list of all apps that Intune found installed on the device.
	![Detected applications node](./media/detected-applications.png)
- **Monitor** Choose **Device Actions** to see a list of device actions that have been performed on devices you manage and the current state of those actions.
![Monitor device actions](./media/monitor-device-actions.png)
- **Help and Support** - Displays links to troubleshooting and support documentation.

## Available device actions

Additionally, you can perform the following remote actions on the device (not all actions are supported by all device platforms):

### **Remove company data**
Removes only company data managed by Intune. Does not remove personal data from the device. The device will no longer be managed by Intune, and will no longer be able to access corporate resources (not supported for Windows devices that are joined to Azure Active Directory).

### **Factory reset**
Returns the device to its default settings. The device will no longer be managed by Intune and both company and personal data are removed. You cannot undo this action.

### **Remote lock**
Locks the device. The device owner must use their passcode to unlock it. You can only remotely lock a device that has a PIN or password set.

### **Reset passcode**
Generates a new passcode for the device which will be displayed on the <*device name*> **Overview** blade.

### **Bypass Activation Lock**
This will remove the activation lock from an iOS device without the user’s Apple ID and password. Once you bypass the activation lock, the device turns on activation lock again when the Find My iPhone app launches. Only bypass the activation lock if you have physical access to the device.

### **Lost mode**
If an iOS device has been lost or stolen, you can enable lost mode. This lets you specify a message and a phone number that will be displayed on the lock screen of the device. To do this:
1.	On the properties blade for an iOS device, choose **More** > **Lost mode**.
2.	On the **Lost mode** blade, enable lost mode, enter the message that will be displayed, and optionally, a contact phone number.
3.	Click **OK**.
When you enable lost mode, you block all use of the device. The end user cannot access the device until you disable lost mode. While lost mode is enabled, you can use the **Locate device** action to find out where the device is.

### **Locate device**
Use this remote action to display the location of a lost or stolen iOS device on a map. The device must be a corporate-owned iOS device that is in supervised mode. Before you use this action, the device must have been placed into lost mode.
1.	On the properties blade for an iOS device, choose **More** > **Locate device**.
2.	After the device has been located, it's location is displayed on the **Locate device** blade. 
	![Locate device blade](./media/locate-device.png)

### **Restart**
Causes the device to restart. The device owner is not automatically notified of the restart, therefore might lose work.


## Security and privacy information for the lost mode and locate device actions
- No device location information is sent to Intune until you turn this action on.
- When you use the locate device action, the latitude and longitude coordinates of the device are sent to Intune, and displayed in the Azure portal.
- The data is stored for 24 hours, then removed. You cannot manually remove the location data.
- Location data is encrypted, both while stored, and while being transmitted.
- When you configure lost mode, we recommend that the message you enter that is displayed on the lock screen includes information that the device location can be determined.
