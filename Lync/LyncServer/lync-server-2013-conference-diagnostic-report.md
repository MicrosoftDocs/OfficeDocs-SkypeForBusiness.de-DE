---
title: 'Lync Server 2013: Konferenz Diagnosebericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c4489e13f794a924e1512a1e6ed7b32f73da8f1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525992"
---
# <a name="conference-diagnostic-report-in-lync-server-2013"></a>Konferenz Diagnosebericht in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

Der Konferenz Diagnosebericht enthält Informationen über den Erfolg und das Scheitern aller Konferenzsitzungen. Beachten Sie, dass Microsoft lync Server zwischen verschiedenen Arten von Fehlern unterscheidet:

  - **Erwarteter Fehler**. Ein erwarteter Fehler ist normalerweise nur im technischsten Sinn ein Fehler. Nehmen wir beispielsweise an, dass jemand eine Konferenz startet, aber auflegt, bevor jeder beitreten kann. Technisch gesehen ist das ein Fehler: die Konferenz wurde initiiert, aber nicht abgeschlossen. Dies ist jedoch ein Fehler, den Sie erwarten würden: Wenn der Organisator die Konferenz abbricht, bevor jemand beitreten kann, wird die Konferenz nicht abgeschlossen.

  - **Unerwarteter Fehler**: Ein unerwarteter Fehler ist genau das, was der Name aussagt: Ein Fehler, der gemessen an den Umständen nicht zu erwarten ist. Angenommen, Sie rufen eine Person an, und die Person kann den Anruf annehmen. Angenommen, eine Konferenz konnte nicht abgehalten werden, da die Besprechungsrichtlinie des Organisators nicht abgerufen werden konnte. Das ist ein unerwarteter Fehler: Schließlich sollten Sie immer in der Lage sein, die Besprechungsrichtlinie eines Benutzers abzurufen.

Beachten Sie, dass die Metriken für "Erfolg", "Erwarteter Fehler" und "Unerwarteter Fehler" nicht zwangsläufig identisch mit der Metrik unter "Sitzungen insgesamt" sind. Im Bericht werden beispielsweise die folgenden Werte angezeigt:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Erfolge</th>
<th>Erwartete Fehler</th>
<th>Unerwartete Fehler</th>
<th>Sitzungen insgesamt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2024</p></td>
<td><p>469</p></td>
<td><p>16 </p></td>
<td><p>2521</p></td>
</tr>
</tbody>
</table>


Wenn Sie 2024 + 469 + 16 hinzufügen, erhalten Sie insgesamt 2.509 Sitzungen, in der Spalte Gesamt Sitzungen werden jedoch insgesamt 2.521 Sitzungen angezeigt. Die "fehlenden" 12 Sitzungen für sind Sitzungen, die vom System nicht als erfolgreich oder nicht erfolgreich kategorisiert werden konnten. Dies ist manchmal der Fall, wenn ein Drittanbieterprodukt einen neuen Diagnosecode einführt, der Monitoring Server nicht vertraut ist. Wenn dies geschieht, können mit diesem Produkt erstellte Anrufe und das melden dieses Diagnosecodes nicht immer als ein Erfolg, ein erwarteter Fehler oder ein unerwarteter Fehler kategorisiert werden.

<div>

## <a name="accessing-the-conference-diagnostic-report"></a>Zugreifen auf den Konferenz Diagnosebericht

Der Zugriff auf den Konferenz Diagnosebericht erfolgt über die Startseite für Überwachungsberichte. Sie können auf den [Bericht über Fehlerverteilung in lync Server 2013](lync-server-2013-failure-distribution-report.md) zugreifen, indem Sie auf eine der folgenden Metriken klicken:

  - Anzahl der unerwarteten Fehler

  - Anzahl der erwarteten Fehler

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a>Optimale Nutzung des Konferenz Diagnoseberichts

