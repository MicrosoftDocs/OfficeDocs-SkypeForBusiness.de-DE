---
title: 'Lync Server 2013: Anruf Diagnose Zusammenfassungsbericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e747d257e7c88973790e8fd0c9ba828949248598
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a>Anruf Diagnose Zusammenfassungsbericht in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-06_

Der zusammenfassende Anrufdiagnosebericht bietet eine Gesamtübersicht zu fehlgeschlagenen Peer-to-Peer- und Konferenzsitzungen. Der Bericht zeigt die Gesamtfehlerrate für beide Sitzungstypen und detaillierte Fehlerinformationen nach Sitzungsmodalitätstyp:

  - Sofortnachrichten

  - Anwendungsfreigabe

  - Dateiübertragung

  - Audio

  - Video

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a>Zugriff auf den zusammenfassenden Anrufdiagnosebericht

Der Zugriff auf den zusammenfassenden Anrufdiagnosebericht erfolgt auf der Startseite für Überwachungsberichte. Im Bericht Anruf Diagnose Zusammenfassung können Sie auf den Bericht [Peer-to-Peer-Aktivitäts Diagnose in lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) zugreifen, indem Sie im Abschnitt Peer-to-Peer-Sitzungszusammenfassung im Bericht auf die Fehlerrate-Metrik klicken. Sie können auch auf den [Konferenz Diagnosebericht in lync Server 2013](lync-server-2013-conference-diagnostic-report.md) zugreifen, indem Sie auf eine der folgenden Konferenz Metriken klicken:

  - Sitzungsfehlerrate insgesamt

  - Fehlerrate für Konferenzzustandsobjekt

  - MCU-Fehlerrate

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>Optimale Verwendung des zusammenfassenden Anrufdiagnoseberichts

Der Bericht zur Anruf Diagnose Zusammenfassung enthält Diagramme, die Fehlerraten für die verschiedenen in Microsoft lync Server 2013 verwendeten Methoden vergleichen. Die Spalten in diesen Diagrammen sind tatsächlich Hotlinks; Wenn Sie beispielsweise auf die Spalte "Instant Messaging" für Peer-to-Peer-Sitzungen klicken, führen Sie einen Drilldown zu einer Instanz des [Diagnoseberichts zur Peer-to-Peer-Aktivität in lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)durch, in der zusätzliche Informationen zu allen Sofortnachrichten bereitgestellt werden. im Zusammenfassungsbericht zur Anruf Diagnose enthaltene Nachrichten Sitzungen.

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
<td><p>Vollqualifizierter Domänenname (FQDN) des Registrar-Pools oder Edgeservers. Sie können einen einzelnen Pool auswählen oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Metriken für Peer-to-Peer-Sitzungen

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Anrufdiagnosebericht für Peer-to-Peer-Sitzungen (d. h. für Sitzungen mit nur zwei Teilnehmern) angegeben werden.

### <a name="metrics-for-peer-to-peer-sessions"></a>Metriken für Peer-to-Peer-Sitzungen

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
<td><p>Die Gesamtzahl der Peer-to-Peer-Sitzungen, die stattgefunden haben.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fehlerrate</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Peer-to-Peer-Sitzungen, bei denen ein Fehler aufgetreten ist. Wenn Sie auf dieses Element klicken, wird der Diagnosebericht über Peer-to-Peer-Aktivitäten angezeigt, der detailliertere Angaben zu den fehlgeschlagenen Peer-to-Peer-Sitzungen enthält.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>Metriken für Konferenzsitzungen

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Anrufdiagnosebericht für Konferenzsitzungen (d. h. für Sitzungen mit mindestens drei Teilnehmern) angegeben werden.

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

