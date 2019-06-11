---
title: 'Lync Server 2013: Bericht zur Teilnahme an der Konferenz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fac854b9e296d744473593562f32430c6e21fc87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a>Bericht "Konferenzteilnahme Zeit" in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-04-23_

Mit dem Bericht über Zeitpunkt des Konferenzbeitritts können Sie bestimmen, wie lange die Benutzer benötigen, um einer Konferenz beizutreten. Dieser Bericht enthält die durchschnittliche Zeit für den Beitritt (in Millisekunden) sowie eine Übersicht darüber, wie viele Benutzer in maximal 2 Sekunden einer Konferenz beitreten konnten, wie viele Benutzer zwischen 2 und 5 Sekunden für den Konferenzbeitritt benötigten usw.

<div>

## <a name="accessing-the-conference-join-time-report"></a>Zugriff auf den Bericht über Zeitpunkt des Konferenzbeitritts

Auf den Bericht über den Zeitpunkt des Konferenzbeitritts können Sie über die Startseite für Überwachungsberichte zugreifen.

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Zeitpunkt des Konferenzbeitritts verwenden können.

### <a name="conference-join-time-report-filters"></a>Filter im Bericht über Zeitpunkt des Konferenzbeitritts

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
<td><p><strong>Intervall</strong></p></td>
<td><p>Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Stündlich (maximal 25 Stunden können angezeigt werden)</p></li>
<li><p>Täglich (maximal 31 Tage können angezeigt werden)</p></li>
<li><p>Wöchentlich (maximal 12 Wochen können angezeigt werden)</p></li>
<li><p>Monatlich (maximal 12 Monate können angezeigt werden)</p></li>
</ul>
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Wenn Sie beispielsweise das Tagesintervall mit einem Anfangstermin von 7/7/2012 und einem Enddatum von 2/28/2012 auswählen, werden die Daten für die Tage 8/7/2012 12:00 Uhr bis 9/7/2012 12:00 Uhr angezeigt (also insgesamt 31 Tage).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder Edgeservers. Sie können einen einzelnen Pool auswählen oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Konferenzsitzungen</strong></p></td>
<td><p>Der Sitzungstyp. Gültige Werte sind:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Konferenzzustandsobjekt-Sitzungen (der Konferenzzustand ist zentrale Richtlinie sowie Zustandsverwaltung für Online-Besprechungen und koordiniert alle Aspekte einer Konferenz)</p></li>
<li><p>Anwendungsfreigabe</p></li>
<li><p>A/V-Konferenzen</p></li>
</ul>
<p>Wenn Sie [Alle] auswählen, wird die Gesamtzeit für den Konferenzbeitritt oben im Bericht angezeigt. Beachten Sie, dass diese Gesamtwerte nur für Konferenzen sind, die mit Microsoft Exchange oder Microsoft Outlook geplant wurden.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Zeitpunkt des Konferenzbeitritts angegeben werden.

### <a name="conference-join-time-report-metrics"></a>Metriken im Bericht über Zeitpunkt des Konferenzbeitritts

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
<td><p><strong>Datum</strong></p>
<p>Der eigentliche Name dieser Metrik hängt vom ausgewählten Intervall ab.</p></td>
<td><p>Nein</p></td>
<td><p>Zeitpunkt (Datum und Uhrzeit), zu dem die Konferenz stattfand.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Mittelwert (ms)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die durchschnittliche Zeit (in Millisekunden), die die Teilnehmer für den Konferenzbeitritt benötigten.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sitzungen &lt; 2 Sekunden, Lautstärke</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Anzahl der Teilnehmer, die der Konferenz in weniger als 2 Sekunden beitreten konnten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungen &lt; 2 Sekunden, Prozentsatz</strong></p></td>
<td><p>Nein</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>Sitzungen 2-5 Sekunden, Anzahl</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Anzahl der Teilnehmer, die zwischen 2 und 5 Sekunden für den Konferenzbeitritt benötigten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungen 2-5 Sekunden, Prozentsatz</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Gesamtteilnehmer, die zwischen 2 und 5 Sekunden für den Konferenzbeitritt benötigten.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sitzungen 5-10 Sekunden, Anzahl</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Anzahl der Teilnehmer, die zwischen 5 und 10 Sekunden für den Konferenzbeitritt benötigten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungen 5-10 Sekunden, Prozentsatz</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Gesamtteilnehmer, die zwischen 5 und 10 Sekunden für den Konferenzbeitritt benötigten.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sitzungen &gt; 10 Sekunden, Lautstärke</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Anzahl der Teilnehmer, die mehr als 10 Sekunden für den Konferenzbeitritt benötigten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungen &gt; 10 Sekunden, Prozentsatz</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Gesamtteilnehmer, die mehr als 10 Sekunden für den Konferenzbeitritt benötigten.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

