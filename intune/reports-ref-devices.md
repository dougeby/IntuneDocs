---
# required metadata
title: Devices | Microsoft Docs  
description: Reference topic for the Devices category of entity collections in the Intune Data Warehouse API.
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6955E12D-70D7-4802-AE3B-8B276F01FA4F

# optional metadata
#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---

# Reference for devices entities

The **Devices** category contains entities for mobile devices that track information such as:

  -  Device type
  -  Device enrollment and registration status
  -  Device ownership
  -  Device management state
  -  Device membership to Azure AD status
  -  Enrollment status
  -  Historic information about the device
  -  Inventory of apps on the device

## DeviceTypes

The **DeviceTypes** entity represents the device type referenced by other data warehouse entities. The device type typically describes either the device model, manufacturer, or a combination of both.

| Property  | Description |
|---------|------------|
| DeviceTypeID |Unique identifier of the device type |
| DeviceTypeKey |Unique identifier of the device type in the data warehouse - surrogate key |
| DeviceTypeName |Device type |

## Example

| deviceTypeID  | Name | Description |
|---------|------------|--------|
| 0 |Desktop |Windows Desktop device |
| 1 |WindowsRT |WindowsRT device |
| 2 |WinMO6 |Windows Mobile 6.0 device |
| 3 |Nokia |Nokia device |
| 4 |WindowsPhone |Windows Phone device |
| 5 |Mac |Mac device |
| 6 |WinCE |Windows CE device |
| 7 |WinEmbedded |Windows Embedded device |
| 8 |IPhone |iPhone device |
| 9 |IPad |iPad device |
| 10 |IPod |iPod device |
| 11 |Android |Android device-managed using Device Administrator |
| 12 |ISocConsumer |iSoc Consumer device |
| 14 |MacMDM |Mac OS X device managed with the built-in MDM agent |
| 15 |HoloLens |Holo Lens device |
| 16 |SurfaceHub |Surface Hub device |
| 17 |AndroidForWork |Android device-managed using Android for Work Profile Owner |
| 100 |Blackberry |Blackberry Device |
| 101 |Palm |Palm device |
| 255 |Unknown |Unknown device type |

## ClientRegistrationStateTypes

The **ClientRegistrationStateTypes** entity represents the registration type referenced by other data warehouse tables.

| Property  | Description |
|---------|------------|
| clientRegisterationStateID |Unique identifier for registration state |
| clientRegisterationStateKey |Unique identifier of the registration state in the data warehouse - surrogate key |
| clientRegisterationStateName |Registration state |

## Example

| ClientRegisterationStateID  | Name | Description |
|---------|------------|--------|
| 0 |NotRegistered |Not registered |
| 1 |SMSIDConflict |SMS ID conflict |
| 2 |Registered |Registered |
| 3 |Revoked |State means the IT administrator has blocked the client, and the client can be unblocked. A device can also be in the Revoked state after it is wiped or retired. |
| 4 |KeyConflict |Key conflict |
| 5 |ApprovalPending |Approval pending |
| 6 |ResetCert |Reset certificate |
| 7 |NotRegisteredPendingEnrollment |Not registered pending enrollment |
| 8 |Unknown |Unknown state |

## EnrollmentTypes

The **EnrollmentTypes** entity indicates how a device was enrolled. The enrollment type captures the method of enrollment. Examples list the different enrollment types and what they mean.

| Property  | Description |
|---------|------------|
| managementStateID |Unique identifier of the management state. |
| managementStateKey |Unique identifier of the management state in the data warehouse - surrogate key. |
| managementStateName |Indicates the state of the remote action applied to this device. |

## Example

| enrollmentTypeID  | Name | Description |
|---------|------------|--------|
| 0 |Unknown |Enrollment type was not collected |
| 1 |UserEnrollment |User initiated enrollment |
| 2 |DeviceEnrollment |Device enrollment with user-less profile |
| 3 |DeviceEnrollmentWithUDA |Device enrollment with UDA profile. |
| 4 |AzureDomainJoined |User initiated device enrollment through Azure Active Directory |
| 5 |UserEnrollmentWithServiceAccount |User initiated enrollment through service account |
| 6 |DepDeviceEnrollment |DEP Device enrollment with user-less profile |
| 7 |DepDeviceEnrollmentWithUDA |DEP Device enrollment with UDA profile |
| 8 |AutoEnrollment |Combined DRS and MDM Enrollment for BYOD scenario |

