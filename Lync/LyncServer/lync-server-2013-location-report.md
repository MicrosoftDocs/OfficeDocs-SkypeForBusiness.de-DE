---
title: 'Lync Server 2013: Standortbericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e98107d4949a935cbef448e1a533bddb0f7c5dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513792"
---
# <a name="location-report-in-lync-server-2013"></a>Standortbericht in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Der Standortbericht enthält Informationen zu Metriken für die Anrufqualität, gruppiert nach dem Netzwerkspeicherort (im Netzwerk-Subnetz). Wenn Ihre Benutzer Probleme mit ihren anrufen haben, kann dieser Bericht Ihnen helfen zu ermitteln, ob diese Probleme weit verbreitet sind oder ob Sie weitgehend auf ein bestimmtes Netzwerksegment beschränkt sind.

<div>

## <a name="accessing-the-location-report"></a>Zugreifen auf den Standortbericht

Auf den Standortbericht kann über die Startseite für Überwachungsberichte zugegriffen werden. Sie können den Call List Report anzeigen lassen, indem Sie auf eine der folgenden Metriken klicken:

  - Anrufvolumen

  - Prozentsatz der Anrufe schlechter Qualität

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie mit dem Standortbericht nach Dingen suchen, die den Standort haben, an dem ein Anruf entstanden ist, oder ob der Anruf über eine drahtlose oder eine kabelgebundene Verbindung stattfand. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle sind die Filter aufgeführt, die Sie mit dem Standortbericht verwenden können.

### <a name="location-report-filters"></a>Standort Berichtsfilter

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</p>
<p>07.07.2012 13:00</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ziel</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>07.07.2012 13:00</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Speicherort des Anrufers</strong></p></td>
<td><p>IP-Subnetz des Benutzers, der den Anruf getätigt hat. Sie können nur <strong>[alle]</strong> auswählen, um alle Subnetze anzugeben.</p></td>
</tr>
<tr class="even">
<td><p><strong>Speicherort des angerufenen</strong></p></td>
<td><p>IP-Subnetz des Benutzers, der den Anruf empfangen hat. Sie können nur <strong>[alle]</strong> auswählen, um alle Subnetze anzugeben.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Netzwerktyp</strong></p></td>
<td><p>Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:</p>
<ol>
<li><p>Alle</p></li>
<li><p>Wired</p></li>
<li><p>Drahtlos</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</p>
<ol>
<li><p>Alle</p></li>
<li><p>VPN</p></li>
<li><p>Nicht-VPN</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die Informationen aufgeführt, die im Standortbericht angegeben werden.

### <a name="location-report-metrics"></a>Metriken für den Standortbericht

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
<td><p><strong>Subnetz des Anrufers</strong></p></td>
<td><p>Nein</p></td>
<td><p>IP-Subnetz des Benutzers, der den Anruf getätigt hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Subnetz des angerufenen</strong></p></td>
<td><p>Nein</p></td>
<td><p>IP-Subnetz des Benutzers, der den Anruf empfangen hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anruflautstärke</strong></p></td>
<td><p>Ja</p></td>
<td><p>Die Gesamtzahl der getätigten Anrufe.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prozentsatz der Anrufe schlechter Qualität</strong></p></td>
<td><p>Ja</p></td>
<td><p>Prozentsatz der Anrufe, die als schlechte Anrufe klassifiziert wurden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Roundtrip (ms)</strong></p></td>
<td><p>Ja</p></td>
<td><p>Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 100 ms oder weniger gilt als akzeptable Qualität.</p>
<p>Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Beeinträchtigung (MOS)</strong></p></td>
<td><p>Ja</p></td>
<td><p>Die durchschnittliche Beeinträchtigung der Qualität, die gemäß Mean Opinion Score (MOS) während eines Anrufs auftrat. Die Beeinträchtigungswerte liegen zwischen 0,0 (schlecht) und 5,0 (gut). Ein Wert von 0,5 oder besser gilt als akzeptable Beeinträchtigung. Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ. In lync Server verwendet lync Server eine Reihe von Algorithmen, um vorherzusagen, wie Benutzer einen Anruf bewertet hätten.</p>
<p>Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Paketverlust</strong></p></td>
<td><p>Ja</p></td>
<td><p>Die durchschnittliche Rate an RTP-Paketverlusten. Zu Paketverlusten kommt es, wenn RTP-Pakete (RTP ist ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Jitter</strong></p></td>
<td><p>Ja</p></td>
<td><p>Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für die &quot; Zittern eines &quot; Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ausblendungsverhältnis der Reparatur</strong></p></td>
<td><p>Ja</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum "Glätten" der "holprigen" Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Streckungsverhältnis der Reparatur</strong></p></td>
<td><p>Ja</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Komprimierungsverhältnis der Reparatur</strong></p></td>
<td><p>Ja</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu zu schneller Sprachwiedergabe oder zu verzerrter Sprachqualität.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

