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

## Client scan process workflow
The client scan process is outlined in the following steps. Confirm each step in order to properly establish where the issue is.

![alt text](./giphy.gif "process animation")

## Client scan process steps
>[!div class="step-by-step"]

>[1. The client sends a WSUS Location Request to the management point](.\ts-sum-client-loc-request.md)

>[2. Scan agent requests the scan and WUAHandler initiates the scan](.\ts-sum-client-scanning.md)  

>[3. Windows Update Agent (WUA) starts the scan against the WSUS computer](.\ts-sum-client-scanning.md)

>[4. WUAHandler receives results from Windows Update Agent and marks the scan as complete](.\ts-sum-client-scanning.md)        

>[5. WUAHandler parses the scan results](.\ts-sum-client-scanning.md)        

>[6. Update Store records the status and raises a state message for each update in WMI](.\ts-sum-client-scanning.md)        

>[7. State messages are sent to the management point](.\ts-sum-client-scanning.md)        
