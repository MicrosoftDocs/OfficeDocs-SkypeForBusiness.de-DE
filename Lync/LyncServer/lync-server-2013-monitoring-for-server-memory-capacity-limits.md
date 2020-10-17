---
title: 'Lync Server 2013: Überwachen der Kapazitätsgrenzwerte für Server Speicher'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 160d90a5a79291d18afdab00c23ff0a6726fa5b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531942"
---
# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>Überwachen der Kapazitätsgrenzwerte für Server Speicher in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> Die Informationen in diesem Thema, die sich auf die Kapazitätsplanung beziehen, beziehen sich nur auf lync 2010 Mobile-Clients und den Mobilitätsdienst (MCX). Die Kapazitätsplanung für die Unified Communications Web API (UCWA), die von den lync 2013 mobilen Clients verwendet wird, wird vom Planungs Tool lync Server 2013 bereitgestellt.



</div>

Zwei Mobilitäts Leistungsindikatoren helfen Ihnen bei der Ermittlung Ihrer aktuellen Nutzung und unterstützen Sie bei der Planung der Kapazität für den lync Server 2013 Mobilitätsdienst (MCX) sowie beim Überwachen der Speicherauslastung für UCWA. Für UCWA ist die Leistungsindikatorkategorie **ls: Online – UCWA**. Für den Mobilitätsdienst (MCX) befinden sich die Leistungsindikatoren unter der Kategorie **ls: mobiler Kommunikationsdienst**. Zu überwachende Leistungsindikatoren sind:

  - **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements**(Dies ist die aktuelle Anzahl von Endpunkten, die über UCWA registriert sind) oder der Mobilitätsdienst (MCX) mit aktiven Anwesenheitsabonnements (Anzahl von immer verbundenen mobilen Benutzern)

  - **Anzahl der derzeit aktiven Sitzungen**, bei der es sich um die aktuelle Anzahl von Endpunkten handelt, die über UCWA oder den Mobilitätsdienst registriert sind

Wenn der Unterschied zwischen der **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements** und der **aktuell aktiven Sitzungsanzahl** im Laufe der Zeit gering ist, bedeutet dies, dass die meisten Benutzer eines mobilen Geräts über ein immer verbundenes Gerät wie ein Android-oder Nokia Mobilgerät verfügen (nur für MCX). UCWA immer verbundene Geräte sind Apple-und Android-Geräte, auf denen lync 2013 Mobile Clients installiert sind). Wenn die **Anzahl der derzeit aktiven Sitzungen** viel höher ist als die Anzahl der **derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements**, deutet dies darauf hin, dass mehr Benutzer ein Hintergrund Endgerät wie ein Apple IOS-Gerät oder Windows Phone unter MCX verwenden. (Windows Phone ist der einzige lync 2013 Mobile Client, der sich als dieser registrieren wird).

Sie sollten einen Grenzwert für die **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements** und **derzeit aktiven Sitzungs Zähl** Leistungsindikatoren auf der Grundlage ihrer erwarteten Nutzung, der Kapazitäts Planungsergebnisse und der laufenden Überwachung des mobilitätsdiensts und anderer Front-End-Server Indikatoren festlegen. Mit den von Ihnen festgelegten Grenzwerten sollten Sie die Serverkapazität auswerten und Warnungen auslösen können, wenn die Kapazität überschritten wird.

Um die entsprechenden Grenzwerte zu ermitteln, müssen Sie zuerst bestimmen, wie viel Arbeitsspeicher im Front-End-Server für den Mobilitätsdienst verfügbar ist. Überwachen Sie die Leistungsindikatoren, um zu bestimmen, wann Sie eine zusätzliche Kapazität planen müssen, entsprechend der folgenden Formel:

Gesamtarbeitsspeicher des MCX-mobilitätsdiensts (MB) = 164 + (400 + 134)/1024 \* **derzeit aktive Sitzungsanzahl mit aktiven Anwesenheitsabonnements** + 400/1024 \* (**derzeit aktive Sitzungsanzahl** – derzeit aktive Sitzungsanzahl **mit aktiven Anwesenheitsabonnements**)

<div>


> [!IMPORTANT]  
> Der Microsoft lync Server 2010 Kapazitäts Rechner ist eine Arbeitsmappe, die mit allen Formeln vorab aufgefüllt ist, mit denen ein Planer bestimmen kann, welche Anforderungen für die Server gelten, einschließlich CPU, Arbeitsspeicher und Festplatte. Sie können das Arbeitsblatt und ein zugehöriges Dokument herunterladen: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

Der Front-End-Server benötigt genügend Arbeitsspeicher zur Unterstützung des mobilitätsdiensts in Failover-Situationen. Sie können den derzeit verfügbaren Arbeitsspeicher auf dem Front-End-Server überwachen, indem Sie den **Arbeitsspeicher \\ Verfügbare MBytes** verwenden oder die zuvor erwähnte Gleichung verwenden, um die Größe des Arbeitsspeichers zu planen, den Sie vom Mobilitätsdienst erwarten sollten.

Wenn der verfügbare Arbeitsspeicher auf dem Front-End-Server niedriger als 1.500 MB ist, wenn Sie die erwartete Anzahl von Mobilitäts Benutzern planen, müssen Sie weitere Hardware zur Unterstützung des mobilitätsdiensts hinzufügen. Weitere Informationen finden Sie unter [Monitoring Mobility for Performance in lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in der Betriebsdokumentation.

<div>

## <a name="see-also"></a>Siehe auch


[Überwachen der Mobilität auf Leistung in lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

