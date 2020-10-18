---
title: 'Lync Server 2013: Trend Bericht über Server Medienqualität'
description: 'Lync Server 2013: Trend Bericht zu Server Medienqualität.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7ac2482b967aab230c5522c2b6a76e10ced28e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578135"
---
# <a name="server-media-quality-trend-report-in-lync-server-2013"></a>Trend Bericht über Server Medienqualität in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-12_

Der Trend Bericht über die Server Medienqualität bietet Ihnen die Möglichkeit, bis zu fünf Server mit Metriken für die Qualität der Erfahrung, wie Anrufvolumen, Anruf Prozentsatz, Paketverlust und Jitter, grafisch zu vergleichen. Dies erleichtert die Ermittlung von Servern, die schlecht ausgeführt werden, Identifizieren von Servern, die nicht ausgelastet sind, oder identifizieren von Servern, die überlastet sind.

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a>Zugriff auf den Trend Bericht über Medienqualität für Server

Auf den Trend Bericht über Server Medienqualität kann über einen der folgenden Berichte zugegriffen werden:

  - [Bericht über die Server Leistung in lync Server 2013](lync-server-2013-server-performance-report.md) (durch Klicken auf die Trend Metrik)

  - [Anruf Detail Bericht in lync Server 2013](lync-server-2013-call-detail-report.md) (durch Klicken auf die Metrik A/V Edge Server. Wenn es sich bei dem Anrufer oder angerufenen um einen Server handelt, können Sie auch den Medien Trend Bericht über Serverqualität erreichen, indem Sie auf den Endpunktnamen klicken.)

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>Optimale Verwendung des Trend Berichts über Medienqualität in einem Server

Wenn Sie im [Bericht über Serverleistung in lync Server 2013](lync-server-2013-server-performance-report.md) für einen bestimmten Server auf die Trend Metrik klicken, wird der Trendbericht über die Medienqualität von Servern geöffnet. Es wird jedoch nur eine leere Instanz dieses Berichts angezeigt. der Server, den Sie im Bericht über Serverleistung ausgewählt haben, wird nicht auf dem Bildschirm angezeigt. Stattdessen müssen Sie diesen Server aus der Dropdownliste Server auswählen. Beachten Sie auch, dass die Dropdownliste Server eine Option Alle auswählen enthält. Diese Option ist nicht funktionsfähig, wenn Sie über mehr als 5 Server verfügen. der Trend Bericht "Server Medienqualität" kann nur Daten für maximal 5 Server gleichzeitig anzeigen.

Auf den vom Server Medienqualität-Trend Bericht angezeigten Diagrammen sind die Punkte Anruflautstärke und Prozentsatz armer Anrufe Hotlinks; Wenn Sie auf einen Punkt im Diagramm klicken, wird eine Instanz des [Anruflisten Berichts in lync Server 2013](lync-server-2013-call-list-report.md) angezeigt, in der die Gesamtzahl der Anrufe (oder schlechte Anrufe) für den angegebenen Zeitraum angezeigt wird.

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle sind die Filter aufgeführt, die Sie mit dem Trend Bericht über Medienqualität für Server verwenden können.

### <a name="server-media-quality-trend-report-filters"></a>Trend Berichtsfilter für Server Medienqualität

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
<td><p><strong>Intervall</strong></p></td>
<td><p>Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Stündlich (maximal 25 Stunden können angezeigt werden)</p></li>
<li><p>Täglich (maximal 31 Tage können angezeigt werden)</p></li>
<li><p>Wöchentlich (maximal 12 Wochen können angezeigt werden)</p></li>
</ul>
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall "Täglich" mit dem Startdatum 07.08.2012 und dem Enddatum 28.09.2012 ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</p></td>
</tr>
<tr class="even">
<td><p><strong>Servertyp</strong></p></td>
<td><p>Der Typ des Servers, der an dem Anruf beteiligt ist. Gültige Werte sind:</p>
<ul>
<li><p>Vermittlungsserver</p></li>
<li><p>A/V-Konferenzserver</p></li>
<li><p>A/V-Edgeserver</p></li>
<li><p>Gateway (Vermittlungsserver)</p></li>
<li><p>Gateway (Vermittlungsserver Umgehung)</p></li>
<li><p>Als Konferenz Server</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Server</strong></p></td>
<td><p>Name des Servers, der an der Sitzung beteiligt ist; diese Dropdownliste wird basierend auf dem Wert des Servertyp Filters automatisch aufgefüllt. Sie können bis zu fünf verschiedene Server auswählen, wenn Sie einen Bericht kompilieren.</p></td>
</tr>
<tr class="even">
<td><p><strong>Zugriffstyp</strong></p></td>
<td><p>Gibt an, ob der Teilnehmer am internen Netzwerk oder über das externe Netzwerk angemeldet war. Gültige Werte sind:</p>
<ul>
<li><p>Alle</p></li>
<li><p>Intern</p></li>
<li><p>Extern</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Netzwerktyp</strong></p></td>
<td><p>Gibt den Typ des Netzwerks an, mit dem der Teilnehmer verbunden war. Gültige Werte sind:</p>
<ul>
<li><p>Alle</p></li>
<li><p>Wired</p></li>
<li><p>Drahtlos</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Gibt an, ob ein externer Teilnehmer während der Sitzung eine VPN-Verbindung (Virtual Private Network) verwendet hat. Gültige Werte sind:</p>
<ul>
<li><p>Alle</p></li>
<li><p>VPN</p></li>
<li><p>Nicht-VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die Informationen aufgeführt, die im Trend Bericht über Medienqualität für Server angezeigt werden.

### <a name="server-media-quality-trend-report-metrics"></a>Metriken für den Trend Berichts Server Medienqualität

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
<td><p><strong>Anruflautstärke</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe.</p></td>
</tr>
<tr class="even">
<td><p><strong>Beeinträchtigung (MOS)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Durchschnittliche Anzahl von MOS-Einbußen (Mittleres Options Ergebnis), die während eines Anrufs erlitten haben. Die Werte für die Verschlechterung können zwischen einem Tiefstwert von 0,0 und einem Höchstwert von 5,0 liegen. ein Wert von 0,5 oder niedriger stellt eine akzeptable Beeinträchtigung dar. Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ. Lync Server verwendet eine Reihe von Algorithmen, um vorherzusagen, wie Benutzer einen Anruf bewertet hätten.</p>
<p>Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Prozentsatz der Anrufe schlechter Qualität</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</p></td>
</tr>
<tr class="even">
<td><p><strong>Roundtrip (ms)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Durchschnittliche Zeit (in Millisekunden), die für ein Real-Time Transport Protokoll Paket benötigt wird, um an einen Endpunkt und dann zurück zu reisen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</p>
<p>Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routing konfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Paketverlust</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport Protocol). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Jitter (ms)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für die &quot; Zittern eines &quot; Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ausblendungsverhältnis der Reparatur</strong></p></td>
<td><p>Nein</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum "Glätten" der "holprigen" Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Streckungsverhältnis der Reparatur</strong></p></td>
<td><p>Nein</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Komprimierungsverhältnis der Reparatur</strong></p></td>
<td><p>Nein</p></td>
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

