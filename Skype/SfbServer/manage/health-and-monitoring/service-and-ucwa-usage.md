---
title: Überwachen der Mobilitätsdienst- und UCWA-Nutzung in Skype for Business Server
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
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Zusammenfassung: Verwalten des Mobilitätsdiensts (Mcx) und der Unified Communications Web API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: 76bcf8727d3abbb417595f033ce9a59ec00a39ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814245"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Überwachen der Mobilitätsdienst- und UCWA-Nutzung in Skype for Business Server
 
**Zusammenfassung:** Verwalten des Mobilitätsdiensts (Mcx) und der Unified Communications Web API (UCWA) in Skype for Business Server.

> [!NOTE]
> Die McX (Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits unified Communications Web API (UCWA), um Chat, Anwesenheit und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
Sie sollten fortlaufend die CPU und den Arbeitsspeicher überwachen, die vom Skype for Business Server Mobility Service (Mcx) und der Unified Communications Web API (UCWA) verwendet werden. Zum Überwachen der Verwendung können Sie Folgendes verwenden:
  
 **Für Unified Communications Web API (UCWA):**
  
- Der **LyncUcwa-Arbeitsprozess** im Internetinformationsdienste-Manager. Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.
    
- Die Leistungsindikatoren **CPU** und **Prozessor**.
    
Bei den meisten Bereitstellungen sollte die UCWA-CPU-Auslastung im Durchschnitt unter 15 % liegen. Die Speicherauslastung sollte innerhalb der grenzen liegen, die unter [Monitor for server memory capacity limits in Skype for Business Server beschrieben sind.](server-memory-capacity-limits.md)
  
Zusätzlich zu CPU- und Speicherauslastungsindikatoren können Sie die folgenden Leistungsindikatoren verwenden, um zu bestimmen, wann ein Server mit Anforderungen überlastet ist:
  
- **LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, was die Anzahl der ausstehenden Webanforderungen auf dem Server angibt. Wenn dieser Indikator 10.000 erreicht, tritt bei nachfolgenden Anforderungen ein Fehler auf, und die Fehlermeldung "503 - Dienst nicht verfügbar" wird angezeigt.
    
- **ASP.NET\Requests Queued** (sollte immer Null sein).
    
> [!NOTE]
> Wenn Sie diese Werte erfüllen oder überschreiten, sollten Sie Ihre Kapazitätsplanung für die richtige Größe der CPU, die Anzahl der Kerne und den Arbeitsspeicher für die Computer, die die Webdienste hosten, erneut durcharbeiten und neu berechnen. 
  
 **Für den Mobilitätsdienst (Mcx):**
  
- Die **Arbeitsprozesse CSIntMcxAppPool** und **CSExtMcxAppPool** im Internetinformationsdienste(IIS)-Manager. Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.
    
- Die Leistungsindikatoren **CPU** und **Prozessor**.
    
Bei den meisten Bereitstellungen sollte die Mobilitätsdienst-CPU-Auslastung im Durchschnitt unter 15 % liegen. Die Speicherauslastung sollte innerhalb der grenzen liegen, die unter [Monitor for server memory capacity limits in Skype for Business Server beschrieben sind.](server-memory-capacity-limits.md)
  
Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden ASP.NET-Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:
  
- **ASP.NET v2.0.50727\Requests Current**, der die Anzahl der ausstehenden Webanforderungen auf dem Server angibt. Wenn dieser Indikator 5.000 erreicht, tritt bei nachfolgenden Anforderungen die Fehlermeldung "503 - Dienst nicht verfügbar" auf.
    
- **ASP.NET\Requests Queued** (sollte immer Null sein).
    
> [!NOTE]
> Wenn Sie diese Werte erfüllen oder überschreiten, sollten Sie Ihre Kapazitätsplanung für die richtige Größenanpassung der CPU, der Anzahl der Kerne und des Arbeitsspeichers für die Computer, die die Webdienste hosten, erneut durcharbeiten. 

> [!NOTE]
> Die McX (Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits unified Communications Web API (UCWA), um Chat, Anwesenheit und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
## <a name="see-also"></a>Weitere Informationen

[Überwachen auf Kapazitätsgrenzen für den Serverspeicher in Skype for Business Server](server-memory-capacity-limits.md)
