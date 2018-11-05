---
title: Key Health Indicators
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084824
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Key Health Indicators

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Dieser Artikel ist ein Begleiter für das Poster [Key Health Indicators: die Grundlage für die Aufrechterhaltung fehlerfreier Lync-Server](http://go.microsoft.com/fwlink/?linkid=391838), das Sie aus dem Download Center herunterladen können.

![Poster mit Beschreibung der Fehlerbehandlung mithilfe von KHI-Daten](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster mit Beschreibung der Fehlerbehandlung mithilfe von KHI-Daten")

Auf diesem Poster erfahren Sie mehr über Key Health Indicators (KHIs), Leistungsindikatoren mit Schwellenwerten, die darauf ausgerichtet sind, Probleme mit der Benutzerfreundlichkeit offenzulegen. Das Sammeln von KHI-Daten ist in der Regel der erste Schritt für die Implementierung der Call Quality Methodology (CQM), deren Schwerpunkt darauf liegt, ein hochwertiges Audioerlebnis für Lync-Benutzer zu sichern.

Fragen zur Verwendung von CQM können Sie an cqmfeedback@microsoft.com senden.

Auf dem Poster werden die folgenden Bereiche erklärt:

  - Was sind Key Health Indicators?

  - So sammeln Sie KHI-Daten

  - Wartungsfluss für alle Serverrollen

  - Glossar

  - Front-End-Server

  - Back-End-SQL-Server

  - Vermittlungsserver

  - Edgeserver

## Was sind Key Health Indicators?

Key Health Indicators sind Leistungsindikatoren mit Schwellenwerten, die darauf ausgerichtet sind, Probleme mit der Benutzerfreundlichkeit offenzulegen. Das Sammeln von KHI-Daten ist in der Regel der erste Schritt bei der Implemtierung der Call Quality Methodology (CQM), deren Schwerpunkt darauf liegt, ein hochwertiges Audioerlebenis für Lync-Benutzer zu sichern.

KHIs werden zusätzlich zu Lync-Standardüberwachungslösungen (z. B. System Center Operations Manager, Synthetic Transactions, Monitoring Server) verwendet, nicht anstelle dieser Lösungen.

Sammeln Sie die KHI-Leistungsindikatoren und füllen Sie das KHI-Arbeitsblatt aus, das mit dem Netzwerkhandbuch bereitgestellt wird, um eine Bewertung zu erstellen, die Ihnen hilft, die Serverintegrität einer Lync-Bereitstellung zu ermitteln. Nach dem Ausfüllen ist das Arbeitsblatt eine Anleitung für die Reparatur der Umgebung und stellt zusätzliche Einblicke für andere Beteiligte bereit. Werten Sie KHIs auf monatlicher Basis aus und binden Sie sie in die laufenden betrieblichen Prozesse jeder Bereitstellung ein.

Laden Sie das [Lync Server-Netzwerkhandbuch](http://go.microsoft.com/fwlink/p/?linkid=390677) herunter, um eine vollständige Liste der KHIs anzusehen und die damit zusammenhängenden Arbeitsblätter zu erhalten.

## So sammeln Sie KHI-Daten

1.  Führen Sie das mit dem Lync Server-Netzwerkhandbuch ausgelieferte KHI-Skript auf jedem Lync-Server aus. Damit wird ein Datensammler in der Leistungsüberwachung mit dem Namen "KHI" erstellt. Standardmäßig werden alle 15 Sekunden Daten abgefragt.

2.  Rufen Sie vor Beginn des Arbeitstages in Ihrem Unternehmen jeden Lync-Server auf und starten Sie den KHI-Datensammler.

3.  Am Ende des Tages beenden Sie den KHI-Datensammler und kopieren die Daten an einen zentralen Standort.

4.  Nachdem Sie das im Download des Lync Server-Netzwerkhandbuchs enthaltene KHI-Arbeitsblatt mithilfe der Leistungsüberwachung ausgefüllt haben, vergleichen Sie die Ergebnisse mit den empfohlenen Zielen.

## Wartungsfluss für alle Serverrollen

Beginnen Sie für jeden Server in Ihrer Lync-Implementierung mit der Überprüfung, ob die Integritäts- und Systemleistung der Serverkomponente dem gewünschten Grad entspricht oder darüber liegt. Erst danach sollten Sie sich die Indikatoren ansehen, die mit der Rolle des Servers in der allgemeinen Lync-Implementierung zusammenhängen.

Beginnen Sie mit dem Sammeln von KHI-Leistungsdaten für alle Server. Legen Sie für jede der Systemrollen (die später in diesem Dokument ausführlich dargestellt werden) fest, ob die grundlegenden Systemkomponenten den empfohlenen Zielen entsprechen. Falls nicht, warten Sie die Systemleistung und sammeln Sie dann erneut KHI-Daten. Stellen Sie die Systemintegrität sicher, bevor Sie sich die für die Rolle des Servers in der Lync-Implementierung spezifischen Kennzahlen ansehen. Die Komponentenintegrität für alle Rollen wird wie folgt definiert:

  - CPU-Auslastung \< 80 %

  - Durchschn. Datenträgerschreibvorgänge \< 10 ms

  - Durchschn. Datenträgerlesevorgänge \< 10 ms

  - Verfügbarer Speicher \> 20 % der Gesamt-MB des Systems

  - Netzwerkwarteschlangenlänge \< 2

  - Verworfene Pakete (ein-/ausgehend) = 0

## Glossar

Die folgenden Begriffe und Abkürzungen werden auf diesem Poster verwendet:

AS MCU = Multipoint Control Unit (MCU) für Anwendungsfreigaben

AV MCU = Audio/Video-MCU

IM MCU = Chat-MCU

UCWA = Unified Communications Web-API

AV Edge = Überquerung von Audio/Video über Edge

AV Auth = Audio-/Videoauthentifizierung

SIP Stack = enthält die Kern-SIP-Implementierung von Lync

Data Proxy = verwendet für Edgekonferenzen

LySS = Lync-Speicherdienst

## Front-End-Server

Die folgenden empfohlenen KHI-Ziele sind zusätzlich zur grundlegenden Komponentenintegrität für Front-End-Server spezifisch:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Funktionsbereich</th>
<th>Zielkennzahlen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AS/AV/IM-MCU</p></td>
<td><p>MCU-Integritätsstatus &lt;2</p></td>
</tr>
<tr class="even">
<td><p>Webkomponenten</p></td>
<td><p>AD-Timeouts für Verteilerlistenerweiterung &lt;0</p>
<p>ABWQ-Ausfälle = 0</p>
<p>LIS-Ausfälle = 0</p>
<p>Authentifizierungsfehler &lt; 1/Sek</p>
<p>Abgelehnte ASP.NET v4-Anforderungen = 0</p></td>
</tr>
<tr class="odd">
<td><p>SIP-Stack</p></td>
<td><p>Durchschn. Verarbeitung eingehender Nachrichten &lt; 1 Sek</p>
<p>Gelöschte eingehende Antworten &lt; 1/Sek Gelöschte eingehende Anforderungen &lt; 1/Sek</p>
<p>Warteschlangenlatenz &lt; 100 ms</p>
<p>Sproc-Latenz &lt; 100 ms</p>
<p>Gedrosselte Anforderungen = 0</p>
<p>Authentifizierungsfehler &lt; 1/Sek</p>
<p>Timeout bei eingehenden Nachrichten &lt; 2</p>
<p>Durchschn. Halten eingehender Nachrichten &lt; 1 Sek</p>
<p>Flusskontrollierte Verbindungen &lt; 2</p>
<p>Durchschn. Verzögerung der ausgehenden Warteschlange &lt; 2 Sek</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>% des Speicherplatzes, der von der Speicherdienst-DB verwendet wird &lt; 80</p>
<p>Anzahl von Replikatsreplikationsfunktionen = 0</p>
<p>Anzahl der Datenverlustereignisse = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Seitenlebenserwartung &gt; 300 Sek</p>
<p>Stapelanforderungen/Sek &lt; 2500</p></td>
</tr>
</tbody>
</table>


## Back-End-SQL-Server

Die folgenden empfohlenen KHI-Ziele sind zusätzlich zur grundlegenden Komponentenintegrität für SQL-Server spezifisch:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Funktionsbereich</th>
<th>Zielkennzahlen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Seitenlebenserwartung &gt; 300 Sek</p>
<p>Stapelanforderungen/Sek &lt; 2500</p></td>
</tr>
</tbody>
</table>


## Vermittlungsserver

Die folgenden empfohlenen KHI-Ziele sind zusätzlich zur grundlegenden Komponentenintegrität für Vermittlungsserver spezifisch:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Funktionsbereich</th>
<th>Zielkennzahlen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Vermittlungsserverdienst</p></td>
<td><p>Laden von Anruffehlerindex = 0</p>
<p>Fehlgeschlagene Anrufe wegen Proxy &lt;10</p>
<p>Fehlgeschlagene Anrufe wegen Gateway &lt;10</p>
<p>Abgelehnte Anrufe (ein- oder ausgehendt) = 0</p>
<p>Fehlende Medienkandidaten = 0</p>
<p>Fehler bei Medienverbindungsüberprüfungen = 0</p></td>
</tr>
</tbody>
</table>


## Edgeserver

Die folgenden empfohlenen KHI-Ziele sind zusätzlich zur grundlegenden Komponentenintegrität für Edgeserver spezifisch:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Funktionsbereich</th>
<th>Zielkennzahlen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AV Auth</p></td>
<td><p>Ungültige Anforderungen &lt; 20/Sek</p></td>
</tr>
<tr class="even">
<td><p>AV Edge</p></td>
<td><p>Authentifizierungsfehler &lt;20/Sek</p>
<p>Zuweisungsfehler &lt;20/Sek</p>
<p>Verworfene Pakete &lt;300/Sek</p></td>
</tr>
<tr class="odd">
<td><p>Datenproxy</p></td>
<td><p>Gedrosselte Serververbindungen &lt; 3</p>
<p>System wird gedrosselt &lt;1</p></td>
</tr>
<tr class="even">
<td><p>SIP-Stack</p></td>
<td><p>Verworfene Verbindungen über Limit &lt; 1</p>
<p>Senden von Timeout &lt;10</p>
<p>Flussgesteuerte Verbindungen &lt;100</p>
<p>Verworfene eingehende Anforderungen &lt; 1/Sek</p>
<p>Durchschn. Nachrichtenverarbeitung &lt; 3 Sek</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Weitere Ressourcen

[Lync Server-Netzwerkhandbuch](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Key Health Indicators: die Grundlage für die Aufrechterhaltung fehlerfreier Lync-Server](http://go.microsoft.com/fwlink/?linkid=391838)  
[Lync Call Quality Methodology](http://go.microsoft.com/fwlink/?linkid=391841)

