---
title: Voraussetzungen und Setup für die Skype für busines Stress and Performance Tool
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Anforderungen oder Voraussetzungen für das Skype for Business Server 2015 Stress and Performance Tool. So installieren oder richten Sie das Stress and Performance Tool ein.
ms.openlocfilehash: 60ff4476a92949b2f5ba0d7a027b5cadf3eab533
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835163"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Voraussetzungen und Setup für die Skype für busines Stress and Performance Tool
 
Anforderungen oder Voraussetzungen für das Skype for Business Server 2015 Stress and Performance Tool. So installieren oder richten Sie das Stress and Performance Tool ein.
  
Wir haben die folgenden Abschnitte der Hardware-, Software- und Systemkonfigurationsanforderungen, die Sie berücksichtigen müssen, bevor Sie das Stress and Performance Tool ausführen:
  
- [Clienthardwareanforderungen](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Clientsoftwareanforderungen](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Konfigurationsanforderungen](prerequisites-and-setup.md#ConfigReqs)
    
Darüber hinaus finden Sie weiter unten einen Abschnitt zum [Installieren des Tools Skype for Business Server 2015 Stress and Performance](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Clienthardwareanforderungen
<a name="ClientHardwareReqs"> </a>

Wenn Sie das Stress and Performance Tool für Ihre Skype for Business Server 2015-Bereitstellung ausführen, benötigen Sie mindestens diese Hardwareanforderungen, die für alle 4500 Benutzer in Ihrem Test erfüllt sind:
  
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
    
- Sie können das Skype for Business Server 2015-Benutzererstellungstool (UserProvisioningTool.exe) nicht auf einem Front-End-Server oder Standard Edition Server installieren, auf dem sich die Benutzerkonten befinden.
    
- Wenn das Benutzererstellungstool mehrmals ausgeführt wird, muss jeder Benutzer, der für Microsoft Unified Communications aktiviert ist, über eine eindeutige Telefonnummer verfügen.
    
- Die Größe der Seitendatei sollte vom System verwaltet werden oder auf andere Weise mindestens das 1,5-fache der Ram-Größe im Computersystem betragen.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Installieren des Tools Skype for Business Server 2015 Stress and Performance
<a name="Installing"> </a>

Die Installation konnte nicht einfacher sein. Sie müssen die Windows Installer-Datei **CapacityPlanningTool.msi** auf jedem Clientcomputer ausführen, den Sie zum Simulieren des Benutzerdatenverkehrs verwenden möchten, und auf einem Front-End-Server in jedem Pool, auf dem Sie Benutzer und Kontakte erstellen.
  
Um die .msi zusammen mit den in unseren anderen Artikeln erwähnten Beispielskripts herunterzuladen, wechseln Sie zum Download Center-Link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).
  

