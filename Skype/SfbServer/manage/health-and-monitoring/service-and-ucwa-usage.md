---
title: Überwachen des Mobilitätsdienstes und der Verwendung der UCWA in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Zusammenfassung: Verwalten von den Mobilitätsdienst ("MCX") und der Web-API (UCWA) von Unified Communications in Skype für Business Server 2015.'
ms.openlocfilehash: e71d18fe90eb9a7f2fd7b6563e6d6930f2473e74
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server-2015"></a>Überwachen des Mobilitätsdienstes und der Verwendung der UCWA in Skype for Business Server 2015
 
**Zusammenfassung:** Verwalten Sie den Mobilitätsdienst ("MCX") und der Web-API (UCWA) von Unified Communications in Skype für Business Server 2015.
  
Kontinuierlich sollten Sie überwachen, CPU und Arbeitsspeicher, die von der Skype Business Server-Mobilitätsdienst ("MCX") und Unified Communications Web-API (UCWA) verwendet wird. Zum Überwachen der Auslastung können Sie Folgendes verwenden:
  
 **Für die Unified Communications-Web-API (UCWA):**
  
- Der **LyncUcwa** -Arbeitsprozess in Internetinformationsdienste (Internet Information Services, IIS)-Manager. Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.
    
- Die Leistungsindikatoren **CPU** und **Prozessor**.
    
Bei den meisten Bereitstellungen sollte die UCWA-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen. Speicherverwendung sollten in der im [Monitor für Server-Speicher-Kapazitätsgrenzen in Skype für Business Server 2015](server-memory-capacity-limits.md)beschriebenen Grenzwerte fallen.
  
Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:
  
- **LS:WEB - Drosselung und Authentication\WEB - Gesamtanfragen bei der Verarbeitung**, gibt die Anzahl der ausstehenden Webanfragen auf dem Server an. Wenn dieser Leistungsindikator 10.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung „503 - Dienst nicht verfügbar“ fehl.
    
- **ASP.NET\Requests Queued** (sollte immer NULL sein).
    
> [!NOTE]
> Wenn diese Werte erreicht oder überschritten werden, sollten Sie die Kapazitätsplanung für die Computer überarbeiten, die die Webdienste hosten, und die Größenanpassung für die CPU, die Anzahl von Kernen sowie den Arbeitsspeicher neu berechnen. 
  
 **Für den Mobilitätsdienst (Mcx):**
  
- Die **CSIntMcxAppPool** und **CSExtMcxAppPool** Arbeitsprozesse in Internetinformationsdienste (Internet Information Services, IIS)-Manager. Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.
    
- Die Leistungsindikatoren **CPU** und **Prozessor**.
    
Bei den meisten Bereitstellungen sollte die Mobilitätsdienst-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen. Speicherverwendung sollten in der im [Monitor für Server-Speicher-Kapazitätsgrenzen in Skype für Business Server 2015](server-memory-capacity-limits.md)beschriebenen Grenzwerte fallen.
  
Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden ASP.NET-Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:
  
- **ASP.NET v2.0.50727\Requests aktuelle**, gibt die Anzahl der ausstehenden Webanfragen auf dem Server an. Wenn dieser Leistungsindikator 5.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung „503 - Dienst nicht verfügbar“ fehl.
    
- **ASP.NET\Requests Queued** (sollte immer NULL sein).
    
> [!NOTE]
> Wenn diese Werte erreicht oder überschritten werden, sollten Sie die Kapazitätsplanung für die Computer überarbeiten, die die Webdienste hosten, und die Größenanpassung für die CPU, die Anzahl von Kernen sowie den Arbeitsspeicher neu berechnen. 
  
## <a name="see-also"></a>Siehe auch

#### 

[Überwachen von Server-Speicher-kapazitätslimits in Skype für Business Server 2015](server-memory-capacity-limits.md)

