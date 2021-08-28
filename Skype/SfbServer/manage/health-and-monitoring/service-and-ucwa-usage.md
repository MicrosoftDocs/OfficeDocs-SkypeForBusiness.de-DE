---
title: Überwachen der Mobilitätsdienste- und UCWA-Nutzung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Zusammenfassung: Verwalten des Mobilitätsdiensts (Mcx) und der Unified Communications-Web-API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: a9cc79e523c3ba6671df302d844dc5e05d3bae28
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608162"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Überwachen der Mobilitätsdienste- und UCWA-Nutzung in Skype for Business Server
 
**Zusammenfassung:** Verwalten Sie den Mobilitätsdienst (Mcx) und die Unified Communications-Web-API (UCWA) in Skype for Business Server.

> [!NOTE]
> McX(Mobility Service)-Unterstützung für mobile Legacyclients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen Skype for Business mobile Clients verwenden bereits unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.
  
Sie sollten kontinuierlich die CPU und den Arbeitsspeicher überwachen, die vom Skype for Business Server Mobility Service (Mcx) und der Unified Communications Web API (UCWA) verwendet werden. Um die Nutzung zu überwachen, können Sie Folgendes verwenden:
  
 **Für Unified Communications Web API (UCWA):**
  
- Der **LyncUcwa-Arbeitsprozess** im Internetinformationsdienste (IIS)-Manager. Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.
    
- Die Leistungsindikatoren **CPU** und **Prozessor**.
    
Bei den meisten Bereitstellungen sollte die UCWA-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen. Die Speicherauslastung sollte innerhalb der Unter ["Monitor for server memory capacity limits" in Skype for Business Server](server-memory-capacity-limits.md)beschriebenen Grenzwerte liegen.
  
Zusätzlich zu CPU- und Speicherauslastungszählern können Sie die folgenden Leistungsindikatoren verwenden, um zu ermitteln, wann ein Server mit Anforderungen überlastet ist:
  
- **LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server. Wenn dieser Zähler 10.000 erreicht, schlagen nachfolgende Anforderungen fehl, wobei die Fehlermeldung "503 - Dienst nicht verfügbar" angezeigt wird.
    
- **ASP.NET\Requests Queued** (sollte immer Null sein).
    
> [!NOTE]
> Wenn Sie diese Werte erfüllen oder überschreiten, sollten Sie Ihre Kapazitätsplanung für die richtige Größe der CPU, die Anzahl der Kerne und den Arbeitsspeicher für die Computer, die die Webdienste hosten, erneut berechnen. 
  
 **Für den Mobilitätsdienst (Mcx):**
  
- Die **Arbeitsprozesse "CSIntMcxAppPool"** und **"CSExtMcxAppPool"** im Internetinformationsdienste-Manager (IIS). Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.
    
- Die Leistungsindikatoren **CPU** und **Prozessor**.
    
Bei den meisten Bereitstellungen sollte die CPU-Auslastung des Mobilitätsdiensts im Durchschnitt unter 15 Prozent liegen. Die Speicherauslastung sollte innerhalb der Unter ["Monitor for server memory capacity limits" in Skype for Business Server](server-memory-capacity-limits.md)beschriebenen Grenzwerte liegen.
  
Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden ASP.NET-Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:
  
- **ASP.NET v2.0.50727\Requests Current**, der die Anzahl der ausstehenden Webanforderungen auf dem Server angibt. Wenn dieser Indikator 5.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung "503 - Dienst nicht verfügbar" fehl.
    
- **ASP.NET\Requests Queued** (sollte immer Null sein).
    
> [!NOTE]
> Wenn Sie diese Werte erfüllen oder überschreiten, sollten Sie Ihre Kapazitätsplanung für die richtige Größe der CPU, die Anzahl der Kerne und den Arbeitsspeicher für die Computer, die die Webdienste hosten, erneut überprüfen und neu berechnen. 

> [!NOTE]
> McX(Mobility Service)-Unterstützung für mobile Legacyclients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen Skype for Business mobile Clients verwenden bereits unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.
  
## <a name="see-also"></a>Siehe auch

[Überwachen von Kapazitätslimits für den Serverspeicher in Skype for Business Server](server-memory-capacity-limits.md)
