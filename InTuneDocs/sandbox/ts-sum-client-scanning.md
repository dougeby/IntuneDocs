---
title: Client Software Update Scanning
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: tempfile
author: jeffgilb
---
# Client Software Update Scanning

## Picture with text on same line
The client scan process is outlined in the following steps. Confirm each step in order to properly establish where the issue is.

![alt text](./giphy.gif "process animation")


>[!div class="step-by-step"]

>[The client sends a WSUS Location Request to the management point](.\ts-sum-client-loc-request.md)

>[Scan agent requests the scan and WUAHandler initiates the scan](.)  

>[Windows Update Agent (WUA) starts the scan against the WSUS computer](.)

>[WUAHandler receives results from Windows Update Agent and marks the scan as complete  ](.)        

>[WUAHandler parses the scan results](.)        

>[Update Store records the status and raises a state message for each update in WMI](.)        

>[State messages are sent to the management point ](.)        
