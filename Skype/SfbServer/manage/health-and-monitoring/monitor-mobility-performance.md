---
title: Überwachen der Mobilität in Bezug auf die Leistung in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Zusammenfassung: Informationen Sie zu den Mobilitätsdienst ("MCX") und der Web-API (UCWA) von Unified Communications in Skype für Business Server 2015.'
ms.openlocfilehash: 1981bff8398f3fab9206f9dab748c545268f7edf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server-2015"></a>Überwachen der Mobilität in Bezug auf die Leistung in Skype for Business Server 2015
 
**Zusammenfassung:** Informieren Sie sich über den Mobilitätsdienst ("MCX") und der Web-API (UCWA) von Unified Communications Skype für Business Server 2015.
  
Die Skype Business Server-Mobilitätsdienst ("MCX") und Unified Communications Web-API (UCWA) erhöhen die Last auf dem Front-End-Servern und Front-End-Pools. Mobile Geräte, die eine Verbindung mit dem Server verwalten, auch wenn die mobile Anwendung minimiert wird, wie beispielsweise Android- und Nokia-Geräte, die mit Lync 2010 Mobile sowie Android und Apple-Geräte, die mit Lync 2013 Mobile bedingen eine größere Belastung als Geräte, Ihre Verbindung mit dem Server zu beenden, wenn die mobile Anwendung minimiert ist. Nimmt die Nutzung der Mobilitätsdienste zu, müssen Sie die Mobilitätsleistung überwachen, um festzustellen, ob die Kapazität erhöht werden muss.
  
Die Mobilitätsleistung wird durch mehrere Limits beeinflusst: 
  
- Verfügbarer Speicher
    
- Anforderungswarteschlangenlimit
    
- Gleichzeitige Verbindungen
    
- IIS-Warteschlangenlänge
    
Darüber hinaus wirken sich andere Serverlimits auf die Mobilitätsleistung aus. Hierzu gehören maximal 12 gleichzeitige Anmeldungen, Authentifizierungen und Sitzungserneuerungen und -beendigungen. Für die meisten Bereitstellungen müssen die Maximalwerte nicht geändert werden.
  
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

- [Überwachen von Server-Speicher-kapazitätslimits in Skype für Business Server 2015](server-memory-capacity-limits.md)
    
- [Überwachen Sie Nutzung des Mobilitätsdiensts und des UCWA in Skype für Business Server 2015](service-and-ucwa-usage.md)
    
- [Konfigurieren von Mobility Service für hohe Leistung in Skype für Business Server 2015](configure-service.md)
    
- [Monitoring IIS request Tracing Log Files in der Skype für Business Server 2015](iis-request-tracing-log-files.md)
    
- [Leistungsindikatoren für Mobilität in Skype für Business Server 2015](performance-counters.md)
    

