---
title: Überwachen von Serverspeicherkapazitätslimits in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Kapazitätsgrenzen des Serverspeichers in Skype for Business Server überwachen.'
---

# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Überwachen von Serverspeicherkapazitätslimits in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Serverspeicherkapazitätsgrenzen in Skype for Business Server überwachen.
  
> [!CAUTION]
> Die Informationen in diesem Thema, die sich auf die Kapazitätsplanung beziehen, beziehen sich nur auf Lync 2010 Mobile-Clients und den Mobilitätsdienst (Mcx). Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool. 

> [!NOTE]
> McX(Mobility Service)-Unterstützung für mobile Legacyclients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen Skype for Business mobile Clients verwenden bereits unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.
  
Zwei Leistungsindikatoren für Mobilität können Ihnen helfen, Ihre aktuelle Nutzung zu ermitteln und die Kapazität für den Skype for Business Server Mobility Service (Mcx) zu planen sowie die Speicherauslastung für UCWA zu überwachen. Für UCWA lautet die Zählerkategorie **LS:WEB - UCWA**. Für den Mobilitätsdienst (Mcx) befinden sich die Leistungsindikatoren in der Kategorie **"LS:WEB – Mobiler Kommunikationsdienst"**. Die zu überwachenden Indikatoren sind:
  
- **Anzahl der derzeit aktiven Sitzungen mit Aktiven Anwesenheitsabonnements**. Dies ist die aktuelle Anzahl von Endpunkten, die über UCWA oder den Mobilitätsdienst (Mcx) registriert wurden, die über aktive Anwesenheitsabonnements verfügen (Anzahl der immer verbundenen mobilen Benutzer).
    
- **Anzahl der derzeit aktiven Sitzungen**. Dies ist die aktuelle Anzahl von Endpunkten, die über UCWA oder den Mobilitätsdienst registriert wurden.
    
Wenn der Unterschied zwischen **der Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements** und der **Anzahl der derzeit aktiven Sitzungen** im Laufe der Zeit gering ist, bedeutet dies, dass die meisten Benutzer mobiler Geräte über ein immer verbundenes Gerät verfügen, z. B. ein mobiles Android- oder Nokia-Gerät (nur für Mcx). Zu den immer verbundenen UCWA-Geräten gehören Apple- und Android-Geräte mit Lync 2013 Mobile-Clients). Wenn **die Anzahl der derzeit aktiven Sitzungen** **bei Aktiven Anwesenheitsabonnements wesentlich höher ist als die Anzahl der derzeit aktiven Sitzungen**, bedeutet dies, dass mehr Benutzer ein Hintergrundendpunktgerät verwenden, z. B. ein Apple iOS-Gerät oder Windows Phone unter Mcx. (Windows Phone ist der einzige Lync 2013 Mobile-Client, der sich als dieser registriert).
  
Sie sollten einen Grenzwert für die **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements** und Leistungsindikatoren für **die Anzahl der derzeit aktiven Sitzungen** festlegen, basierend auf der erwarteten Nutzung, den Ergebnissen der Kapazitätsplanung und der fortlaufenden Überwachung des Mobilitätsdiensts und anderer Front-End-Serverzähler. Die von Ihnen festgelegten Grenzwerte sollten es Ihnen ermöglichen, die Serverkapazität auszuwerten und Warnungen auszulösen, wenn die Kapazität überschritten wird.
  
Um die entsprechenden Grenzwerte zu ermitteln, müssen Sie zunächst ermitteln, wie viel Arbeitsspeicher auf dem Front-End-Server für den Mobilitätsdienst verfügbar ist. Überwachen Sie die Leistungsindikatoren, um zu bestimmen, wann Sie zusätzliche Kapazität planen müssen, gemäß der folgenden Formel:
  
Gesamter vom Mcx Mobility Service (MB) verwendeter Arbeitsspeicher = 164 + (400 + 134) / 1024 * **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements** + 400 / 1024 * ( **Derzeit aktive Sitzung CountCurrently** -  **Active Session Count with Active Presence Subscriptions**)
  
> [!IMPORTANT]
> Der Microsoft Lync Server 2010-Kapazitätsrechner ist eine Tabellenkalkulation, die mit allen Formeln vorgefüllt wird, mit denen ein Planer bestimmen kann, welche Anforderungen für die Skype for Business Server gelten, einschließlich CPU, Arbeitsspeicher und Festplatte. Sie können [das Arbeitsblatt und ein zugeordnetes Dokument herunterladen](https://go.microsoft.com/fwlink/p/?LinkID=212657). 
  
Der Front-End-Server benötigt genügend verfügbaren Arbeitsspeicher, um den Mobilitätsdienst in Failoversituationen zu unterstützen. Sie können den aktuellen verfügbaren Speicher auf dem Front-End-Server überwachen, indem Sie den **Speicher\Verfügbare MB-Zähler** oder die zuvor genannte Formel verwenden, um die Menge des Arbeitsspeichers zu planen, den der Mobilitätsdienst voraussichtlich verwenden wird.
  
Wenn der verfügbare Arbeitsspeicher auf dem Front-End-Server niedriger als 1.500 MB ist, wenn Sie die erwartete Anzahl von Mobilitätsbenutzern planen, müssen Sie weitere Hardware hinzufügen, um den Mobilitätsdienst zu unterstützen. Weitere Informationen finden Sie unter [Überwachen der Mobilität für die Leistung in Skype for Business Server](monitor-mobility-performance.md) in der Betriebsdokumentation.
  
## <a name="see-also"></a>Siehe auch

[Überwachen der Mobilität auf Leistung in Skype for Business Server](monitor-mobility-performance.md)
