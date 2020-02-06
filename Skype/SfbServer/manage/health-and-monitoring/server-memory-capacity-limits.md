---
title: Überwachen der Kapazitätsgrenzen von Server Speicher in Skype for Business Server
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
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Grenzwerte für Server Speicherkapazität in Skype for Business Server überwachen.'
ms.openlocfilehash: 4f56fec8f3ed6900f4c4f1a97286dc14b66bb7c8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817704"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Überwachen der Kapazitätsgrenzen von Server Speicher in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Grenzwerte für Server Speicherkapazität in Skype for Business Server überwachen können.
  
> [!CAUTION]
> Die Informationen in diesem Thema, die sich auf die Kapazitätsplanung beziehen, bezieht sich nur auf lync 2010-Mobile Clients und den Mobilitätsdienst (MCX). Die Kapazitätsplanung für die Unified Communications Web-API (UCWA), die von den mobilen lync 2013-Clients verwendet wird, wird vom lync Server 2013, Planungs Tool, bereitgestellt. 

> [!NOTE]
> MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten. Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
Zwei Mobilitäts Leistungsindikatoren können Ihnen dabei helfen, Ihre aktuelle Nutzung zu ermitteln und Ihnen dabei zu helfen, die Kapazität für den Skype for Business Server-Mobilitätsdienst (MCX) zu planen und die Speicherauslastung für UCWA zu überwachen. Für UCWA ist die Zähler Kategorie **ls: Web-UCWA**. Für den Mobilitätsdienst (Mobility Service, MCX) befinden sich die Leistungsindikatoren unter der Kategorie **ls: Web-Mobile Communication Service**. Die zu überwachenden Leistungsindikatoren sind:
  
- **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements**: Dies ist die aktuelle Anzahl von Endpunkten, die über die UCWA oder den Mobilitätsdienst (Mcx) registriert wurden und aktive Anwesenheitsabonnements besitzen (Anzahl der immer verbundenen mobilen Benutzer).
    
- **Anzahl der derzeit aktiven Sitzungen**: Dies ist die aktuelle Anzahl von Endpunkten, die über UCWA oder den Mobilitätsdienst registriert wurden.
    
Wenn der Unterschied zwischen **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements** und **Anzahl der derzeit aktiven Sitzungen** im Laufe der Zeit gering ist, bedeutet dies, dass die meisten Benutzer ein Mobilgerät verwenden, dass immer verbunden ist, beispielsweise ein Android- oder Nokia-Mobilgerät (nur für Mcx). UCWA immer angeschlossene Geräte sind Apple-und Android-Geräte, auf denen lync 2013 Mobile-Clients ausgeführt werden. Wenn die **Anzahl der derzeit aktiven Sitzungen** sehr viel höher ist als die **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements**, weist dies darauf hin, dass mehr Benutzer ein Hintergrund-Endpunktgerät unter Mcx verwenden, z. B. ein Apple iOS-Gerät oder ein Windows Phone. (Windows Phone ist der einzige mobile lync 2013-Client, der als dieser registriert wird).
  
Sie sollten eine Grenze für die **derzeit aktive Sitzungsanzahl mit aktiven Anwesenheitsabonnements** und **derzeit aktiven Sitzungen zählen** -Leistungsindikatoren basierend auf ihrer erwarteten Nutzung, den Ergebnissen der Kapazitätsplanung und der laufenden Überwachung des mobilitätsdiensts und anderer Front-End-Server-Leistungsindikatoren festzulegen. Die festgelegten Beschränkungen sollten das Auswerten der Serverkapazität und das Auslösen von Warnungen bei einer Kapazitätsüberschreitung erlauben.
  
Um die entsprechenden Grenzwerte zu ermitteln, müssen Sie zunächst ermitteln, wie viel Arbeitsspeicher auf dem Front-End-Server für den Mobilitätsdienst zur Verfügung steht. Überwachen Sie die Leistungsindikatoren, um anhand der folgenden Formel festzustellen, ob zusätzliche Kapazität eingeplant werden muss:
  
Gesamtspeicher des MCX-mobilitätsdiensts (MB) = 164 + (400 + 134)/1024 * **zurzeit aktive Sitzungsanzahl mit aktiven Anwesenheitsabonnements** + 400/1024 * ( **derzeit aktive** - Sitzungsanzahl**mit aktiven Anwesenheitsabonnements**)
  
> [!IMPORTANT]
> Der Microsoft lync Server 2010-Kapazitäts Rechner ist eine Kalkulationstabelle, die alle Formeln enthält, mit denen ein Planner ermitteln kann, welche Anforderungen für die Skype for Business-Server gelten, einschließlich CPU, Arbeitsspeicher und Festplatte. Sie können [die Kalkulationstabelle und ein zugehöriges Dokument herunterladen](https://go.microsoft.com/fwlink/p/?LinkID=212657). 
  
Der Front-End-Server benötigt genügend Arbeitsspeicher, um den Mobilitätsdienst in Failover-Situationen zu unterstützen. Sie können den aktuellen verfügbaren Arbeitsspeicher auf dem Front-End-Server mithilfe des **Memory\Available MBytes** -Indikators oder mithilfe der zuvor erwähnten Formel überwachen, um die Menge des Arbeitsspeichers zu planen, den Sie vom Mobilitätsdienst erwarten.
  
Wenn die auf dem Front-End-Server verfügbare Arbeitsspeichermenge unter 1.500 MB liegt, wenn Sie die erwartete Anzahl von Mobilitäts Benutzern planen, müssen Sie weitere Hardware hinzufügen, um den Mobilitätsdienst zu unterstützen. Weitere Informationen finden Sie unter [Überwachen der Mobilität für die Leistung in Skype for Business Server](monitor-mobility-performance.md) in der Betriebsdokumentation.
  
## <a name="see-also"></a>Siehe auch

[Überwachen der Mobilität für die Leistung in Skype for Business Server](monitor-mobility-performance.md)
