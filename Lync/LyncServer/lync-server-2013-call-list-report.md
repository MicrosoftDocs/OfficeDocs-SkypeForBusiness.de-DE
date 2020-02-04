---
title: 'Lync Server 2013: Anruflistenbericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce2954f848d448676aea2931cda4dffa8ddc0c5d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a>Bericht zur Anrufliste in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Der Anruflistenbericht enthält QoE-Metriken (Quality of Experience) für einzelne Anrufe, die in Ihrer Organisation getätigt oder empfangen wurden. Beachten Sie, dass die tatsächlich im Bericht verzeichneten Metriken davon abhängen, wie Sie auf den Anruflistenbericht zugreifen. Wenn Sie beispielsweise den Bericht aus dem [gerätebericht in lync Server 2013](lync-server-2013-device-report.md)öffnen, werden Metriken wie die folgenden Metriken angezeigt, die auch im gerätebericht angezeigt werden:

  - Mikrofon des Anrufers

  - Lautsprecher des Anrufers

  - Mikrofon des Angerufenen

  - Lautsprecher des Angerufenen

  - Anteil Sprachumschaltzeit

Wenn Sie den Anruflistenbericht aber über den [Standortbericht in lync Server 2013](lync-server-2013-location-report.md)öffnen, werden keine dieser Metriken angezeigt. Stattdessen werden Metriken wie die folgenden angezeigt:

  - Roundtrip (ms)

  - Beeinträchtigung (MOS)

  - Paketverlust

  - Jitter (ms)

Dies sind Metriken aus dem Standortbericht. Im Anruflistenbericht können Sie jedoch jederzeit auf die Metrikdetails klicken und zu allen Anrufen vollständige QoE-Informationen anzeigen.

<div>

## <a name="accessing-the-call-list-report"></a>Zugriff auf den Anruflistenbericht

Auf den Anruflistenbericht kann über alle folgenden Berichte zugegriffen werden:

  - Der [Standortbericht in lync Server 2013](lync-server-2013-location-report.md) (durch Klicken auf die Lautstärke des Anrufs oder die prozentuale Kennzahl für schlechten Anruf)

  - Der [gerätebericht in lync Server 2013](lync-server-2013-device-report.md) (durch Klicken auf die Lautstärke des Anrufs oder die prozentuale Kennzahl für schlechten Anruf)

  - Der [Bericht zur Zusammenfassung der Medienqualität in lync Server 2013](lync-server-2013-media-quality-summary-report.md) (durch Klicken auf das Anrufvolumen oder die prozentuale Kennzahl für schlechten Anruf)

  - Der [Server Leistungsbericht in lync Server 2013](lync-server-2013-server-performance-report.md) (durch Klicken auf das Anrufvolumen oder die prozentuale Kennzahl für schlechten Anruf)

Innerhalb des Anruflisten Berichts können Sie auf den [Anruf Detailbericht in lync Server 2013](lync-server-2013-call-detail-report.md) zugreifen, indem Sie auf die Detail Metrik klicken.

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a>Optimale Verwendung des Anruflistenberichts

Wenn Sie vergessen haben, wofür einige der Anruflistenberichtsmetriken stehen (z. B. der Anteil Sprachumschaltzeit), bewegen Sie den Mauszeiger über die Beschriftung der Metrik, damit eine QuickInfo mit einer kurzen Beschreibung der Metrik angezeigt wird.

</div>

<div>

## <a name="filters"></a>Filter

Keine. Sie können den Anruflistenbericht nicht filtern.

</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die im Anruflistenbericht enthaltenen Informationen für jeden Anruf aufgeführt.

### <a name="call-list-report-metrics"></a>Anruflistenbericht-Metriken

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
<td><p><strong>Anrufer</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse der Person, die den Anruf initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Callee</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse der Person, die angerufen wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Startzeitpunkt</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit des Beginns des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Endzeitpunkt</strong></p></td>
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
<td><p>Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 100 ms oder weniger gilt als akzeptable Qualität.</p>
<p>Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Beeinträchtigung (MOS)</strong></p></td>
<td><p>Ja</p></td>
<td><p>Die durchschnittliche Beeinträchtigung der Qualität, die gemäß Mean Opinion Score (MOS) während eines Anrufs auftrat. Die Beeinträchtigungswerte liegen zwischen 0,0 (schlecht) und 5,0 (gut). Ein Wert von 0,5 oder weniger gilt als akzeptable Beeinträchtigung. Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ. In lync Server verwendet lync Server einen Satz von Algorithmen, um vorherzusagen, wie Benutzer einen Anruf bewertet hätten.</p>
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
<td><p>Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für die &quot;Zittern&quot; eines Anrufs.) Starke Jitterwerte werden in der Regel durch Überlastung oder einen überladenen Medienserver verursacht, was zu verzerrten oder verlorenen Audiodaten führt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ausblendungsverhältnis der Reparatur</strong></p></td>
<td><p>Ja</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum „Glätten“ der „holprigen“ Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Streckungsverhältnis der Reparatur</strong></p></td>
<td><p>Ja</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.</p></td>
</tr>
<tr class="even">
<td><p><strong>Komprimierungsverhältnis der Reparatur</strong></p></td>
<td><p>Ja</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu einer zu schnellen Sprachwiedergabe oder zu verzerrter Sprachqualität.</p></td>
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


</div>

</div>

<span> </span>

</div>

</div>

</div>

