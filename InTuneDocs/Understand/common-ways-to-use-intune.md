---
title: Common ways to use Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 
author: jeffgilb
---
# Common ways to use Intune

The more IT control, the more "as appropriate" access for employees. 

## Unknown device
The following table describes common usage scenarios for IT management of unknown devices. 



<div class"table-wrapper">
	<table class="table-striped">
		<caption>Intune managemenet scenario for unknown devices></caption>
		<thead>
			<tr>
				<th>Scenario</th>
				<th>Description></th>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td>Example</td>
				<td>Kiosk at a hotel</td>
			</tr>
			<tr>
				<td>Type of user</td>
				<td>Information worker</td>
			</tr>	
			<tr>
				<td>What you can access</td>
				<td>Employees can access coroporate data only within a protected browser session.</td>
			</tr>	
			<tr>
				<td>What you can't access</td>
				<td>Employees can't download anything</td>
			</tr>			<tr>
				<td>What's managed</td>
				<td>Browswer session</td>
			</tr>	
			<tr>
				<td>Key features</td>
				<td>Web conditional acceess, web session protection, and multi-factor authentication</td>
			</tr>	
		</tbody>
	</table>
</div>

## Personal devices
The following table describes common usage scenarios for IT management of personal devices. 
<div class"table-wrapper">
	<table class="table-striped">
		<caption>Intune managemenet scenario for personal devices></caption>
		<tbody>
			<tr>
				<td>Example</td>
				<td>Personal iPad or home PC</td>
			</tr>
			<tr>
				<td>Type of user</td>
				<td>Information worker</td>
			</tr>	
			<tr>
				<td>What you can access</td>
				<td>Employees can use mobile productivity apps controlled by IT to prevent company data leakage.</td>
			</tr>			
			<tr>
				<td>What you can't access</td>
				<td>Employees can't access the corporate network, sync data, or use private apps.</td>
			</tr>	
			<tr>
				<td>What's managed</td>
				<td>Managed productivity apps and a managed web browser.</td>
			</tr>	
			<tr>
				<td><Key features></td>
				<td><Desktop and mobile application management conditional acceess, mobile application management without device enrollment, Azure Rights Management Service, Azure Remote App, and multi-factor authentication.</td>
			</tr>	
		</tbody>
	</table>
</div>

## Managed devices
The following table describes common usage scenarios for IT management of managed devices. 
<div class"table-wrapper">
	<table class="table-striped">
		<caption>Intune managemenet scenario for managed devices</caption>
		<tbody>
			<tr>
				<td>Example</td>
				<td>Company provided phone</td>
			</tr>
			<tr>
				<td>Type of user</td>
				<td>Information worker</td>
			</tr>	
			<tr>
				<td>What you can access></td>
				<td>Employees can access all mobile apps, access the corporate network, and sync corporate documents.</td>
			</tr>			
			<tr>
				<td>What you can't access></td>
				<td>Employees get full access per IT policies.</td>
			</tr>	
			<tr>
				<td>What's managed</td>
				<td>All mobile devices, Windows PCs, and apps used by employees.</td>
			</tr>	
			<tr>
				<td>Key features</td>
				<td>Desktop and mobile application management conditional acceess, mobile application management without device enrollment, mobile application management with device enrollment, Azure Rights Management Service, Azure Remote App, and multi-factor authentication.</td>
			</tr>	
		</tbody>
	</table>
</div>

## Shared devices
The following table describes common usage scenarios for IT management of shared devices. 
<div class"table-wrapper">
	<table class="table-striped">
		<caption>Intune managemenet scenario for shared devices</caption>
		<tbody>
			<tr>
				<td>Example</td>
				<td>Mobile retail point of sale tablet</td>
			</tr>
			<tr>
				<td>Type of user</td>
				<td>Task worker</td>
			</tr>	
			<tr>
				<td>What you can access</td>
				<td>Employees use the specific shared apps needed for their task.</td>
			</tr>			
			<tr>
				<td>What you can't access</td>
				<td>Anything else.</td>
			</tr>	
			<tr>
				<td>What's managed</td>
				<td>A locked down device with specific apps.</td>
			</tr>	
			<tr>
				<td>Key features</td>
				<td>Windows 10 provision profile, DEP/Configurator, kiosk mode.</td>
			</tr>	
		</tbody>
	</table>
</div>

