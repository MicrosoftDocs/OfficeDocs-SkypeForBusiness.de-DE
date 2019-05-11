---
title: Überwachen der Mobilität für die Leistung in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Zusammenfassung: Informationen Sie zu den Mobilitätsdienst ("MCX") und der Unified Communications-Web-API (UCWA) in Skype für Business Server.'
ms.openlocfilehash: e2da6f073dc14268442e3c49273189b002eaadc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902833"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Überwachen der Mobilität für die Leistung in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu den Mobilitätsdienst ("MCX") und der Unified Communications-Web-API (UCWA) in Skype für Business Server.
  
Die Skype Business Server-Mobilitätsdienst ("MCX") und Unified Communications Web-API (UCWA) erhöhen die Last auf dem Front-End-Servern und Front-End-Pools. Mobile Geräte, die eine Verbindung mit dem Server verwalten, auch wenn die mobile Anwendung minimiert wird, wie beispielsweise Android- und Nokia-Geräte, die mit Lync 2010 Mobile sowie Android und Apple-Geräte, die mit Lync 2013 Mobile bedingen eine größere Belastung als Geräte, Ihre Verbindung mit dem Server zu beenden, wenn die mobile Anwendung minimiert ist. Nimmt die Nutzung der Mobilitätsdienste zu, müssen Sie die Mobilitätsleistung überwachen, um festzustellen, ob die Kapazität erhöht werden muss.

> [!NOTE]
> Unterstützung für mobile Clients von Vorversionen MCX (Mobility Service) ist nicht mehr in Skype für Business Server 2019 verfügbar. Alle aktuellen Skype für mobile Clients Business Unified Communications Web API (UCWA) zur Unterstützung von Sofortnachrichten (IM), Anwesenheit und Kontakte bereits verwenden. Benutzer mit Clients von Vorversionen von MCX müssen an einen aktuellen Client aktualisieren.
  
Die Mobilitätsleistung wird durch mehrere Limits beeinflusst: 
  
- Verfügbarer Speicher
    
- Anforderungswarteschlangenlimit
    
- Gleichzeitige Verbindungen
    
- IIS-Warteschlangenlänge
    
Darüber hinaus wirken sich andere Serverlimits auf die Mobilitätsleistung aus. Hierzu gehören maximal 12 gleichzeitige Anmeldungen, Authentifizierungen und Sitzungserneuerungen und -beendigungen. Für die meisten Bereitstellungen müssen die Maximalwerte nicht geändert werden.
  
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

- [Überwachen von Server-Speicher-kapazitätslimits in Skype für Business Server](server-memory-capacity-limits.md)
    
- [Überwachen Sie Nutzung des Mobilitätsdiensts und des UCWA in Skype für Business Server](service-and-ucwa-usage.md)
    
- [Konfigurieren von Mobility Service für hohe Leistung in Skype für Business Server](configure-service.md)
    
- [Monitoring IIS Request tracing Log Files in der Skype für Business Server](iis-request-tracing-log-files.md)
    
- [Leistungsindikatoren für Mobilität in Skype für Business Server](performance-counters.md)
    

