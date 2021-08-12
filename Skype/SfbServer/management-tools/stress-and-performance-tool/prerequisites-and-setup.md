---
title: Voraussetzungen und Setup für die Skype für das Stress- und Leistungstool von Busines
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
ms.openlocfilehash: 947cc43f68fc4d3140f664fbeb554096fcbb5cfb8c13d7354bc937af93812e93
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333147"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Voraussetzungen und Setup für die Skype für das Stress- und Leistungstool von Busines
 
Anforderungen oder Voraussetzungen für das Skype for Business Server 2015 Stress and Performance Tool. So installieren oder richten Sie das Stress and Performance Tool ein.
  
Wir haben die folgenden Abschnitte der Hardware-, Software- und Systemkonfigurationsanforderungen, die Sie berücksichtigen müssen, bevor Sie das Stress and Performance Tool ausführen:
  
- [Clienthardwareanforderungen](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Clientsoftwareanforderungen](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Konfigurationsanforderungen](prerequisites-and-setup.md#ConfigReqs)
    
Darüber hinaus haben wir auch einen Abschnitt unten für [die Installation des tools Skype for Business Server 2015 Stress and Performance](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Clienthardwareanforderungen
<a name="ClientHardwareReqs"> </a>

Wenn Sie das Stress and Performance Tool für Ihre Skype for Business Server 2015-Bereitstellung ausführen, benötigen Sie mindestens diese Hardwareanforderungen für alle 4500 Benutzer in Ihrem Test:
  
- 1 Gigabit-Netzwerkadapter
    
- 8 GB RAM
    
- 2 Dual-Core-CPUs
    
## <a name="client-software-requirements"></a>Clientsoftwareanforderungen
<a name="ClientSoftwareReqs"> </a>

Die unterstützten Betriebssysteme für das Stress and Performance Tool sind:
  
- Windows Server 2012
    
- Windows Server 2008 (64-Bit)
    
Darüber hinaus müssen Computer die folgenden Softwareanforderungen erfüllen:
  
- Sie müssen Microsoft .NET 4.5 Framework installiert haben. [Laden Sie hier .Net 4.5 Framework herunter.](https://www.microsoft.com/download/details.aspx?id=30653)
    
- Sie benötigen die Desktopdarstellungsfunktion in Windows aktiviert.
    
- Sie müssen Microsoft Visual C++ 2013 (x64) installiert sein. [Visual C++ 2013 hier herunterladen](https://www.microsoft.com/download/details.aspx?id=40784)
    
- Sie benötigen Skype for Business Server 2015 erfolgreich bereitgestellt.
    
## <a name="configuration-requirements"></a>Konfigurationsanforderungen
<a name="ConfigReqs"> </a>

Sie benötigen diese zusätzlichen Konfigurationen, um das Stress and Performance Tool erfolgreich auszuführen:
  
- Sie müssen sich beim Server als Mitglied der Gruppe "Domäne" oder "Lokaler Administrator" anmelden.
    
- Sie können das Skype for Business Server 2015-Benutzererstellungstool (UserProvisioningTool.exe) nicht auf einem Front-End-Server oder Standard Edition-Server installieren, auf dem sich die Benutzerkonten befinden.
    
- Wenn das Benutzererstellungstool mehrmals ausgeführt wird, muss jeder Benutzer, der für Microsoft Unified Communications aktiviert ist, über eine eindeutige Telefonnummer verfügen.
    
- Die Größe der Seitendatei sollte vom System verwaltet werden oder auf andere Weise mindestens das 1,5-fache der Ram-Größe im Computersystem betragen.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Installieren des Tools Skype for Business Server 2015 Stress and Performance
<a name="Installing"> </a>

Die Installation konnte nicht einfacher sein. Sie müssen die Windows Installer-Datei **CapacityPlanningTool.msi** auf jedem Clientcomputer ausführen, den Sie zum Simulieren des Benutzerdatenverkehrs verwenden möchten, und auf einem Front-End-Server in jedem Pool, auf dem Sie Benutzer und Kontakte erstellen.
  
Um die .msi zusammen mit den in unseren anderen Artikeln erwähnten Beispielskripts herunterzuladen, wechseln Sie zum Download Center-Link: [Skype for Business Server 2015, Stress and Performance Tool.](https://www.microsoft.com/download/details.aspx?id=50367)
  

