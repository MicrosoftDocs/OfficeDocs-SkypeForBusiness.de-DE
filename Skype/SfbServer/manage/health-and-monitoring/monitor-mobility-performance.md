---
title: Überwachen der Mobilität für die Leistung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Zusammenfassung: erfahren Sie mehr über den Mobilitätsdienst (MCX) und die Unified Communications Web-API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: 4d604c46704881a055385336f8b1ff32862d929a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817834"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Überwachen der Mobilität für die Leistung in Skype for Business Server
 
**Zusammenfassung:** Informieren Sie sich über den Mobilitätsdienst (MCX) und die Unified Communications Web-API (UCWA) in Skype for Business Server.
  
Der Skype for Business Server-Mobilitätsdienst (MCX) und die Unified Communications Web-API (UCWA) erhöhen die Auslastung von Front-End-Servern und Front-End-Pools. Mobile Geräte, die eine Verbindung mit dem Server beibehalten, auch wenn die Mobile Anwendung minimiert ist, wie etwa Android-und Nokia-Geräte mit lync 2010 Mobile sowie Android-und Apple-Geräte, auf denen lync 2013 Mobile ausgeführt wird, stellen eine größere Belastung als Geräte dar, die die Verbindung zum Server wird beendet, wenn die Mobile Anwendung minimiert wird. Nimmt die Nutzung der Mobilitätsdienste zu, müssen Sie die Mobilitätsleistung überwachen, um festzustellen, ob die Kapazität erhöht werden muss.

> [!NOTE]
> MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten. Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
Die Mobilitätsleistung wird durch mehrere Limits beeinflusst: 
  
- Verfügbarer Speicher
    
- Anforderungswarteschlangenlimit
    
- Gleichzeitige Verbindungen
    
- IIS-Warteschlangenlänge
    
Darüber hinaus wirken sich andere Serverlimits auf die Mobilitätsleistung aus. Hierzu gehören maximal 12 gleichzeitige Anmeldungen, Authentifizierungen und Sitzungserneuerungen und -beendigungen. Für die meisten Bereitstellungen müssen die Maximalwerte nicht geändert werden.
  
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

- [Überwachen der Kapazitätsgrenzen von Server Speicher in Skype for Business Server](server-memory-capacity-limits.md)
    
- [Überwachen des mobilitätsdiensts und der UCWA-Nutzung in Skype for Business Server](service-and-ucwa-usage.md)
    
- [Konfigurieren des mobilitätsdiensts für eine leistungsstarke Funktion in Skype for Business Server](configure-service.md)
    
- [Überwachen von IIS-Anforderungs Protokollierungs Protokolldateien in Skype for Business Server](iis-request-tracing-log-files.md)
    
- [Mobilitäts Leistungsindikatoren in Skype for Business Server](performance-counters.md)
    

