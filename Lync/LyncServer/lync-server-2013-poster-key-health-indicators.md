---
title: 'Lync Server 2013: Poster: wichtige Integritätsindikatoren'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9454197642ac87f5d8bc0d768795854d792f9a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a>Wichtige Integritätsindikatoren in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-10_

Dieser Artikel ist ein Begleiter zu den [wichtigsten Integritätsindikatoren: die Grundlage für die Verwaltung eines fehlerfreien lync Servers](http://go.microsoft.com/fwlink/?linkid=391838) -Plakats, das Sie aus dem Download Center herunterladen können.

Poster, das die ![Problembehandlung mithilfe von KHI-Daten beschreibt] Poster, das die (images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Problembehandlung mithilfe von KHI-Daten beschreibt")

Sie können dieses Poster verwenden, um Informationen zu wichtigen Integritätsindikatoren (KHIs), Leistungsindikatoren mit Schwellenwerten für die Anzeige von Problemen mit der Benutzeroberfläche zu erhalten. Das Sammeln von KHI-Daten ist in der Regel der erste Schritt zur Implementierung der Methode für die Anrufqualität (Call Quality Method, CQM), die auf die Gewährleistung einer Audioqualität für lync-Benutzer ausgerichtet ist.

Wenn Sie Fragen zur Verwendung von CQM haben, können Sie Ihre Fragen an cqmfeedback@Microsoft.com senden.

Das Poster erläutert die folgenden Bereiche:

  - Was sind die wichtigsten Statusindikatoren?

  - So erfassen Sie KHI-Daten

  - Korrektur Fluss für alle Server Rollen

  - Glossar

  - Front-End-Server

  - Back-End-SQL-Server

  - Vermittlungsserver

  - Edgeservers

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>Was sind die wichtigsten Statusindikatoren?

Zu den wichtigsten Integritätsindikatoren zählen Leistungsindikatoren mit Schwellenwerten, die darauf abzielen, Probleme mit der Benutzeroberfläche zu erkennen. Das Sammeln von KHI-Daten ist in der Regel der erste Schritt zur Implementierung der Methode für die Anrufqualität (Call Quality Method, CQM), die auf die Gewährleistung einer Audioqualität für lync-Benutzer ausgerichtet ist.

KHIs werden zusätzlich zu den standardmäßigen lync-Überwachungslösungen (z. b. System Center Operations Manager, synthetische Transaktionen, Monitoring Server) und nicht anstelle dieser Lösungen verwendet.

Sammeln Sie die KHI-Leistungsindikatoren, und füllen Sie die KHI-Kalkulationstabelle mit dem Netzwerk Leit Faden aus, um eine Scorecard zu erstellen, mit der Sie den Serverzustand einer lync-Bereitstellung ermitteln können. Sobald die Datei ausgefüllt ist, führt Sie Sie bei der Reparatur der Umgebung und gibt weiteren Einblick in andere Stakeholder. Bewerten Sie KHIs monatlich, und fügen Sie Sie in die laufenden operativen Prozesse der Bereitstellung ein.

Laden Sie den [lync Server-Netzwerk Leit Faden](http://go.microsoft.com/fwlink/p/?linkid=390677) herunter, um die vollständige Liste der KHIs anzuzeigen und die zugehörigen Kalkulationstabellen abzurufen.

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>So erfassen Sie KHI-Daten

1.  Führen Sie das KHI-Skript aus, das im lync Server-Netzwerk Leit Faden auf jedem lync-Server enthalten ist. Dadurch wird ein Datenauflister innerhalb des Systemmonitors erstellt und der Name khi. Standardmäßig werden Daten alle 15 Sekunden abgefragt.

2.  Wechseln Sie vor dem Beginn des Geschäftstages des Unternehmens zu jedem lync-Server, und starten Sie den KHI-Datensammler.

3.  Beenden Sie am Ende dieses Tages den KHI-Datenauflister, und kopieren Sie die Daten an eine zentrale Position.

4.  Nachdem Sie die mit dem lync Server Networking Guide-Download enthaltene KHI-Kalkulationstabelle mit dem System Monitor gefüllt haben, vergleichen Sie die Ergebnisse mit den empfohlenen Zielen.

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>Korrektur Fluss für alle Server Rollen

Stellen Sie für jeden Server in ihrer lync-Implementierung zunächst sicher, dass die komponentenintegrität und Systemleistung des Servers auf oder über dem gewünschten Wert liegen. Erst danach sollten Sie sich die Indikatoren in Bezug auf die Rolle des Servers in der gesamten lync-Implementierung anschauen.

Beginnen Sie mit dem Sammeln von KHI-Leistungsdaten für alle Server. Für jede Systemrolle (Details, die weiter unten in diesem Dokument erläutert werden) ermitteln Sie, ob die grundlegenden Systemkomponenten die empfohlenen Ziele erfüllen. Wenn dies nicht der Fall ist, beheben Sie die Systemleistung, und sammeln Sie dann KHI-Daten erneut, und stellen Sie die Systemintegrität sicher, bevor Sie sich die Metriken ansehen, die für die Rolle des Servers in der lync-Implementierung spezifisch sind. Der Komponentenstatus für alle Rollen ist wie folgt definiert:

  - CPU- \< Auslastung 80%

  - AVG. Disk schreibt \< 10 ms

  - AVG. Disk lesen \< Sie 10 ms

  - Verfügbarer Arbeitsspeicher \>20% System gesamt MB

  - Netzwerk-Warte \< schlangenlänge 2

  - Verworfene Pakete (in/out) = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>Glossar

Die folgenden Begriffe und Akronyme werden in diesem Poster verwendet:

Als MCU = Application Sharing Multi-Punkt-Steuereinheit

AV MCU = Audio/Video-MCU

IM MCU = Instant Messaging-MCU

UCWA = Unified Communications Web-API

AV Edge = durchlaufen von Audio/Video über Edge

AV auth = Audio/Video-Authentifizierung

SIP Stack = enthält die zentrale SIP-Implementierung von lync

Data Proxy = wird für Edge-Konferenzen verwendet

LySS = lync-Speicherdienst

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>Front-End-Server

Die folgenden empfohlenen KHI-Ziele sind für Front-End-Server zusätzlich zu den grundlegenden Komponentenstatus spezifisch:


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
<td><p>AS/AV/im-MCU</p></td>
<td><p>MCU-Integritätsstatus &lt;2</p></td>
</tr>
<tr class="even">
<td><p>Web-Komponenten</p></td>
<td><p>Erweiterung der Verteilerliste anzeigen Timeouts &lt;0</p>
<p>ABWQ-Fehler = 0</p>
<p>LIS-Fehler = 0</p>
<p>Authentifizierungs &lt; Fehler 1/Sek.</p>
<p>ASP.net V4-Anforderungen abgelehnt = 0</p></td>
</tr>
<tr class="odd">
<td><p>SIP-Stack</p></td>
<td><p>Verarbeitung &lt; von eingehenden Nachrichten 1 Sek.</p>
<p>Eingehende Antworten &lt; sanken 1/sec Eingeh &lt; Ende Anforderungen sanken 1/Sek.</p>
<p>Warteschlangen Wartezeit &lt; 100 MS</p>
<p>Latenz Wartezeit &lt; 100 MS</p>
<p>Gedrosselte Anforderungen = 0</p>
<p>Authentifizierungs &lt; Fehler 1/Sek.</p>
<p>Timeout für eingehende &lt; Nachrichten 2</p>
<p>Eingehende Nachrichten: &lt; 1 Sek.</p>
<p>Durchflussgesteuerte &lt; Verbindungen 2</p>
<p>Verzögerung &lt; von AVG. Out-Warteschlange 2 Sek.</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>% des vom Speicherdienst DB &lt; 80 verwendeten Speicherplatzes</p>
<p>#Replikat Replikationsfehler = 0</p>
<p>#von Datenverlust Ereignissen = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Lebenserwartung &gt; der Seite 300 Sek.</p>
<p>Batch Anforderungen/Sek &lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>Back-End-SQL-Server

Die folgenden empfohlenen KHI-Ziele gelten zusätzlich zu den grundlegenden Komponenten Integritäts Merkmalen für SQL-Server:


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
<td><p>Lebenserwartung &gt; der Seite 300 Sek.</p>
<p>Batch Anforderungen/Sek &lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>Vermittlungsserver

Die folgenden empfohlenen KHI-Ziele gelten speziell für Vermittlungsserver sowie für die grundlegende komponentenintegrität:


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
<td><p>Vermittlungs Server Dienst</p></td>
<td><p>Fehler beim Laden des Anrufs Index = 0</p>
<p>Fehlgeschlagene Anrufe &lt;wegen Proxy 10</p>
<p>Fehlgeschlagene Anrufe &lt;wegen Gateway 10</p>
<p>Anrufe (in oder aus) abgelehnt = 0</p>
<p>Medien Kandidaten fehlen = 0</p>
<p>Fehler bei der Medien Verbindungsüberprüfung = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>Edgeservers

Die folgenden empfohlenen KHI-Ziele gelten zusätzlich zu den grundlegenden Komponentenstatus speziell für Edge-Server:


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
<td><p>AV-auth</p></td>
<td><p>Ungültige Anforderungen &lt; 20/Sek.</p></td>
</tr>
<tr class="even">
<td><p>AV-Edge</p></td>
<td><p>Auth. Fehler &lt;20/Sek.</p>
<p>Zuordnungsfehler &lt;20/Sek.</p>
<p>Pakete, &lt;die 300/Sek. gelöscht wurden</p></td>
</tr>
<tr class="odd">
<td><p>Daten Proxy</p></td>
<td><p>Gedrosselte Server &lt; Verbindungen 3</p>
<p>System Drosselung &lt;1</p></td>
</tr>
<tr class="even">
<td><p>SIP-Stack</p></td>
<td><p>Verbindungen über Grenze sanken &lt; 1</p>
<p>Zeitüberschreitung bei &lt;Sends 10</p>
<p>Durchflussgesteuerte &lt;Verbindungen 100</p>
<p>Eingehende Anforderungen &lt; sanken auf 1/Sek.</p>
<p>AVG. Nachrichtenverarbeitung &lt; 3 Sek.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Siehe auch


[Lync Server-Netzwerkhandbuch](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Wichtige Integritätsindikatoren: die Grundlage für die Verwaltung von fehlerfreien lync-Servern](http://go.microsoft.com/fwlink/?linkid=391838)  
[Methodik der lync-Anrufqualität](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