## OwnerTypes

The **EnrollmentTypes** entity indicates whether a device is corporate, personally owned, or unknown.

| Property  | Description | Example |
|---------|------------|--------|
| ownerTypeID |Unique identifier of the owner type | |
| ownerTypeKey |Unique identifier of the owner type in the data warehouse - surrogate key | |
| ownerTypeName |Represents the owner type of the devices:  Company - device is enterprise owned. Personal - device is personally owned (BYOD).  Unknown - no information on this device. |Company Personal Unknown |

## MdmStatuses

The **MdmStatuses** entity indicates compliance state of the device.

| Property  | Description | Example |
|---------|------------|--------|
| MdmStatusName |MdmStatus Identifier |0 - Unknown 1 - Compliant 2 - Not Compliant |
| MdmStatusKey |Unique identifier of compliance state in the data warehouse - surrogate key | |

## ManagementStates

The **ManagementStates** entity provides details on the state of the device. Detail can be useful in the cases where remote actions are applied, the device is jailbroken, or rooted.

| Property  | Description |
|---------|------------|
| managementStateID |Unique identifier of the management state |
| managementStateKey |Unique identifier of the management state in the data warehouse - surrogate key |
| managementStateName |Indicates the state of the remote action applied to this device. |

## Example

| managementStateID  | Name | Description |
|---------|------------|--------|
| 0 |Managed |Managed with no pending remote actions. |
| 1 |RetirePending |There is a retire command pending for the device. |
| 2 |RetireFailed |The retire command failed on the device. |
| 3 |WipePending |There is a wipe command pending for the device. |
| 4 |WipeFailed |The wipe command failed on the device. |
| 5 |Unhealthy |Unhealthy state |
| 6 |DeletePending |There is a delete command pending for the device. |
| 7 |RetireIssued |A retire command has been issued to the device. |
| 8 |WipeIssued |A wipe command has been issued. |
| 9 |WipeCanceled |Wipe command has been canceled. |
| 10 |RetireCanceled |Retire command has been canceled. |
| 11 |Discovered |The device is newly discovered by Intune, once it checks in for the first time it moves to -Managed- state |

## WorkPlaceJoinStateTypes

The **WorkPlaceJoinStateTypes** entity represents the Azure Active Directory Workplace Join state of the device.  The enrollment workflow can use one or more certificates to verify or authenticate. When a device WorkPlace enrolls, these certificates  are used to validate the device and the user. The issuance of certificates is provided through a SCEP (Simple Certificate Enrollment Point) server. The values in The entity indicate various states that a device could be in as it goes through this process. Some of these states include WorkPlace join failing due to the issuance of a required certificate (from a SCEP server) failing. If a device never went through this workflow, the value is set to Unknown.

| Property  | Description |
|---------|------------|
| WorkPlaceJoinStateID |Unique identifier of the work place join state |
| WorkPlaceJoinStateKey |Unique identifier of the work place join state in the data warehouse - surrogate key |
| WorkPlaceJoinStateName |Work place join state |

## Example

| workPlaceJoinStateID  | Name | Description |
|---------|------------|--------|
| 0 |Unknown |If a device is not workplace joined, it is in the Unknown state |
| 1 |Succeeded |Successfully workplace joined |
| 2 |FailureToGetScepMetadata |Failure to get SCEP metadata |
| 3 |FailureToGetScepChallenge |Failure to get SCEP challenge |
| 4 |DeviceFailureToInstallScepCommand |Failure to install SCEP command on device |
| 5 |DeviceFailureToGetCertificate |Device failed to get certificate through SCEP |
| 6 |DeviceScepPending |Pending state; device is still doing SCEP |
| 7 |DeviceScepFailed |Device failed to install certificate through SCEP |
| 8 |AADValidationFailed |Failed to validate device exists on AAD |

## ManagementAgentTypes

The **ManagementAgentTypes** entity represents the agents used to manage a device.

| Property  | Description |
|---------|------------|
| ManagementAgentTypeID |Unique identifier of the management agent type |
| ManagementAgentTypeKey |Unique identifier of the management agent type in the data warehouse - surrogate key |
| ManagementAgentTypeName |Indicates what kind of agent is used to manage the device. |

