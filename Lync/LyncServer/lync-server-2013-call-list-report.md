---
title: 'Lync Server 2013: Anruflistenbericht'
TOCTitle: Anruflistenbericht
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615020(v=OCS.15)
ms:contentKeyID: 49294824
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anruflistenbericht in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der Anruflistenbericht enthält QoE-Metriken (Quality of Experience) für einzelne Anrufe, die in Ihrer Organisation getätigt oder empfangen wurden. Beachten Sie, dass die tatsächlich im Bericht verzeichneten Metriken davon abhängen, wie Sie auf den Anruflistenbericht zugreifen. Wenn Sie den Bericht z. B. über den [Gerätebericht in Lync Server 2013](lync-server-2013-device-report.md) öffnen, werden Metriken wie die folgenden angezeigt - Metriken, die auch im Gerätebericht enthalten sind:

  - Mikrofon des Anrufers

  - Lautsprecher des Anrufers

  - Mikrofon des Angerufenen

  - Lautsprecher des Angerufenen

  - Anteil Sprachumschaltzeit

Wenn Sie den Anruflistenbericht jedoch über den [Standortbericht in Lync Server 2013](lync-server-2013-location-report.md) öffnen, sind statt der genannten die folgenden Metriken enthalten:

  - Roundtrip (ms)

  - Beeinträchtigung (MOS)

  - Paketverlust

  - Jitter (ms)

Dies sind Metriken aus dem Standortbericht. Im Anruflistenbericht können Sie jedoch jederzeit auf die Metrikdetails klicken und zu allen Anrufen vollständige QoE-Informationen anzeigen.

## Zugriff auf den Anruflistenbericht

Auf den Anruflistenbericht kann über alle folgenden Berichte zugegriffen werden:

  - [Standortbericht in Lync Server 2013](lync-server-2013-location-report.md) (durch Klicken auf das Anrufvolumen oder den Prozentsatz Anrufe schlechter Qualität)

  - [Gerätebericht in Lync Server 2013](lync-server-2013-device-report.md) (durch Klicken auf das Anrufvolumen oder den Prozentsatz Anrufe schlechter Qualität)

  - [Zusammenfassender Bericht über Medienqualität in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (durch Klicken auf das Anrufvolumen oder den Prozentsatz Anrufe schlechter Qualität)

  - [Bericht über Serverleistung in Lync Server 2013](lync-server-2013-server-performance-report.md) (durch Klicken auf das Anrufvolumen oder den Prozentsatz Anrufe schlechter Qualität)

Aus dem Anruflistenbericht können Sie durch Klicken auf die Detailmetriken auf den [Anrufdetailbericht in Lync Server 2013](lync-server-2013-call-detail-report.md) zugreifen.

## Optimale Verwendung des Anruflistenberichts

Wenn Sie vergessen haben, wofür einige der Anruflistenberichtsmetriken stehen (z. B. der Anteil Sprachumschaltzeit), bewegen Sie den Mauszeiger über die Beschriftung der Metrik, damit eine QuickInfo mit einer kurzen Beschreibung der Metrik angezeigt wird.

## Filter

Keine. Sie können den Anruflistenbericht nicht filtern.

## Metriken

In der folgenden Tabelle sind die im Anruflistenbericht enthaltenen Informationen für jeden Anruf aufgeführt.

### Anruflistenbericht-Metriken

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Kann nach dieser Metrik sortiert werden?</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Beschreibung</strong></p></td>
<td><p>Nein</p></td>
<td><p>Wenn Sie auf dieses Element klicken, werden zusätzliche Informationen über den Anruf angezeigt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Caller</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse der Person, die den Anruf initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Callee</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse der Person, die angerufen wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Beginn</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit des Beginns des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Endzeit</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit des Endes des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>Benutzer-Agent des Anrufers</strong></p></td>
<td><p>Ja</p></td>
<td><p>Software, die vom Endpunkt der Person, die den Anruf initiiert hat, verwendet wird.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Benutzer-Agent des Angerufenen</strong></p></td>
<td><p>Ja</p></td>
<td><p>Software, die vom Endpunkt der Person, die angerufen wurde, verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>Roundtrip (ms)</strong></p></td>
<td><p>Ja</p></td>
<td><p>Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 100 ms oder weniger gilt als akzeptable Qualität.</p>
<p>Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Beeinträchtigung (MOS)</strong></p></td>
<td><p>Ja</p></td>
<td><p>Die durchschnittliche Beeinträchtigung der Qualität, die gemäß Mean Opinion Score (MOS) während eines Anrufs auftrat. Die Beeinträchtigungswerte liegen zwischen 0,0 (schlecht) und 5,0 (gut). Ein Wert von 0,5 oder besser gilt als akzeptable Beeinträchtigung. Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ. Lync Server ermittelt anhand mehrerer Algorithmen, wie die Benutzer einen Anruf bewertet hätten.</p>
<p>Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Paketverlust</strong></p></td>
<td><p>Ja</p></td>
<td><p>Die durchschnittliche Rate an RTP-Paketverlusten. Zu Paketverlusten kommt es, wenn RTP-Pakete (RTP ist ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Jitter</strong></p></td>
<td><p>Ja</p></td>
<td><p>Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das &quot;Zittern&quot; der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ausblendungsverhältnis der Reparatur</strong></p></td>
<td><p>Ja</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum &quot;Glätten&quot; der &quot;holprigen&quot; Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Streckungsverhältnis der Reparatur</strong></p></td>
<td><p>Ja</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.</p></td>
</tr>
<tr class="even">
<td><p><strong>Komprimierungsverhältnis der Reparatur</strong></p></td>
<td><p>Ja</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu zu schneller Sprachwiedergabe oder zu verzerrter Sprachqualität.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Verbindung</strong></p></td>
<td><p>Ja</p></td>
<td><p>Typ einer Kommunikationsverbindung über Funk. In der Regel wird damit einer der folgenden Typen bezeichnet:</p>
<ul>
<li><p>Vermittelt</p></li>
<li><p>Direkt</p></li>
</ul></td>
</tr>
</tbody>
</table>

