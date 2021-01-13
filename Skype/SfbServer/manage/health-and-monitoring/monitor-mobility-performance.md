---
title: Überwachen der Mobilität für die Leistung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Zusammenfassung: Erfahren Sie mehr über den Mobilitätsdienst (Mcx) und die Unified Communications Web API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: d7473d22f2de0576bf6214ae43719c8bfc70d49a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816835"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Überwachen der Mobilität für die Leistung in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Mobilitätsdienst (Mcx) und die Unified Communications Web API (UCWA) in Skype for Business Server.
  
Der Skype for Business Server Mobility Service (Mcx) und die Unified Communications Web API (UCWA) erhöhen die Last auf Front-End-Servern und Front-End-Pools. Mobile Geräte, die eine Verbindung mit dem Server auch dann aufrecht erhalten, wenn die mobile Anwendung minimiert ist, z. B. Android- und Nokia-Geräte, auf denen Lync 2010 Mobile ausgeführt wird, sowie Android- und Apple-Geräte, auf denen Lync 2013 Mobile ausgeführt wird, haben eine höhere Last als Geräte, die die Verbindung mit dem Server beenden, wenn die mobile Anwendung minimiert wird. Wenn die Mobilitätsnutzung zunimmt, müssen Sie die Mobilitätsleistung überwachen, um festzustellen, wann Sie Ihre Kapazität erhöhen müssen.

> [!NOTE]
> Die McX (Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits unified Communications Web API (UCWA), um Chat, Anwesenheit und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
Die Mobilitätsleistung wird durch mehrere Limits beeinflusst: 
  
- Verfügbarer Speicher
    
- Anforderungswarteschlangenlimit
    
- Gleichzeitige Verbindungen
    
- IIS-Warteschlangenlänge
    
Weitere Grenzwerte für Server, die sich auf die Mobilitätsleistung auswirken können, sind maximal 12 gleichzeitige Anmeldungen, Authentifizierungen, Sitzungserneuerungen und Beendigungen. Diese Höchstwerte müssen für die meisten Bereitstellungen nicht geändert werden.
  
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

- [Überwachen auf Kapazitätsgrenzen für den Serverspeicher in Skype for Business Server](server-memory-capacity-limits.md)
    
- [Überwachen der Mobilitätsdienst- und UCWA-Nutzung in Skype for Business Server](service-and-ucwa-usage.md)
    
- [Konfigurieren des Mobilitätsdiensts für hohe Leistung in Skype for Business Server](configure-service.md)
    
- [Überwachen der Protokolldateien für die Ablaufverfolgung von IIS-Anfragen in Skype for Business Server](iis-request-tracing-log-files.md)
    
- [Leistungsindikatoren für mobilität in Skype for Business Server](performance-counters.md)
    

