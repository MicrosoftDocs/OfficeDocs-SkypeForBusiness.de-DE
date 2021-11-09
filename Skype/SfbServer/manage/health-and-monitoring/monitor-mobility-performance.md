---
title: Überwachen der Mobilität auf Leistung in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Zusammenfassung: Erfahren Sie mehr über den Mobilitätsdienst (Mcx) und die Unified Communications-Web-API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: 5560e869a4b3313cf63ef4466aa9f8ce394766d1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863562"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Überwachen der Mobilität auf Leistung in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Mobilitätsdienst (Mcx) und die Unified Communications-Web-API (UCWA) in Skype for Business Server.
  
Der Skype for Business Server Mobility Service (Mcx) und die Unified Communications Web API (UCWA) erhöhen die Last auf Front-End-Servern und Front-End-Pools. Mobile Geräte, die eine Verbindung mit dem Server aufrechterhalten, auch wenn die mobile Anwendung minimiert wird, z. B. Android- und Nokia-Geräte mit Lync 2010 Mobile sowie Android- und Apple-Geräte mit Lync 2013 Mobile, führen zu einer höheren Last als Geräte, die ihre Verbindung mit dem Server beenden, wenn die mobile Anwendung minimiert wird. Wenn Ihre Mobilitätsnutzung zunimmt, müssen Sie die Mobilitätsleistung überwachen, um zu bestimmen, wann Sie Ihre Kapazität erhöhen müssen.

> [!NOTE]
> McX(Mobility Service)-Unterstützung für mobile Legacyclients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen Skype for Business mobile Clients verwenden bereits unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.
  
Die Mobilitätsleistung wird durch mehrere Limits beeinflusst: 
  
- Verfügbarer Speicher
    
- Anforderungswarteschlangenlimit
    
- Gleichzeitige Verbindungen
    
- IIS-Warteschlangenlänge
    
Weitere Grenzwerte für Server, die die Mobilitätsleistung beeinflussen können, sind maximal 12 gleichzeitige Anmeldungen, Authentifizierungen, Sitzungsverlängerungen und Beendigungen. Diese Höchstwerte müssen für die meisten Bereitstellungen nicht geändert werden.
  
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

- [Überwachen von Kapazitätslimits für den Serverspeicher in Skype for Business Server](server-memory-capacity-limits.md)
    
- [Überwachen der Mobilitätsdienste- und UCWA-Nutzung in Skype for Business Server](service-and-ucwa-usage.md)
    
- [Konfigurieren des Mobilitätsdiensts für hohe Leistung in Skype for Business Server](configure-service.md)
    
- [Überwachen der Protokolldateien der IIS-Anforderungsablaufverfolgung in Skype for Business Server](iis-request-tracing-log-files.md)
    
- [Leistungsindikatoren für Mobilität in Skype for Business Server](performance-counters.md)
    