Der Konferenz Diagnosebericht enthält eine Reihe von Diagrammen. Jede der im Diagramm gezeigten Spalten ist eigentlich ein Hyperlink. Wenn Sie auf eine Spalte klicken, führen Sie einen Drilldown zum [Fehler Verteilungs Bericht in lync Server 2013](lync-server-2013-failure-distribution-report.md) für diesen Zeitraum und diesen Konferenztyp aus.

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie mit dem Konferenz Diagnosebericht nach Dingen suchen, die den Typ der Konferenz (beispielsweise eine Fokus basierte Konferenz) oder den in der Konferenz verwendeten Edgeserver filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Konferenzen nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle sind die Filter aufgeführt, die Sie mit dem Konferenz Diagnosebericht verwenden können.

### <a name="conference-diagnostic-report-filters"></a>Filter für Konferenz Diagnoseberichte

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
<li><p>Monatlich (maximal 12 Monate werden angezeigt)</p></li>
</ul>
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall Täglich mit dem Startdatum 07.08.2012 und dem Enddatum 28.09.2012 ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Vollqualifizierter Domänenname (FQDN) des Registrierungsstellenpools oder Edgeservers. Sie können einen einzelnen Pool auswählen, oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Konferenzsitzungen</strong></p></td>
<td><p>Gibt den Typ der Konferenzsitzung an. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Alle</p></li>
<li><p>Konferenzzustandsobjekt-Sitzungen</p></li>
<li><p>Alle MCU-Sitzungen</p></li>
<li><p>Sofortnachrichtenkonferenzen</p></li>
<li><p>Anwendungsfreigabe</p></li>
<li><p>A/V-Konferenzen</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die Informationen aufgeführt, die im Diagnosebericht über die Konferenz für jeden Typ von Konferenzsitzung bereitgestellt werden.

### <a name="conference-diagnostic-report-metrics"></a>Metriken für den Konferenz Diagnosebericht

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
<td><p><strong>Anzahl der erfolgreichen Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der erfolgreichen Konferenzen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prozentsatz der erfolgreichen Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Prozentsatz der Konferenzen, die mit erheblichen Problemen abgeschlossen wurden. Errechnet sich durch Dividieren der Anzahl der erfolgreichen Sitzungen durch die Gesamtzahl der Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anzahl der erwarteten Fehler</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Konferenzen, bei denen ein &quot; Erwarteter Fehler &quot; aufgetreten ist.</p>
<p>Ein erwarteter Fehler ist ein Fehler, dessen Auftreten erwartet wird. Wenn beispielsweise ein Benutzer seinen Status auf Nicht stören festgelegt hat, ist zu erwarten, dass jeder Anruf an diesen Benutzer fehlschlägt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prozentsatz der erwarteten Fehler</strong></p></td>
<td><p>Nein</p></td>
<td><p>Prozentsatz der Konferenzen, bei denen ein erwarteter Fehler auftrat. Errechnet sich durch Dividieren der Anzahl der erwarteten Fehler durch die Gesamtzahl der Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anzahl der unerwarteten Fehler</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Konferenzen, bei denen ein &quot; unerwarteter Fehler &quot; aufgetreten ist.</p>
<p>Ein unerwarteter Fehler ist ein Fehler, der in einem System auftritt, das abgesehen davon anscheinend intakt ist. Beispielsweise sollte ein Anruf nicht beendet werden, wenn der Anrufer in der Warteschleife platziert ist. Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prozentsatz der unerwarteten Fehler</strong></p></td>
<td><p>Nein</p></td>
<td><p>Prozentsatz der Konferenzen, bei denen ein unerwarteter Fehler auftrat Errechnet sich durch Dividieren der Anzahl der unerwarteten Fehler durch die Gesamtzahl der Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der Konferenzen, einschließlich erfolgreicher Konferenzen, fehlgeschlagener Konferenzen (sowohl erwartete Fehler als auch unerwartete Fehler) und nicht kategorisierter Konferenzen.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

