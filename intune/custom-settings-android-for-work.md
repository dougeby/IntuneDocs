---
# required metadata

title: Intune custom profile settings for Android for Work
titlesuffix: "Azure portal"
description: Learn how to create Intune custom profile settings for Android for Work devices."
keywords:
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Create Intune custom profile settings for Android for Work devices

Use the Intune Android for Work custom configuration policy to assign OMA-URI settings that can be used to control features on Android for Work devices. These are standard settings that many mobile device manufacturers use to control device features.

This capability is intended to allow you to assign Android settings that are not configurable with Intune policies. Intune supports a limited number of Android custom policies at present. See the examples in this topic to find out which policies you can configure.

## Create a custom profile

1. Use the instructions in [How to configure custom device settings](custom-settings-configure.md) to get started.
2. On the **Custom OMA-URI Settings** blade, choose **Add** to add a new setting.
3. On the **Add Row** blade, configure the following:
	- **Name** - Enter a unique name for the Android for work custom settings to help you identify it in the Azure portal.
	- **Description** - Provide a description that gives an overview of the Android custom policy and other relevant information that helps you to locate it.
	- **OMA-URI** - Enter the OMA-URI you want to supply a setting for.
	- **Data type** - Select the data type in which you will specify this OMA-URI setting. Choose from **String**, **String (XML file)**, **Date and time**, **Integer**, **Floating point**, **Boolean**, or **Base64 (file)**.
	- **Value** - Specify the value to associate with the OMA-URI that you specified previously. The method you use to supply this value will vary according to the data type you selected. For example, if you chose **Date and time**, you'll select the value from a date picker.
4. When you have finished, choose OK to return to the **Custom OMA-URI Settings**, and then add more settings, or choose **Create** to create the custom profile.


## Example

In this example, you'll create a custom profile that can be used to restrict whether copy and paste actions between work and personal apps are allowed on managed Android for Work devices.

1. Use the procedure in this topic to create a custom profile for Android for Work devices using the following values:
	- **Name** - Enter "Block copy and paste" or text of your own choosing.
	- **Description** - Enter "Blocks copy/paste between work and personal apps" or text of your own choosing.
	- **OMA-URI** - Enter **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste**.
	- **Data type** - Select **Boolean** to indicate that the value for this OMA-URI is either **True** or **False**.
	- **Value** - Select **True**.
2. You should end up with a setting looking similar to this image.
![Block copy and paste for Android for Work.](./media/custom-policy-afw-copy-paste.png)
3. Now, when you assign this custom profile to Android for Work devices you manage, copy and paste will be blocked between apps in the work, and personal profiles.