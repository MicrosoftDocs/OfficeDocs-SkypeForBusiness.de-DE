---
title: Voraussetzungen und Setup für das Skype for Business Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Anforderungen oder Voraussetzungen für das Skype for Business Server 2015 Stress and Performance Tool. Vorgehensweise zum Installieren oder Einrichten des Stress-und Leistungstools.
ms.openlocfilehash: 9389feedb21948604b1ea68319c5fc068a561679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005980"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Voraussetzungen und Setup für das Skype for Business Stress and Performance Tool
 
Anforderungen oder Voraussetzungen für das Skype for Business Server 2015 Stress and Performance Tool. Vorgehensweise zum Installieren oder Einrichten des Stress-und Leistungstools.
  
Wir haben die folgenden Abschnitte der Hardware-, Software-und System Konfigurationsanforderungen, die Sie vor der Ausführung des Stress-und Leistungstools beachten müssen:
  
- [Client Hardwareanforderungen](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Client Softwareanforderungen](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Konfigurationsanforderungen](prerequisites-and-setup.md#ConfigReqs)
    
Darüber hinaus haben wir auch einen Abschnitt unten für [die Installation des Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Client Hardwareanforderungen
<a name="ClientHardwareReqs"> </a>

Wenn Sie das Belastungs-und Leistungs Tool für Ihre Skype for Business Server 2015-Bereitstellung verwenden, müssen Sie mindestens diese Hardwareanforderungen erfüllen, die für alle 4500-Benutzer in Ihrem Test erfüllt sind:
  
- 1 Gigabit-Netzwerkadapter
    
- 8 GB RAM
    
- 2 Dual-Core-CPUs
    
## <a name="client-software-requirements"></a>Client Softwareanforderungen
<a name="ClientSoftwareReqs"> </a>

Die unterstützten Betriebssysteme für das Tool Stress and Performance sind:
  
- Windows Server 2012
    
- Windows Server 2008 (64-Bit)
    
Darüber hinaus müssen Computer die folgenden Softwareanforderungen erfüllen:
  
- Sie benötigen das Microsoft .NET 4,5 Framework installiert. [Laden Sie das .NET 4,5 Framework hier herunter.](https://www.microsoft.com/download/details.aspx?id=30653)
    
- Sie benötigen das Feature "Desktop Experience" in Windows aktiviert.
    
- Sie müssen Microsoft Visual C++ 2013 (x64) installiert haben. [Visual C++ 2013 hier herunterladen](https://www.microsoft.com/download/details.aspx?id=40784)
    
- Sie benötigen Skype for Business Server 2015 erfolgreich bereitgestellt werden.
    
## <a name="configuration-requirements"></a>Konfigurationsanforderungen
<a name="ConfigReqs"> </a>

Sie benötigen diese zusätzlichen Konfigurationen, um das Stress-und Leistungs Tool erfolgreich auszuführen:
  
- Sie müssen sich beim Server als Mitglied der Domäne oder der Gruppe des lokalen Administrators anmelden.
    
- Sie können das Skype for Business Server 2015-Benutzer Erstellungstool (UserProvisioningTool. exe) nicht auf einem Front-End-Server oder Standard Edition-Server installieren, in dem sich die Benutzerkonten befinden.
    
- Wenn das Benutzer Erstellungstool mehrmals ausgeführt wird, muss jeder Benutzer, der für Microsoft Unified Communications aktiviert ist, über eine eindeutige Telefonnummer verfügen.
    
- Die Größe der Auslagerungsdatei sollte System verwaltet sein oder muss auf andere Weise mindestens 1,5 mal so viel RAM im Computersystem sein.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Installieren des Skype for Business Server 2015-Tools für Stress und Leistung
<a name="Installing"> </a>

Die Installation kann nicht einfacher sein. Sie müssen die Windows Installer-Datei **CapacityPlanningTool. msi**auf jedem Clientcomputer ausführen, den Sie zum Simulieren des Benutzerdatenverkehrs verwenden werden, und auf einer Front-End-Server in jedem Pool, in dem Sie Benutzer und Kontakte erstellen.
  
Um die MSI-Datei sowie die in den anderen Artikeln erwähnten Beispielskripts herunterzuladen, wechseln Sie zum Download Center-Link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).
  