## Example

| ManagementAgentTypeID  | Name | Description |
|---------|------------|--------|
| 1 |EAS |The device is managed through Exchange Active Sync |
| 2 |MDM |The device is managed using an MDM agent |
| 3 |EasMdm |The device is managed by both Exchange Active Sync and an MDM agent |
| 4 |IntuneClient |The device is managed by the Intune PC agent |
| 5 |EasIntuneClient |The device is managed by both Exchange Active Sync and the Intune PC agent |
| 8 |ConfigManagerClient |The device is managed by the System Center Configuration Manager agent |
| 16 |Unknown |Unknown management agent type |

## Devices

The **Devices** entity lists all enrolled devices under management and their corresponding properties.

| Property  | Description |
|---------|------------|
| DeviceKey |Unique identifier of the device in the data warehouse - surrogate key |
| DeviceId |Unique identifier of the device |
| DeviceName |Name of the device on platforms that allow naming a device. On other platforms, Intune creates a name from other properties. This attribute cannot be available for all devices. |
| DeviceTypeKey |Key of the device type attribute for this device |
| ClientRegisterationStateKey |Key of the client registration state attribute for this device |
| OwnerTypeKey |Key of the owner type attribute for this device: corporate, personal, or unknown. |
| objectSourceKey |Ignore this column. |
| CreatedDate |Date the device was enrolled on |
| LastContact |Last known device check-in with Intune |
| LastContactNotification |Last time Intune notified the device to check in with Intune |
| LastContactWorkplaceJoin |The timestamp indicating last known Workplace Join state for this device. |
| ManagementAgentKey |Key of the management agent associated with this device. |
| ManagementStateKey |Key of the management state associated with this device, indicating latest state of a remote action or if it was jailbroken/rooted. |
| ReferenceId |The device-s ID in Azure Active Directory |
| WorkPlaceJoinStateKey |Key of the workplace join state associated with this device. |
| CategoryId |Ignore this column. |
| EnrollmentTypeKey |Key of the enrollment type associated with this device, indicating method of enrollment. |
| CertExpirationDate |Expiry date of the MDM management certificate. |
| MdmStatusKey |A key to MdmStatus |
| OSFamily |OS Family (Windows, iOS, Android, etc.) |
| OSVersion |OS version |
| OSMajorVersion |Major version component of the OS version (major.minor.build.revision) |
| OSMinorVersion |Minor version component of the OS version (major.minor.build.revision) |
| OSBuildNumber |Build version component of the OS version (major.minor.build.revision) |
| OSRevisionNumber |Revision version component of the OS version (major.minor.build.revision) |
| EasID |This devices EAS ID, if the device is managed by Exchange Active Sync. |
| GraphDeviceIsManaged |The last management status that Intune set in AAD |
| GraphDeviceIsCompliant |The last compliance state that Intune set in AAD |
| SerialNumber |Serial number of the device, if available |
| EnrolledByUser |The ID of user who enrolled this device that references the userId column in User table. |
| RowLastModifiedDateTimeUTC |Last time this record was modified. |
| ProcessorArchitecture |Processor architecture |
| DeviceAction |Last device action issued, Ignore for now. |
| Manufacturer |Manufacturer of the device |
| Model |Model of the device |
| LastPolicyUpdateUtc |Latest time when policy was updated on the device |
| LastExchangeStatusUtc |Last time the device synced with exchange. |
| IsDeleted |Set to True if the device is not managed by Intune anymore. Preserves the last known state. |

## DevicePropertyHistory

The **DevicePropertyHistory** entity has the same properties as the devices table and daily snapshots of each device record per day for the past 90 days. The DateKey column indicates the day for each row.

