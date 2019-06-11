---
title: 'Lync Server 2013: Überwachen der Speicher Kapazitätsgrenzwerte für Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68728c85b14231644b445569857896f34abe535f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>Überwachen der Speicher Kapazitätsgrenzwerte von Servern in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> Die Informationen in diesem Thema, die sich auf die Kapazitätsplanung beziehen, bezieht sich nur auf lync 2010-Mobile Clients und den Mobilitätsdienst (MCX). Die Kapazitätsplanung für die Unified Communications Web-API (UCWA), die von den mobilen lync 2013-Clients verwendet wird, wird vom lync Server 2013, Planungs Tool, bereitgestellt.



</div>

Zwei Mobilitäts Leistungsindikatoren können Ihnen dabei helfen, Ihre aktuelle Nutzung zu ermitteln und Ihnen bei der Planung der Kapazität für den lync Server 2013 Mobility Service (MCX) sowie beim Überwachen der Speicherauslastung für UCWA zu helfen. Für UCWA ist die Indikatorkategorie **ls: Web – UCWA**. Für den Mobilitätsdienst (Mobility Service, MCX) befinden sich die Leistungsindikatoren unter der Kategorie **ls: Web-Mobile Communication Service**. Die zu überwachenden Leistungsindikatoren sind:

  - **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements**: Dies ist die aktuelle Anzahl von Endpunkten, die über die UCWA oder den Mobilitätsdienst (Mcx) registriert wurden und aktive Anwesenheitsabonnements besitzen (Anzahl der immer verbundenen mobilen Benutzer).

  - **Anzahl der derzeit aktiven Sitzungen**: Dies ist die aktuelle Anzahl von Endpunkten, die über UCWA oder den Mobilitätsdienst registriert wurden.

Wenn der Unterschied zwischen **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements** und **Anzahl der derzeit aktiven Sitzungen** im Laufe der Zeit gering ist, bedeutet dies, dass die meisten Benutzer ein Mobilgerät verwenden, dass immer verbunden ist, beispielsweise ein Android- oder Nokia-Mobilgerät (nur für Mcx). UCWA immer angeschlossene Geräte sind Apple-und Android-Geräte, auf denen lync 2013 Mobile-Clients ausgeführt werden. Wenn die **Anzahl der derzeit aktiven Sitzungen** sehr viel höher ist als die **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements**, weist dies darauf hin, dass mehr Benutzer ein Hintergrund-Endpunktgerät unter Mcx verwenden, z. B. ein Apple iOS-Gerät oder ein Windows Phone. (Windows Phone ist der einzige mobile lync 2013-Client, der als dieser registriert wird).

Sie sollten eine Grenze für die **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements** und **derzeit aktiven Sitzungen-count** -Leistungsindikatoren auf der Grundlage ihrer erwarteten Nutzung, der Kapazitäts Planungsergebnisse und der laufenden Überwachung von Mobilitätsdienst und andere Front-End-Server-Leistungsindikatoren. Die festgelegten Beschränkungen sollten das Auswerten der Serverkapazität und das Auslösen von Warnungen bei einer Kapazitätsüberschreitung erlauben.

Um die entsprechenden Grenzwerte zu ermitteln, müssen Sie zunächst ermitteln, wie viel Arbeitsspeicher auf dem Front-End-Server für den Mobilitätsdienst zur Verfügung steht. Überwachen Sie die Leistungsindikatoren, um anhand der folgenden Formel festzustellen, ob zusätzliche Kapazität eingeplant werden muss:

Gesamtspeicher des MCX-mobilitätsdiensts (MB) = 164 + (400 + 134)/1024 \* **derzeit aktive Sitzungsanzahl mit aktiven Anwesenheitsabonnements** + 400/1024 \* (**derzeit aktive Sitzungsanzahl** – **zurzeit aktive Sitzungsanzahl mit aktiven Anwesenheitsabonnements**)

<div>


> [!IMPORTANT]  
> Der Microsoft lync Server 2010-Kapazitäts Rechner ist eine Kalkulationstabelle, die alle Formeln enthält, mit denen ein Planner ermitteln kann, welche Anforderungen für die Server gelten, einschließlich CPU, Arbeitsspeicher und Festplatte. Sie können die Kalkulationstabelle und ein zugehöriges Dokument herunterladen unter:<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

Der Front-End-Server benötigt genügend Arbeitsspeicher, um den Mobilitätsdienst in Failover-Situationen zu unterstützen. Sie können den aktuellen verfügbaren Arbeitsspeicher auf dem Front-End-Server überwachen, indem Sie den **Speicher\\verfügbaren MBytes** -Indikator verwenden oder die oben erwähnte Formel verwenden, um die Menge des Arbeitsspeichers zu planen, den der Mobilitätsdienst zu verwenden erwartet.

Wenn die auf dem Front-End-Server verfügbare Arbeitsspeichermenge unter 1.500 MB liegt, wenn Sie die erwartete Anzahl von Mobilitäts Benutzern planen, müssen Sie weitere Hardware hinzufügen, um den Mobilitätsdienst zu unterstützen. Weitere Informationen finden Sie unter Überwachen der [Mobilität für die Leistung in lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in der Betriebsdokumentation.

<div>

## <a name="see-also"></a>Siehe auch


[Überwachen der Mobilität für die Leistung in lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

