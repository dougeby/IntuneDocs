---
title: Microsoft Intune App SDK Frequently Asked Questions
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 133d81c4-e550-404a-980e-64f6e843c649
author: Msmbaldwin
---
# Microsoft Intune App SDK Frequently Asked Questions
Here are some frequently asked questions regarding the Intune App SDK.

## I found an issue with the Intune App SDK or documentation. How do I submit feedback or report issues?

Feedback on the Intune App SDK can be submitted through the Microsoft Connect site here. You will see an option to submit the feedback or issue there. Please provide a priority for submitted issues, and the Microsoft Intune team will address them as soon as possible.

![App Feedback Form](/Image/App_Feedback_Form.png)

## How does the Intune App SDK treat OS updates and compatibility?

We will strive to ensure that existing SDK features will work on new OS version as soon as possible, and that the SDK will not cause application crashes or other serious end user impact due to new OS features accessible to end users from within existing applications.

When sufficient lead time is provided by OS vendors, Intune will provide support for OS Beta versions to enable application pre-release testing. ISVs should report in advance any discovered compatibility issues or plans to release application versions targeting OS preview versions.

New features added to the SDK will not break existing OS compatibility without advanced notice and agreement from Microsoft; unintentional compatibility issues will be handled as bugs.

## How does the Intune App SDK affect my mobile app?

The SDK can affect application in three main ways.
* **Performance**: The methods used to enforce policy may impact application performance. Please test the performance and report any issues as bugs and include performance results with and without policy for the scenario.
* **Optional Features**: The SDK supports optional features through the API surface (e.g. save-as). These features require application changes to support.

  > [AZURE.NOTE] Telemetry is an “opt-in” feature. The iOS MAM SDK logs SDK telemetry data on usage events **by default**. This data gets sent to Microsoft Intune. If you choose not to send SDK telemetry data to Microsoft Intune from your application, you must disable SDK telemetry capture by setting the `MAMTelemetryDisabled` property to "YES" in the `IntuneMAMSettings`.
  
* **Policy Enforcement**: When MAM Policy is applied to SDK applications, application features and user experience may be altered. Application teams should work with the Intune team to test their applications to understand this impact.
