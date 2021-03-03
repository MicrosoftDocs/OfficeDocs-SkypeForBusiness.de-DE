---
title: Überwachen auf Kapazitätsgrenzen für den Serverspeicher in Skype for Business Server
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
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie kapazitätslimits für serverspeicher in Skype for Business Server überwachen.'
ms.openlocfilehash: f1423d840fdf690332081a8083617c3a072b373c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814295"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Überwachen auf Kapazitätsgrenzen für den Serverspeicher in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie in Skype for Business Server die Kapazitätsgrenzen für den Serverspeicher überwachen.
  
> [!CAUTION]
> Die Informationen in diesem Thema, die sich auf die Kapazitätsplanung beziehen, beziehen sich nur auf Lync 2010 Mobile-Clients und den Mobilitätsdienst (Mcx). Die Kapazitätsplanung für die Unified Communications Web API (UCWA), die von den Lync 2013 Mobile-Clients verwendet wird, wird vom Lync Server 2013-Planungstool bereitgestellt. 

> [!NOTE]
> Die McX (Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits unified Communications Web API (UCWA), um Chat, Anwesenheit und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
Mithilfe von zwei Leistungsindikatoren für die Mobilität können Sie Ihre aktuelle Nutzung ermitteln und die Kapazität für den Skype for Business Server Mobility Service (Mcx) planen sowie die Speicherauslastung für UCWA überwachen. Für UCWA ist die Zählerkategorie **LS:WEB - UCWA**. Für den Mobilitätsdienst (Mcx) befinden sich die Leistungsindikatoren unter der Kategorie **LS:WEB - Mobile Communication Service**. Die zu überwachenden Leistungsindikatoren sind:
  
- **Anzahl der** derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements, d. h. die aktuelle Anzahl von Endpunkten, die über UCWA oder den Mobilitätsdienst (Mcx) registriert sind, die über aktive Anwesenheitsabonnements verfügen (Anzahl der immer verbundenen mobilen Benutzer)
    
- **Anzahl der derzeit aktiven Sitzungen**, die aktuelle Anzahl von Endpunkten, die über UCWA oder den Mobilitätsdienst registriert sind
    
Wenn der  Unterschied zwischen der Anzahl der  derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements und der Anzahl der derzeit aktiven Sitzungen im Laufe der Zeit gering ist, bedeutet dies, dass die meisten Benutzer mobiler Geräte über ein immer verbundenes Gerät verfügen, z. B. ein mobiles Android- oder Nokia-Gerät (nur für Mcx). Zu den immer verbundenen UCWA-Geräten gehören Apple- und Android-Geräte mit Lync 2013 Mobile-Clients). Wenn  die Anzahl der derzeit aktiven Sitzungen wesentlich höher als die Anzahl der derzeit aktiven Sitzungen mit **aktiven** Anwesenheitsabonnements ist, bedeutet dies, dass mehr Benutzer ein Hintergrundendpunktgerät verwenden, z. B. ein Apple iOS-Gerät oder Windows Phone unter Mcx. (Windows Phone ist der einzige Lync 2013 Mobile-Client, der als dieser registriert wird).
  
Sie sollten einen Grenzwert  für die Anzahl der  derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements und Leistungsindikatoren für die Anzahl der derzeit aktiven Sitzungen basierend auf der erwarteten Nutzung, den Ergebnissen der Kapazitätsplanung und der fortlaufenden Überwachung des Mobilitätsdiensts und anderer Front-End-Serverindikatoren festlegen. Mit den von Ihnen festgelegten Grenzwerten sollten Sie die Serverkapazität auswerten und Warnungen auslösen können, wenn die Kapazität überschritten wird.
  
Um die entsprechenden Grenzwerte zu ermitteln, müssen Sie zunächst ermitteln, wie viel Arbeitsspeicher auf dem Front-End-Server für den Mobilitätsdienst verfügbar ist. Überwachen Sie die Leistungsindikatoren, um zu bestimmen, wann Zusätzliche Kapazität geplant werden muss, gemäß der folgenden Formel:
  
Gesamtspeicher, der vom #A0 (MB) verwendet wird = 164 + (400 + 134) / 1024 * Anzahl derzeit aktiver Sitzungen mit aktiven Anwesenheitsabonnements + 400 / 1024 * ( **Anzahl** derzeit aktiver Sitzungen mit aktiven  Anwesenheitsabonnements)  -  
  
> [!IMPORTANT]
> Der Microsoft Lync Server 2010-Kapazitätsrechner ist eine Kalkulationstabelle, die mit allen Formeln vorausgefüllt wird, mit denen ein Planer bestimmen kann, welche Anforderungen für die Skype for Business-Server erfüllt werden sollen, einschließlich CPU, Arbeitsspeicher und Festplatte. Sie können [die Kalkulationstabelle und ein zugeordnetes Dokument herunterladen.](https://go.microsoft.com/fwlink/p/?LinkID=212657) 
  
Der Front-End-Server benötigt genügend verfügbaren Arbeitsspeicher, um den Mobilitätsdienst in Failoversituationen zu unterstützen. Sie können den aktuell verfügbaren Arbeitsspeicher auf dem  Front-End-Server überwachen, indem Sie den Leistungsindikator Arbeitsspeicher\Verfügbare MB oder die zuvor erwähnte Gleichung verwenden, um die Menge an Arbeitsspeicher zu planen, die vom Mobilitätsdienst verwendet werden soll.
  
Wenn die auf dem Front-End-Server verfügbare Arbeitsspeichermenge bei der Planung der erwarteten Anzahl von Mobilitätsbenutzern unter 1.500 MB liegt, müssen Sie zur Unterstützung des Mobilitätsdiensts zusätzliche Hardware hinzufügen. Weitere Informationen finden Sie unter "Überwachen der Mobilität [für die Leistung in Skype for Business Server"](monitor-mobility-performance.md) in der Betriebsdokumentation.
  
## <a name="see-also"></a>Weitere Informationen

[Überwachen der Mobilität für die Leistung in Skype for Business Server](monitor-mobility-performance.md)
