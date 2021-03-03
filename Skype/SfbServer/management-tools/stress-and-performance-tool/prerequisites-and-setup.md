---
title: Voraussetzungen und Einrichtung für das Skype for Busines Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Anforderungen oder Voraussetzungen für das Skype for Business Server 2015 Stress and Performance Tool. So installieren oder richten Sie das Stress and Performance Tool ein.
ms.openlocfilehash: a58eb5e291878bea74365cd1b9519983c7a77a84
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814955"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Voraussetzungen und Einrichtung für das Skype for Busines Stress and Performance Tool
 
Anforderungen oder Voraussetzungen für das Skype for Business Server 2015 Stress and Performance Tool. So installieren oder richten Sie das Stress and Performance Tool ein.
  
Wir haben die folgenden Abschnitte mit Hardware-, Software- und Systemkonfigurationsanforderungen, die Sie kennen müssen, bevor Sie das Stress and Performance Tool ausführen:
  
- [Clienthardwareanforderungen](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Clientsoftwareanforderungen](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Konfigurationsanforderungen](prerequisites-and-setup.md#ConfigReqs)
    
Darüber hinaus finden Sie weiter unten einen Abschnitt zum Installieren des [Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Clienthardwareanforderungen
<a name="ClientHardwareReqs"> </a>

Wenn Sie das Stress and Performance Tool für Ihre Skype for Business Server 2015-Bereitstellung ausführen, benötigen Sie mindestens diese Hardwareanforderungen für alle 4500 Benutzer in Ihrem Test:
  
- 1 Gigabit-Netzwerkadapter
    
- 8 GB RAM
    
- 2 Dual-Core-CPUs
    
## <a name="client-software-requirements"></a>Clientsoftwareanforderungen
<a name="ClientSoftwareReqs"> </a>

Die unterstützten Betriebssysteme für das Stress and Performance Tool sind:
  
- Windows Server 2012
    
- Windows Server 2008 (64-Bit)
    
Darüber hinaus müssen Computer die folgenden Softwareanforderungen erfüllen:
  
- Microsoft .NET 4.5 Framework muss installiert sein. [Laden Sie das .Net 4.5 Framework hier herunter.](https://www.microsoft.com/download/details.aspx?id=30653)
    
- Sie benötigen das Desktop-Experience-Feature, das in Windows aktiviert ist.
    
- Sie müssen Microsoft Visual C++ 2013 (x64) installiert haben. [Laden Sie Visual C++ 2013 hier herunter.](https://www.microsoft.com/download/details.aspx?id=40784)
    
- Sie benötigen eine erfolgreiche Bereitstellung von Skype for Business Server 2015.
    
## <a name="configuration-requirements"></a>Konfigurationsanforderungen
<a name="ConfigReqs"> </a>

Sie benötigen diese zusätzlichen Konfigurationen, um das Stress and Performance Tool erfolgreich ausführen zu können:
  
- Sie müssen sich beim Server als Mitglied der Gruppe "Domäne" oder "Lokaler Administrator" anmelden.
    
- Sie können das Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) nicht auf einem Front-End-Server oder Standard Edition-Server installieren, auf dem sich die Benutzerkonten befinden.
    
- Wenn das Tool "Benutzererstellung" mehrmals ausgeführt wird, muss jeder Benutzer, der für Microsoft Unified Communications aktiviert ist, über eine eindeutige Telefonnummer verfügen.
    
- Die Größe der Seitendatei sollte vom System verwaltet werden oder auf andere Weise mindestens das 1,5-fache des Arbeitsspeichers im Computersystem sein.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Installieren des Skype for Business Server 2015 Stress and Performance Tool
<a name="Installing"> </a>

Die Installation war nicht einfacher. Sie müssen die Windows Installer-Datei **CapacityPlanningTool.msi** auf jedem Clientcomputer ausführen, den Sie zum Simulieren des Benutzerdatenverkehrs verwenden möchten, und auf einem Front-End-Server in jedem Pool, in dem Sie Benutzer und Kontakte erstellen.
  
Um die .msi zusammen mit den Beispielskripts in unseren anderen Artikeln herunterzuladen, wechseln Sie zum Download Center-Link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).
  

