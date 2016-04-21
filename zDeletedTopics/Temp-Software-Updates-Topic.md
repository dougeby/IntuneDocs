---
title: Temp Software Updates Topic
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 82b7fc4b-52e9-46bb-ad8a-4c6f752c5485
author: robstackmsft
---
# Temp Software Updates Topic
## Improving Intune performance when you have many software updates to deploy

When you deploy a high number of software updates to a large number of PCs, the performance of the [!INCLUDE[wit_nextref](/Token/wit_nextref.xml)] console might be degraded. This might typically occur when you are deploying more than 100 updates to more than 1000 PCs.
While Microsoft continue to enhance the product to alleviate any performance issues, you can use the following workaround to deploy your required updates in smaller batches:
1. In the **Updates** workspace of the  [wit_nextref](/Token/wit_nextref.xml)] console, search for any outstanding updates you want to deploy.
![Software Updates node](/Image/Software-Updates/Software-Updates-node.png)
2.	Export these updates into a comma-seperated values (csv) file and open this file with Microsoft Excel.
![Filter Software Updates](/Image/Software-Updates/Filter-Software-Updates.png)
3.	Break the updates into smaller batches. Some suggestions that might be helpful include:
a.	Filter based on the name, focus on the cumulative update types or security updates first, then other updates
b.	Filter based on the name, focus on the platform (Windows 7, Office, etc.) based on your priority
c.	Filter based on the number of deployments needed, starting with smaller updates 
4.	Once the overall set of updates are broken down into smaller batches, then deploy these smaller batches.  

Deploying smaller batches should help avoid the load issue associated with trying to deploy too many updates at once. This will help you more quickly reduce the number of outstanding updates. 







For FAQ Topic

* When I deploy a high number of software updates to a large number of PCs (typically more than 100 updates to more than 1000 PCs), this is very slow. How can I speed this process up? 

You can use the workaround detailed in **Improving Intune performance when you have many software updates to deploy** to deploy required software updates in batches which will help to solve this problem.