| Property  | Description |
|---------|------------|
| DateKey |Reference to date table indicating the day |
| DeviceKey |Unique identifier of the device in the data warehouse - surrogate key. This is a reference to the Device table that contains the Intune device ID |
| DeviceName |Name of the device on platforms that allow naming a device. On other platforms, Intune creates a name from other properties. This attribute cannot be available for all devices. |
| DeviceTypeKey |Key of the device type attribute for this device |
| ClientRegisterationStateKey |Key of the client registration state attribute for this device |
| OwnerTypeKey |Key of the owner type attribute for this device: corporate, personal, or unknown. |
| objectSourceKey |Ignore this column. |
| CreatedDate |Date the device was enrolled on |
| LastContact |Last known device check-in with Intune |
| LastContactNotification |Last time Intune notified the device to check in with Intune |
| LastContactWorkplaceJoin |The timestamp indicating last known Workplace Join state for this device. |
| ManagementAgentKey |Key of the management agent associated with this device. |
| ManagementStateKey |Key of the management state associated with this device, indicating latest state of a remote action or if it was jailbroken/rooted. |
| ReferenceId |The device-s ID in Azure Active Directory |
| WorkPlaceJoinStateKey |Key of the workplace join state associated with this device. |
| CategoryId |Ignore this column. |
| EnrollmentTypeKey |Key of the enrollment type associated with this device, indicating method of enrollment. |
| CertExpirationDate |Expiry date of the MDM management certificate. |
| MdmStatusKey |A key to MdmStatus |
| OSFamily |OS Family (Windows, iOS, Android, etc.) |
| OSVersion |OS version |
| OSMajorVersion |Major version component of the OS version (major.minor.build.revision) |
| OSMinorVersion |Minor version component of the OS version (major.minor.build.revision) |
| OSBuildNumber |Build version component of the OS version (major.minor.build.revision) |
| OSRevisionNumber |Revision version component of the OS version (major.minor.build.revision) |
| EasID |This devices EAS ID, if the device is managed by Exchange Active Sync. |
| GraphDeviceIsManaged |The last management status that Intune set in AAD |
| GraphDeviceIsCompliant |The last compliance state that Intune set in AAD |
| SerialNumber |Serial number of the device, if available |
| EnrolledByUser |The ID of user who enrolled this device that references the userId column in User table. |
| RowLastModifiedDateTimeUTC |Last time this record was modified. |
| ProcessorArchitecture |Processor architecture |
| DeviceAction |Last device action issued, Ignore for now. |
| Manufacturer |Manufacturer of the device |
| Model |Model of the device |
| LastPolicyUpdateUtc |Latest time when policy was updated on the device |
| LastExchangeStatusUtc |Last time the device synced with exchange. |
## MdmDeviceInventoryHistories

