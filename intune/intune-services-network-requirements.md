---
# required metadata

title: Network requirements for Microsoft Intune Services
titleSuffix: 
description: Review network configuration requirements and bandwidth details for Intune.
keywords:
author: fredrik.rudin
ms.author: erikje
manager: dougeby
ms.date: 04/03/2019
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
---

#  Network requirements for Microsoft Intune Services

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

This guidance helps Intune admins understand the network requirements for the additional Intune service. You can use this information to understand IP address and port settings needed for proxy settings and firewall rules.

## Network communication requirements

Enable network communications between the services you manage and the endpoints required for cloud-based services.

To manage services behind firewalls and proxy servers, you must enable communication to Intune.

- The proxy server must support **HTTPS (443)** 
- For some tasks (like downloading software updates), The server will require unauthenticated proxy server access to manage.microsoft.com

You can modify proxy server settings on individual servers. You can also use Group Policy settings to change settings for all servers located behind a specified proxy server.

***IE Enhanced Security Configuration***
Please note that The IE Enhanced Security Configuration needs to be disabled on the Windows Server 2016 to be allowed to activate the NDES Connector. 
Start the Server Manager and open Local Server you see the IE Enhanced Security Configuration set to On. 
Turn off IE Enhanced Security Configuration for Administrators and/or for Users and click OK. Turning it off of the Administrators should do the trick for activating/enrolling the NDES Connector.


The following tables list the ports and services that the Intune Services accesses:

|**Domains**|**IP address**|
|---------------------|-----------|
|login.microsoft.com
|login.microsoftonline-p.com
|login.microsoftonline.com | More information [Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) |
|portal.manage.microsoft.com<br> m.manage.microsoft.com |52.175.12.209<br>20.188.107.228<br>52.138.193.149<br>51.144.161.187<br>52.160.70.20<br>52.168.54.64 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com 
