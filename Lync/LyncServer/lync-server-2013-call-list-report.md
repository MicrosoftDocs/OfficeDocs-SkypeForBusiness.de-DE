---
title: 'Lync Server 2013: Anruflistenbericht'
description: 'Lync Server 2013: Anruflistenbericht.'
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
ms.openlocfilehash: 5b08d4c5f3011facc9cd8d4f6b2800638f3cc896
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561691"
---
# <a name="call-list-report-in-lync-server-2013"></a>Anruflistenbericht in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Der Anruflistenbericht enthält QoE-Metriken (Quality of Experience) für einzelne Anrufe, die in Ihrer Organisation getätigt und empfangen werden. Beachten Sie, dass die gemeldeten tatsächlichen Metriken davon abhängen, wie Sie auf den Anruflistenbericht zugreifen können. Wenn Sie beispielsweise den Bericht [im gerätebericht in lync Server 2013](lync-server-2013-device-report.md)öffnen, werden Metriken wie die folgenden Metriken angezeigt, die auch im gerätebericht angezeigt werden:

  - Mikrofon des Anrufers

  - Sprecher des Anrufers

  - Mikrofon des angerufenen

  - Sprecher des angerufenen

  - Verhältnis der Zeit für die Sprachumstellung

Wenn Sie den Anruflistenbericht jedoch über den [Standortbericht in lync Server 2013](lync-server-2013-location-report.md)öffnen, werden keine dieser Metriken angezeigt; Stattdessen werden Metriken wie die folgenden angezeigt:

  - Roundtrip (ms)

  - Beeinträchtigung (MOS)

  - Paketverlust

  - Jitter (ms)

Dies sind die Metriken, die im Standortbericht angegeben werden. Aus dem Anruflistenbericht können Sie jedoch jederzeit auf die Detail Metrik klicken, um vollständige QoE-Informationen für jeden Anruf bereitzustellen.

<div>

## <a name="accessing-the-call-list-report"></a>Zugreifen auf den Anruflistenbericht

Auf den Anruflistenbericht kann über einen der folgenden Berichte zugegriffen werden:

  - Der [Standortbericht in lync Server 2013](lync-server-2013-location-report.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz schlechter Anrufe")

  - Der [gerätebericht in lync Server 2013](lync-server-2013-device-report.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz schlechter Anrufe")

  - Der [zusammenfassende Bericht über Medienqualität in lync Server 2013](lync-server-2013-media-quality-summary-report.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz schlechter Anrufe")

  - Der [Bericht über die Server Leistung in lync Server 2013](lync-server-2013-server-performance-report.md) (durch Klicken auf die Metrik "Anruflautstärke" oder "Prozentsatz schlechter Anrufe")

Im Anruflistenbericht können Sie auf den [Anruf Detailbericht in lync Server 2013](lync-server-2013-call-detail-report.md) zugreifen, indem Sie auf die Metrik Detail klicken.

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a>Optimale Verwendung des Anruflisten Berichts

Wenn Sie nicht mehr wissen, welche Metriken für den Anruflistenbericht (beispielsweise die Zeit für das Verhältnis von VoIP-Umschaltungen) tatsächlich gemessen werden, halten Sie die Maus über dem metrischen Etikett; eine QuickInfo wird dann angezeigt, die Ihnen eine kurze Beschreibung der Metrik gibt.

</div>

<div>

## <a name="filters"></a>Filter

Keine. Der Anruflistenbericht kann nicht gefiltert werden.

</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die Informationen aufgeführt, die im Anruflistenbericht für jeden Anruf angegeben werden.

### <a name="call-list-report-metrics"></a>Metriken für den Anruflistenbericht

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
<td><p><strong>Details</strong></p></td>
<td><p>Nein</p></td>
<td><p>Wenn Sie auf dieses Element klicken, zeigt der Bericht zusätzliche Informationen über den Anruf an.</p></td>
</tr>
<tr class="even">
<td><p><strong>Caller</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse der Person, die den Anruf initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Aufgerufene</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse der Person, die aufgerufen wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Start time</strong></p></td>
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
<td><p>Software, die vom Endpunkt der Person, die den Anruf initiiert hat, verwendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Benutzer-Agent des Angerufenen</strong></p></td>
<td><p>Ja</p></td>
<td><p>Software, die vom Endpunkt der Person verwendet wurde, die aufgerufen wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Roundtrip (ms)</strong></p></td>
<td><p>Ja</p></td>
<td><p>Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 100 ms oder weniger gilt als akzeptable Qualität.</p>
<p>Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Beeinträchtigung (MOS)</strong></p></td>
<td><p>Ja</p></td>
<td><p>Die durchschnittliche Beeinträchtigung der Qualität, die gemäß Mean Opinion Score (MOS) während eines Anrufs auftrat. Die Beeinträchtigungswerte liegen zwischen 0,0 (schlecht) und 5,0 (gut). Ein Wert von 0,5 oder besser gilt als akzeptable Beeinträchtigung. Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ. In lync Server verwendet lync Server eine Reihe von Algorithmen, um vorherzusagen, wie Benutzer einen Anruf bewertet hätten.</p>
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
<td><p>Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für die &quot; Zittern eines &quot; Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ausblendungsverhältnis der Reparatur</strong></p></td>
<td><p>Ja</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum "Glätten" der "holprigen" Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
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
<td><p><strong>Konnektivität</strong></p></td>
<td><p>Ja</p></td>
<td><p>Typ der drahtlosen Kommunikationsverbindung. In der Regel ist dies einer der folgenden:</p>
<ul>
<li><p>Relay</p></li>
<li><p>Direkte</p></li>
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

