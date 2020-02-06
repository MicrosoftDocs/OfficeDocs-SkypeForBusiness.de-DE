---
title: Voraussetzungen und Setup für Skype for Business Stress and Performance Tool
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
description: Anforderungen oder Voraussetzungen für Skype for Business Server 2015 Stress and Performance Tool. Installieren oder Setup des Stress and Performance Tool.
ms.openlocfilehash: f52d92022e09314a8f9467cd939f67b2827cc153
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816174"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Voraussetzungen und Setup für Skype for Business Stress and Performance Tool
 
Anforderungen oder Voraussetzungen für Skype for Business Server 2015 Stress and Performance Tool. Installieren oder Setup des Stress and Performance Tool.
  
Die folgenden Abschnitte enthalten Anforderungen für Hardware, Software und Systemkonfiguration, die Sie beachten müssen, bevor Sie Stress and Performance Tool ausführen:
  
- [Clienthardwareanforderungen](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Clientsoftwareanforderungen](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Konfigurationsanforderungen](prerequisites-and-setup.md#ConfigReqs)
    
Außerdem gibt es einen Abschnitt zum [Installieren von Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing).
  
## <a name="client-hardware-requirements"></a>Clienthardwareanforderungen
<a name="ClientHardwareReqs"> </a>

Wenn Sie Stress and Performance Tool für Ihre Skype for Business Server 2015-Bereitstellung ausführen, müssen mindestens die folgenden Hardwareanforderungen für jeweils 4.500 Benutzer in Ihrem Test erfüllt sein:
  
- 1 Gigabitnetzwerkadapter
    
- 8 GB RAM
    
- 2 Doppelkern-CPUs
    
## <a name="client-software-requirements"></a>Clientsoftwareanforderungen
<a name="ClientSoftwareReqs"> </a>

Die folgenden Betriebssysteme werden für Stress and Performance Tool unterstützt:
  
- Windows Server 2012
    
- Windows Server 2008 (64-Bit)
    
Darüber hinaus müssen die Computer die folgenden Softwareanforderungen erfüllen:
  
- Microsoft .NET 4.5 Framework muss installiert sein. [Laden Sie das .NET 4,5-Framework hier herunter.](https://www.microsoft.com/en-us/download/details.aspx?id=30653)
    
- In Windows muss die Funktion Desktopdarstellung aktiviert sein.
    
- Microsoft Visual C++ 2013 (x64) muss installiert sein. [Visual C++ 2013 hier herunterladen](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
    
- Skype for Business Server 2015 muss erfolgreich bereitgestellt sein.
    
## <a name="configuration-requirements"></a>Konfigurationsanforderungen
<a name="ConfigReqs"> </a>

Außerdem müssen Sie diese Konfigurationen vornehmen, um Stress and Performance Tool erfolgreich auszuführen:
  
- Sie müssen sich als Mitglied der Domänenadministratorgruppe oder der lokalen Administratorgruppe beim Server anmelden.
    
- Sie können das Skype for Business Server 2015-Benutzererstellungstool („UserProvisioningTool.exe“) auf einem beliebigen Front-End-Server oder Standard Edition-Server ausführen, auf dem sich die Benutzerkonten befinden werden.
    
- Wenn das Benutzererstellungstool mehrmals ausgeführt wird, benötigt jeder Benutzer, der für Microsoft Unified Communications aktiviert ist, eine eindeutige Telefonnummer.
    
- Die Größe der Auslagerungsdatei sollte vom System verwaltet werden oder andernfalls mindestens das 1,5-Fache der RAM-Größe im Computersystem betragen.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Installieren von Skype for Business Server 2015 Stress and Performance Tool
<a name="Installing"> </a>

Die Installation ist ganz einfach. Sie müssen auf jedem Computer, auf dem Sie Benutzerdatenverkehr simulieren möchten, sowie auf einem Front-End-Server in jedem Pool, in dem Sie Benutzer und Kontakte erstellen werden, die Windows Installer-Datei **CapacityPlanningTool.msi** ausführen.
  
Wenn Sie die MSI-Datei zusammen mit den Beispielskripts, die in unseren anderen Artikeln erwähnt werden, herunterladen möchten, wechseln Sie zum Download Center-Link: [Skype for Business Server 2015, Stress-und Leistungs Tool](https://www.microsoft.com/download/details.aspx?id=50367).
  