The **MdmDeviceInventoryHistories** entity contains daily snapshots of inventory data for MDM-managed devices for the past 90 days. The column DateKey indicates the day for the row. Some properties might not be applicable or populated for all devices so consult this page for further details. For more information see [Understand your devices with inventory in Microsoft Intune](https://docs.microsoft.com/Intune-classic/deploy-use/understand-your-devices-with-inventory-in-microsoft-Intune).

| Property  | Description |
|---------|------------|
| DateKey |Reference to date table indicating the day |
| DeviceKey |Unique identifier of the device in the data warehouse - surrogate key. This is a reference to the Device table that contains the Intune device ID |
| DeviceModel |Model of the device |
| OS |OS of the device |
| DeviceName |Name of the device on platforms that allow naming a device. On other platforms, Intune creates a name from other properties. This attribute cannot be available for all devices. |
| SoftwareVersion |In most cases this is the OS version except in Apple platforms where it differs from OS version. |
| Imei |IMEI number |
| HardwareInventoryTimeUtc |The first time inventory was reported for this device. |
| InventoryModifiedTimeUtc |The last time inventory was stored when this snapshot was taken |
| InventoryReportingTimeUtc |The last time inventory was collected for this device. |
| ExchangeActiveSyncId |Exchange ActiveSync Device ID |
| ComputerSystemDescription |System description |
| ComputerSystemName |System Name |
| ComputerSystemManufacturer |System Manufacturer |
| ComputerSystemModel |System Model |
| UserName |User name |
| OSType |OS Type |
| OSCaption |OS Caption |
| OSName |OS Name |
| OSManufacturer |OS Manufacturer |
| OSProductSuite |OS Product Suite |
| OSProductType |OS Product Type |
| Locale |OS Locale |
| PhysicalMemoryCapacity |Physical Memory Capacity (in bytes) |
| PhysicalMemoryRemovable |Physical Removable Memory (in bytes) |
| SystemEnclosureChassisTypesInnerText |Defines the system chassis type for this device. The numbers indicate the following values:  0 or Empty = Unknown   1 = It is a Desktop   2 = It is a Laptop  3 = It is a Workstation  4 = It is an Enterprise Server  100 = It is a Phone  101 = It is a Tablet  102/103 = Another unknown type of Mobile device |
| SystemEnclosureModel |System Enclosure model |
| SystemEnclosureSerialNumber |System Enclosure Serial number |
| NetworkAdapterConfigurationText |Configuration text from network adapter |
| MacAddress |MAC address |
| SmsID |Intune device ID |
| CertExpiry |Expiry date of the MDM management certificate |
| DeviceClientAgentVersion |Client Agent Version |
| DeviceClientID |Device Client ID |
| SerialNumber |Serial Number |
| DeviceManufacturer |Device Manufacturer |
| DMVersion |DM version |
| FirmwareVersion |Firmware Version |
| HardwareVersion |Hardware Version |
| PlatformType |Platform Type |
| ProcessorLevel |Processor level |
| ProcessorRevision |Processor Revision |
| Product |Product |
| ProductVersion |Product version |
| OEM |Original Equipment manufacturer |
| DeviceBuildVersion |Device Build version |
| Meid |Mobile equipment identifier. |
| PhoneNumber |Phone number |
| SubscriberCarrierNetwork |Phone Carrier Network Name |
| CellularTechnology |Phone Carrier Network Type (CDMA/GSM) |
| Imsi |IMSI number |
| JailBroken |True if the device is Jail Broken or Rooted. |
| IsActivationLockEnabled |True Is Activation Lock is Enabled |
| DeviceType |Device Type |
| IsSupervised |Is Supervised |
| DeviceDisplayNumberOfColors |Device display Number Of Colors |
| HorizontalResolution |Device horizontal screen resolution |
| VerticalResolution |Device vertical screen resolution |
| StorageFree |Free storage (in bytes) |
| StorageTotal |Total storage (in bytes) |
| ProgramFree |Free Program memory (in bytes) |
| ProgramTotal |Total Program memory (in bytes) |
| RemovableStorageFree |Free removable storage (in bytes) |
| RemovableStorageTotal |Total removable storage (in bytes) |
| DeviceMemoryDeviceCapacity |Device memory capacity |
| DeviceMemoryAvailableDeviceCapacity |Device memory available capacity |
| DeviceOSVersion |OS Version |
| DeviceOSPlatform |OS platform |
| DeviceOSLanguage |OS language |
| PasswordMaxAttemptsBeforeWipe |Maximum allowed password attempts allowed before device wipe |
| PasswordMinComplexChars |Minimum number of complex characters required in the password |
| PasswordMinLength |Minimum required length of password |
| PasswordHistory |Password - Minimum historic passwords unaccepted |
| PasswordEnabled |Password - Enabled? |
| PasswordExpiration |Password - Expiration date |
| AllowRecoveryPassword |Allow password recovery |
| PasswordAutoLockTimeout |Password - Auto lock timeout |
| PasswordType |Password Type |
| BacklightACTimeout |Backlight time out when plugged into power source |
| BacklightBatTimeout |Backlight timeout on battery |
| PowerBackupPercent |Power backup percent |
| BatteryPercent |Remaining battery percent. |
| PlatformID |Platform ID |
| ExchangeDeviceID |Exchange Device ID |
| SmsProcessorDescription |Processor description |
| OwnerEmailAddress |Owner-s email address |
| DeviceOSName |OS Name |
| WifiMac |WIFI Mac address |
| EthernetMac |Ethernet MAC address |
| RequireEncryption |Indicates whether device is encrypted or not. |
| ActivationLockBypassCode |Activation lock Bypass code |

## ApplicationInventory

The **ApplicationInventory** entity lists the apps found on the device at the time of inventory collection.

| Property  | Description |
|---------|------------|
| DeviceKey |A reference to devices table |
| ApplicationKey |? (copied from ExchangeDeviceService\DeviceApplication) |
| ApplicationName |? (copied from ExchangeDeviceService\DeviceApplication) |
| ApplicationVersion |? (copied from ExchangeDeviceService\DeviceApplication) |
| BundleSize |? (copied from ExchangeDeviceService\DeviceApplication) |
