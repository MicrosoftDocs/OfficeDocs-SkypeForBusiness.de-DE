---
title: Überwachen des mobilitätsdiensts und der UCWA-Nutzung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Zusammenfassung: Verwalten des mobilitätsdiensts (MCX) und der Unified Communications Web-API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: 5447eb0ac8ffe468fd52c7011824cc1f2f2f7b55
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279795"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Überwachen des mobilitätsdiensts und der UCWA-Nutzung in Skype for Business Server
 
**Zusammenfassung:** Verwalten Sie den Mobilitätsdienst (MCX) und die Unified Communications Web-API (UCWA) in Skype for Business Server.

> [!NOTE]
> MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten. Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
Auf einer kontinuierlichen Basis sollten Sie die CPU und den Arbeitsspeicher überwachen, die von Skype for Business Server Mobility Service (MCX) und der Unified Communications Web-API (UCWA) verwendet werden. Zum Überwachen der Auslastung können Sie Folgendes verwenden:
  
 **Für die Unified Communications-Web-API (UCWA):**
  
- Der **LyncUcwa** -Workerprozess im Internet Informationsdienste (IIS)-Manager. Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.
    
- Die Leistungsindikatoren **CPU** und **Prozessor**.
    
Bei den meisten Bereitstellungen sollte die UCWA-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen. Die Speicherauslastung sollte innerhalb der in Skype for Business Server festgelegten Grenzwerte unter [Monitor für Server Speicherkapazität](server-memory-capacity-limits.md)liegen.
  
Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:
  
- **Ls: webdrosselungs-und Authentication\WEB Gesamtanforderungen in der Verarbeitung**, die die Anzahl der ausstehenden Webanforderungen auf dem Server angeben. Wenn dieser Leistungsindikator 10.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung „503 - Dienst nicht verfügbar“ fehl.
    
- **ASP.NET\Requests Queued** (sollte immer Null sein).
    
> [!NOTE]
> Wenn diese Werte erreicht oder überschritten werden, sollten Sie die Kapazitätsplanung für die Computer überarbeiten, die die Webdienste hosten, und die Größenanpassung für die CPU, die Anzahl von Kernen sowie den Arbeitsspeicher neu berechnen. 
  
 **Für den Mobilitätsdienst (Mcx):**
  
- Die **CSIntMcxAppPool** -und **CSExtMcxAppPool** -Arbeitsprozesse im Internet Informationsdienste (IIS)-Manager. Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.
    
- Die Leistungsindikatoren **CPU** und **Prozessor**.
    
Bei den meisten Bereitstellungen sollte die Mobilitätsdienst-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen. Die Speicherauslastung sollte innerhalb der in Skype for Business Server festgelegten Grenzwerte unter [Monitor für Server Speicherkapazität](server-memory-capacity-limits.md)liegen.
  
Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden ASP.NET-Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:
  
- **ASP.NET v2.0.50727\Requests Current**, der die Anzahl der ausstehenden Webanforderungen auf dem Server angibt. Wenn dieser Leistungsindikator 5.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung „503 - Dienst nicht verfügbar“ fehl.
    
- **ASP.NET\Requests Queued** (sollte immer Null sein).
    
> [!NOTE]
> Wenn diese Werte erreicht oder überschritten werden, sollten Sie die Kapazitätsplanung für die Computer überarbeiten, die die Webdienste hosten, und die Größenanpassung für die CPU, die Anzahl von Kernen sowie den Arbeitsspeicher neu berechnen. 

> [!NOTE]
> MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten. Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
## <a name="see-also"></a>Siehe auch

[Überwachen der Kapazitätsgrenzen von Server Speicher in Skype for Business Server](server-memory-capacity-limits.md)
