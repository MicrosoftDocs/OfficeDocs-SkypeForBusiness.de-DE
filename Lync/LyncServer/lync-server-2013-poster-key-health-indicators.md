---
title: 'Lync Server 2013: Poster: wichtige Integritätsindikatoren'
description: 'Lync Server 2013: Poster: wichtige Integritätsindikatoren.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9962d1764d5d2c664bb8415261344d9b48c81149
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566341"
---
# <a name="key-health-indicators-in-lync-server-2013"></a>Wichtige Integritätsindikatoren in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-10_

Dieser Artikel ist ein Begleiter zu den [wichtigsten Integritätsindikatoren: die Grundlage für die Verwaltung eines gesunden Posters für lync Server](https://go.microsoft.com/fwlink/?linkid=391838) , das Sie aus dem Download Center herunterladen können.

![Poster zur Beschreibung der Problembehandlung mithilfe von KHI-Daten](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster zur Beschreibung der Problembehandlung mithilfe von KHI-Daten")

Sie können dieses Poster verwenden, um Informationen zu wichtigen Integritätsindikatoren (KHIs), Leistungsindikatoren mit Schwellenwerten für die Offenlegung von Problemen mit der Benutzerfreundlichkeit zu erhalten. Das Sammeln von KHI-Daten ist in der Regel der erste Schritt zur Implementierung der Call Quality Method (CQM), die sich auf die Sicherstellungeiner qualitativ hochwertigen Audioerfahrung für lync-Benutzer konzentriert.

Wenn Sie Fragen zur Verwendung von CQM haben, können Sie Ihre Fragen an cqmfeedback@Microsoft.com übermitteln.

Das Poster erläutert die folgenden Bereiche:

  - Was sind die wichtigsten Integritätsindikatoren?

  - So erfassen Sie KHI-Daten

  - Korrektur Fluss für alle Server Rollen

  - Glossar

  - Front-End-Server

  - Back-End-SQL-Server

  - Vermittlungsserver

  - Edgeserver

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>Was sind die wichtigsten Integritätsindikatoren?

Wichtige Integritätsindikatoren sind Leistungsindikatoren mit Schwellenwerten für die Offenlegung von Problemen mit der Benutzeroberfläche. Das Sammeln von KHI-Daten ist in der Regel der erste Schritt zur Implementierung der Call Quality Method (CQM), die sich auf die Sicherstellungeiner qualitativ hochwertigen Audioerfahrung für lync-Benutzer konzentriert.

KHIs werden zusätzlich zu den standardmäßigen lync-Überwachungslösungen (beispielsweise System Center Operations Manager, synthetische Transaktionen, Monitoring Server) und nicht anstelle dieser Lösungen verwendet.

Sammeln Sie die KHI-Leistungsindikatoren, und füllen Sie die KHI-Kalkulationstabelle mit dem Netzwerk Leit Faden aus, um eine Scorecard zu erstellen, mit der Sie den Serverstatus einer lync-Bereitstellung bestimmen können. Sobald die Anwendung aufgefüllt wurde, werden Sie bei der Reparatur der Umgebung unterstützt und bietet zusätzliche Einblicke für andere Beteiligte. Bewerten Sie KHIs monatlich, und integrieren Sie diese in die laufenden betrieblichen Prozesse der Bereitstellung.

Laden Sie das [lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) herunter, um die vollständige Liste der KHIs zu sehen und die zugehörigen Arbeitsblätter zu erhalten.

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>So erfassen Sie KHI-Daten

1.  Führen Sie das KHI-Skript aus, das im lync Server-Netzwerk Leit Faden auf jeder lync Server enthalten ist. Dadurch wird ein Datensammelpunkt in der Systemüberwachung erstellt und der Name khi. Standardmäßig werden die Daten alle 15 Sekunden abgefragt.

2.  Wechseln Sie vor dem Start des Geschäftstags Ihres Unternehmens zu jeder lync Server, und starten Sie den KHI-Datensammelpunkt.

3.  Beenden Sie am Ende dieses Tages den KHI-Datensammelpunkt, und kopieren Sie die Daten an einen zentralen Speicherort.

4.  Nachdem Sie den System Monitor verwendet haben, um die im lync Server Network Guide-Download enthaltene KHI-Kalkulationstabelle auszufüllen, vergleichen Sie die Ergebnisse mit den empfohlenen Zielen.

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>Korrektur Fluss für alle Server Rollen

Überprüfen Sie für jeden Server in ihrer lync-Implementierung zunächst, ob sich die Integrität der Komponente und die Systemleistung des Servers auf oder über der gewünschten Ebene befinden. Erst danach sollten Sie sich die Indikatoren ansehen, die sich auf die Rolle des Servers in der gesamten lync-Implementierung beziehen.

Beginnen Sie mit dem Sammeln von KHI-Leistungsdaten für alle Server. Ermitteln Sie für jede Systemrolle (Details weiter unten in diesem Dokument erläutert), ob die grundlegenden Systemkomponenten die empfohlenen Ziele erfüllen. Wenn dies nicht der Fall ist, stellen Sie die Systemleistung wieder her, sammeln Sie dann KHI-Daten, und stellen Sie sicher, dass die Systemintegrität überprüft wird, bevor Sie die für die Serverrolle in der lync-Implementierung spezifischen Metriken betrachten. Der Komponentenzustand für alle Rollen ist wie folgt definiert:

  - CPU-Auslastung \< 80%

  - AVG. Disk Write \< 10 ms

  - AVG. Disk Read \< 10 ms

  - Verfügbarer Arbeitsspeicher \> 20% System gesamt MB

  - Netzwerkwarteschlange (Länge \< 2)

  - Verworfene Pakete (in/out) = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>Glossar

Die folgenden Begriffe und Akronyme werden in diesem Poster verwendet:

AS MCU = Multi-Points-Steuereinheit für die Anwendungsfreigabe

AV MCU = Audio/Video-MCU

Chat MCU = Instant Messaging MCU

UCWA = Unified Communications-WebAPI

AV Edge = Traversieren von Audio/Video über Edge

AV auth = Audio/Video-Authentifizierung

SIP Stack = enthält die zentrale SIP-Implementierung von lync

Daten Proxy = wird für Edge-Konferenzen verwendet

LySS = lync-Speicherdienst

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>Front-End-Server

Die folgenden empfohlenen KHI-Ziele sind für Front-End-Server zusätzlich zur grundlegenden komponentenintegrität spezifisch:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Funktionsbereich</th>
<th>Ziel Metriken</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AS/AV/im MCU</p></td>
<td><p>MCU-Integritätsstatus &lt; 2</p></td>
</tr>
<tr class="even">
<td><p>Web Components</p></td>
<td><p>Verteilerlistenerweiterung AD Timeouts &lt; 0</p>
<p>ABWQ-Fehler = 0</p>
<p>LIS-Fehler = 0</p>
<p>Authentifizierungsfehler &lt; 1/s</p>
<p>ASP.net V4-Anforderungen abgelehnt = 0</p></td>
</tr>
<tr class="odd">
<td><p>SIP-Stack</p></td>
<td><p>AVG. eingehende Nachrichtenverarbeitung &lt; 1 Sek.</p>
<p>Eingehende Antworten fallen gelassen &lt; 1/sec eingehende Anfragen wurden um &lt; 1/Sek.</p>
<p>Warteschlangen Wartezeit &lt; 100 MS</p>
<p>Wartezeit in der Warte Prozedur &lt; 100 MS</p>
<p>Gedrosselte Anforderungen = 0</p>
<p>Authentifizierungsfehler &lt; 1/s</p>
<p>Timeout für eingehende Nachrichten &lt; 2</p>
<p>AVG. eingehende Nachricht halten &lt; 1 Sek.</p>
<p>Fluss gesteuerte Verbindungen &lt; 2</p>
<p>Verzögerung von AVG. Out-Warteschlange &lt; 2 Sek.</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>% des Speicherplatzes, der von der Speicherdienst-DB 80 verwendet wird &lt;</p>
<p># von Replikat Replikationsfehlern = 0</p>
<p># von Datenverlust Ereignissen = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Seiten Lebenserwartung &gt; 300 Sek.</p>
<p>Batch Anforderungen/Sek &lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>Back-End-SQL-Server

Die folgenden empfohlenen KHI-Ziele gelten zusätzlich zu den grundlegenden komponentenintegrität für SQL-Server:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Funktionsbereich</th>
<th>Ziel Metriken</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Seiten Lebenserwartung &gt; 300 Sek.</p>
<p>Batch Anforderungen/Sek &lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>Vermittlungsserver

Die folgenden empfohlenen KHI-Ziele gelten zusätzlich zu den grundlegenden komponentenintegrität für Vermittlungsserver:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Funktionsbereich</th>
<th>Ziel Metriken</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Vermittlungsserver Dienst</p></td>
<td><p>Fehler beim Laden des Anrufs Index = 0</p>
<p>Fehlgeschlagene Anrufe aufgrund von Proxy &lt; 10</p>
<p>Fehlgeschlagene Anrufe aufgrund von Gateway &lt; 10</p>
<p>Zurück geleitete Aufrufe (in oder out) = 0</p>
<p>Fehlende Medien Kandidaten = 0</p>
<p>Fehler bei der Medien Verbindungsüberprüfung = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>Edgeserver

Die folgenden empfohlenen KHI-Ziele gelten neben dem grundlegenden Zustand der Komponenten für Edgeserver spezifisch:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Funktionsbereich</th>
<th>Ziel Metriken</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AV-Authentifizierung</p></td>
<td><p>Ungültige Anforderungen &lt; 20/Sek.</p></td>
</tr>
<tr class="even">
<td><p>AV-Edge</p></td>
<td><p>Authentifizierungsfehler &lt; 20/Sek.</p>
<p>Zuordnungsfehler &lt; 20/Sek.</p>
<p>Gelöschte Pakete &lt; 300/s</p></td>
</tr>
<tr class="odd">
<td><p>Daten Proxy</p></td>
<td><p>Gedrosselte Server Verbindungen &lt; 3</p>
<p>Das System gibt die Drosselung 1 an. &lt;</p></td>
</tr>
<tr class="even">
<td><p>SIP-Stack</p></td>
<td><p>Verbindungen über Grenzwert sank &lt; 1</p>
<p>Sende Zeitüberschreitung &lt; 10</p>
<p>Fluss gesteuerte Verbindungen &lt; 100</p>
<p>Eingehende Anforderungen sanken &lt; 1/s</p>
<p>AVG. Message processing &lt; 3 sec</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Siehe auch


[Leitfaden für lync Server Netzwerke](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[Wichtige Integritätsindikatoren: die Grundlage für die Verwaltung gesunder lync-Server](https://go.microsoft.com/fwlink/?linkid=391838)  
[Methode für die lync-Anrufqualität](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

