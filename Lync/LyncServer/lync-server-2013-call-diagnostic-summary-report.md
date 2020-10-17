---
title: 'Lync Server 2013: zusammenfassender Anruf Diagnosebericht'
description: 'Lync Server 2013: zusammenfassender Anruf Diagnosebericht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b444a176c06974a9eb9827006e078c17b54047a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561701"
---
# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a>Zusammenfassender Anruf Diagnosebericht in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-06_

Der zusammenfassende Anrufdiagnosebericht bietet eine Gesamtübersicht zu fehlgeschlagenen Peer-zu-Peer- und Konferenzsitzungen. Der Bericht zeigt die Gesamtfehlerrate für beide Sitzungstypen und detaillierte Fehlerinformationen nach Sitzungsmodalitätstyp:

  - Sofortnachrichten

  - Anwendungsfreigabe

  - Dateiübertragung

  - Audio

  - Video

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a>Zugriff auf den zusammenfassenden Anrufdiagnosebericht

Der Zugriff auf den zusammenfassenden Anrufdiagnosebericht erfolgt auf der Startseite für Überwachungsberichte. Im zusammenfassenden Bericht "Anruf Diagnose" können Sie auf den [Diagnosebericht über Peer-to-Peer-Aktivitäten in lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) zugreifen, indem Sie im Abschnitt Peer-to-Peer-Sitzungszusammenfassung des Berichts auf die Metrik für Fehlerrate klicken. Sie können auch auf den [Konferenz Diagnosebericht in lync Server 2013](lync-server-2013-conference-diagnostic-report.md) zugreifen, indem Sie auf eine der folgenden Konferenz Metriken klicken:

  - Sitzungsfehlerrate insgesamt

  - Fehlerrate für Konferenzzustandsobjekt

  - MCU-Fehlerrate

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>Optimale Verwendung des zusammenfassenden Anrufdiagnoseberichts

Der zusammenfassende Anruf Diagnosebericht enthält Diagramme, die Fehlerraten für die verschiedenen in Microsoft lync Server 2013 verwendeten Modalitäten vergleichen. Die Spalten in diesen Diagrammen sind tatsächlich Hotlinks; Wenn Sie beispielsweise auf die Instant Messaging-Spalte für Peer-to-Peer-Sitzungen klicken, wird ein Drilldown zu einer Instanz des [Diagnoseberichts über Peer-to-Peer-Aktivitäten in lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)durchführt, ein Bericht mit zusätzlichen Details zu allen Chatnachrichten, die im zusammenfassenden Anruf Diagnosebericht enthalten sind.

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Zusammenfassenden Anrufdiagnosebericht nach Kriterien wie dem Registrierungspool oder den in der Sitzung verwendeten Edgeserver filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Anrufdiagnosebericht verwenden können.

### <a name="call-diagnostic-summary-report-filters"></a>Filter im Zusammenfassenden Anrufdiagnosebericht

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
<td><p>Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder des Edgeservers. Sie können entweder einen einzelnen Pool auswählen oder auf <strong>[Alle]</strong> klicken, um Daten für alle Pools anzuzeigen. Diese Dropdownliste wird automatisch anhand der Datensätze in der Datenbank aufgefüllt.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Metriken für Peer-zu-Peer-Sitzungen

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Anrufdiagnosebericht für Peer-zu-Peer-Sitzungen (d. h. für Sitzungen mit nur zwei Teilnehmern) angegeben werden.

### <a name="metrics-for-peer-to-peer-sessions"></a>Metriken für Peer-zu-Peer-Sitzungen

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
<td><p><strong>Sitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Peer-zu-Peer-Sitzungen, die stattgefunden haben.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fehlerrate</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein Fehler aufgetreten ist. Wenn Sie auf dieses Element klicken, wird der Diagnosebericht über Peer-zu-Peer-Aktivitäten angezeigt, der detailliertere Angaben zu den fehlgeschlagenen Peer-zu-Peer-Sitzungen enthält.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>Metriken für Konferenzsitzungen

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Anrufdiagnosebericht für Konferenzsitzungen (d. h. für Sitzungen mit mindestens drei Teilnehmern) angegeben werden.

### <a name="metrics-for-conferencing-sessions"></a>Metriken für Konferenzsitzungen

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
<td><p><strong>Konferenzen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Konferenzen, die stattgefunden haben.</p></td>
</tr>
<tr class="even">
<td><p><strong>Konferenzsitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Konferenzsitzungen, die durchgeführt wurden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungsfehlerrate insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Konferenzsitzungen, bei denen ein Fehler aufgetreten ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>Konferenzzustandsobjekt-Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Anzahl der auf Konferenzzustandsobjekten basierenden Sitzungen, bei denen Fehler aufgetreten sind.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fehlerrate für Konferenzzustandsobjekt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der auf Konferenzzustandsobjekten basierenden Konferenzsitzungen, bei denen ein Fehler aufgetreten ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>MCU-Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der auf Konferenzservern basierenden Konferenzen (früher als MCU-Konferenzen bezeichnet [Multipoint Control Unit]), bei denen ein Fehler aufgetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MCU-Fehlerrate</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der auf Konferenzservern basierenden Konferenzen (früher als MCU-Konferenzen bezeichnet [Multipoint Control Unit]), bei denen ein Fehler aufgetreten ist.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

