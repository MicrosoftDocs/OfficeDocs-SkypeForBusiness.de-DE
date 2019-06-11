---
title: 'Lync Server 2013: Bericht zum Vergleich der Medienqualität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6697e02d7b821ebd3dc3cabc3a95c8d00960a08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a>Bericht zum Vergleich der Medienqualität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-04-22_

Mit dem Bericht über die Medienqualität können Sie Anrufqualitätswerte für verschiedene Arten von Audioanrufen vergleichen (z. B. Anrufe über ein Funknetzwerk und Anrufe über eine Kabelverbindung).

<div>

## <a name="accessing-the-media-quality-comparison-report"></a>Zugreifen auf den Bericht über die Medienqualität

Auf den Vergleichsbericht über die Medienqualität greifen Sie auf der Startseite „Überwachungsberichte“ zu.

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über die Medienqualität verwenden können.

### <a name="media-quality-comparison-report-filters"></a>Filter im Bericht über die Medienqualität

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
<td><p><strong>Von</strong></p></td>
<td><p>Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</p>
<p>7/7/2012 1:00 Uhr</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bis</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>7/7/2012 1:00 Uhr</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anrufe</strong></p></td>
<td><p>Der Anruftyp, der als primäres Vergleichselement verwendet werden soll. Gültige Werte sind:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Extern</p></li>
<li><p>Intern</p></li>
<li><p>VPN</p></li>
<li><p>Nicht-VPN</p></li>
<li><p>Verkabelt</p></li>
<li><p>Funk</p></li>
<li><p>Extern und verkabelt</p></li>
<li><p>Extern und Funk</p></li>
<li><p>Extern und VPN</p></li>
<li><p>Extern und Nicht-VPN</p></li>
<li><p>Intern und verkabelt</p></li>
<li><p>Intern und Funk</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Mit Anrufen vergleichen</strong></p></td>
<td><p>Der Anruftyp, der als sekundäres Vergleichselement verwendet werden soll. Gültige Werte sind:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Extern</p></li>
<li><p>Intern</p></li>
<li><p>VPN</p></li>
<li><p>Nicht-VPN</p></li>
<li><p>Verkabelt</p></li>
<li><p>Funk</p></li>
<li><p>Extern und verkabelt</p></li>
<li><p>Extern und Funk</p></li>
<li><p>Extern und VPN</p></li>
<li><p>Extern und Nicht-VPN</p></li>
<li><p>Intern und verkabelt</p></li>
<li><p>Intern und Funk</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Intervall</strong></p></td>
<td><p>Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Stündlich (maximal 25 Stunden können angezeigt werden)</p></li>
<li><p>Täglich (maximal 31 Tage können angezeigt werden)</p></li>
<li><p>Wöchentlich (maximal 12 Wochen können angezeigt werden)</p></li>
</ul>
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Wenn Sie beispielsweise das Tagesintervall mit einem Anfangstermin von 7/7/2012 und einem Enddatum von 2/28/2012 auswählen, werden die Daten für die Tage 8/7/2012 12:00 Uhr bis 9/7/2012 12:00 Uhr angezeigt (also insgesamt 31 Tage).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden Metriken aufgelistet, die im Bericht über die Medienqualität angegeben werden.

### <a name="media-quality-comparison-report-metrics"></a>Metriken im Bericht über die Medienqualität

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
<td><p>Durchschnittliche Anzahl von MOS (Mean Opinion Score)-Verschlechterung während eines Anrufs. Die Werte für die Verschlechterung können von einem Tiefstwert von 0,0 bis zu einem Höchstwert von 5,0 liegen. ein Wert von 0,5 oder einer kleineren stellt eine akzeptable Verschlechterung dar. Historisch gesehen wurden durchschnittliche Meinungs Bewertungen berechnet, indem Benutzer die Qualität eines Anrufs auf einer Skala von 1 zu 5 bewertet haben. Lync Server verwendet eine Reihe von Algorithmen, um vorherzusagen, wie Benutzer einen Anruf bewertet hätten.</p>
<p>Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Prozentsatz der Anrufe schlechter Qualität</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</p></td>
</tr>
<tr class="even">
<td><p><strong>Roundtrip (ms)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport-Protokoll) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</p>
<p>Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Paketverlust</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll; ein Protokoll für die Übertragung von Audio und Video über das Internet). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Jitter (ms)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für die &quot;Zittern&quot; eines Anrufs.) Starke Jitterwerte werden in der Regel durch Überlastung oder einen überladenen Medienserver verursacht, was zu verzerrten oder verlorenen Audiodaten führt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ausblendungsverhältnis der Reparatur</strong></p></td>
<td><p>Nein</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum „Glätten“ der „holprigen“ Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Streckungsverhältnis der Reparatur</strong></p></td>
<td><p>Nein</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Komprimierungsverhältnis der Reparatur</strong></p></td>
<td><p>Nein</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu einer zu schnellen Sprachwiedergabe oder zu verzerrter Sprachqualität.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

