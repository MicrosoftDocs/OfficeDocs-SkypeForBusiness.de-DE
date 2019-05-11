---
title: Überwachen Sie Nutzung des Mobilitätsdiensts und des UCWA in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Zusammenfassung: Verwalten der Mobilitätsdienst ("MCX") und der Unified Communications-Web-API (UCWA) in Skype für Business Server.'
ms.openlocfilehash: ddbb8ee4915c64781d059f8495c7e0bd46e57fc6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33887132"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Überwachen Sie Nutzung des Mobilitätsdiensts und des UCWA in Skype für Business Server
 
**Zusammenfassung:** Verwalten Sie der Mobilitätsdienst ("MCX") und der Unified Communications-Web-API (UCWA) in Skype für Business Server.

> [!NOTE]
> Unterstützung für mobile Clients von Vorversionen MCX (Mobility Service) ist nicht mehr in Skype für Business Server 2019 verfügbar. Alle aktuellen Skype für mobile Clients Business Unified Communications Web API (UCWA) zur Unterstützung von Sofortnachrichten (IM), Anwesenheit und Kontakte bereits verwenden. Benutzer mit Clients von Vorversionen von MCX müssen an einen aktuellen Client aktualisieren.
  
Kontinuierlich sollten Sie überwachen, CPU und Arbeitsspeicher, die von der Skype Business Server-Mobilitätsdienst ("MCX") und Unified Communications Web-API (UCWA) verwendet wird. Zum Überwachen der Auslastung können Sie Folgendes verwenden:
  
 **Für die Unified Communications-Web-API (UCWA):**
  
- Der **LyncUcwa** -Arbeitsprozess in Internetinformationsdienste (Internet Information Services, IIS)-Manager. Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.
    
- Die Leistungsindikatoren **CPU** und **Prozessor**.
    
Bei den meisten Bereitstellungen sollte die UCWA-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen. Speicherverwendung sollten in der im [Monitor für Server-Speicher-Kapazitätsgrenzen in Skype für Business Server](server-memory-capacity-limits.md)beschriebenen Grenzwerte fallen.
  
Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:
  
- **LS:WEB - Drosselung und Authentication\WEB - Gesamtanfragen bei der Verarbeitung**, gibt die Anzahl der ausstehenden Webanfragen auf dem Server an. Wenn dieser Leistungsindikator 10.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung „503 - Dienst nicht verfügbar“ fehl.
    
- **ASP.NET\Requests Queued** (sollte immer Null sein).
    
> [!NOTE]
> Wenn diese Werte erreicht oder überschritten werden, sollten Sie die Kapazitätsplanung für die Computer überarbeiten, die die Webdienste hosten, und die Größenanpassung für die CPU, die Anzahl von Kernen sowie den Arbeitsspeicher neu berechnen. 
  
 **Für den Mobilitätsdienst (Mcx):**
  
- Die **CSIntMcxAppPool** und **CSExtMcxAppPool** Arbeitsprozesse in Internetinformationsdienste (Internet Information Services, IIS)-Manager. Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.
    
- Die Leistungsindikatoren **CPU** und **Prozessor**.
    
Bei den meisten Bereitstellungen sollte die Mobilitätsdienst-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen. Speicherverwendung sollten in der im [Monitor für Server-Speicher-Kapazitätsgrenzen in Skype für Business Server](server-memory-capacity-limits.md)beschriebenen Grenzwerte fallen.
  
Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden ASP.NET-Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:
  
- **ASP.NET v2.0.50727\Requests Current**, der die Anzahl der ausstehenden Webanforderungen auf dem Server angibt. Wenn dieser Leistungsindikator 5.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung „503 - Dienst nicht verfügbar“ fehl.
    
- **ASP.NET\Requests Queued** (sollte immer Null sein).
    
> [!NOTE]
> Wenn diese Werte erreicht oder überschritten werden, sollten Sie die Kapazitätsplanung für die Computer überarbeiten, die die Webdienste hosten, und die Größenanpassung für die CPU, die Anzahl von Kernen sowie den Arbeitsspeicher neu berechnen. 

> [!NOTE]
> Unterstützung für mobile Clients von Vorversionen MCX (Mobility Service) ist nicht mehr in Skype für Business Server 2019 verfügbar. Alle aktuellen Skype für mobile Clients Business Unified Communications Web API (UCWA) zur Unterstützung von Sofortnachrichten (IM), Anwesenheit und Kontakte bereits verwenden. Benutzer mit Clients von Vorversionen von MCX müssen an einen aktuellen Client aktualisieren.
  
## <a name="see-also"></a>Siehe auch

[Überwachen von Server-Speicher-kapazitätslimits in Skype für Business Server](server-memory-capacity-limits.md)
