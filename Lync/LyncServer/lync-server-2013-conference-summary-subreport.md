---
title: 'Lync Server 2013: Konferenz Zusammenfassungs Unterbericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2537cbe959639baee6f0f986b3faea1ebd79b5a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a>Konferenz Zusammenfassung Unterbericht in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-06_

Der zusammenfassende Konferenzunterbericht stellt eine Gesamtübersicht zu gescheiterten Konferenzsitzungen bereit, bei denen Fehler aufgetreten sind. Diese gescheiterten Sitzungen sind weiter nach Sitzungstyp unterteilt: Konferenzzustandsobjekt-Sitzungen und MCU-Sitzungen.

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im zusammenfassenden Konferenzunterbericht verwenden können.

### <a name="conference-summary-subreport-filters"></a>Filter im zusammenfassenden Konferenzunterbericht

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
<td><p><strong>Pool</strong></p></td>
<td><p>Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder Edgeservers. Sie können einen einzelnen Pool auswählen oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die Metriken aufgelistet, die im zusammenfassenden Konferenzunterbericht angegeben werden.

### <a name="conference-summary-subreport-metrics"></a>Metriken im zusammenfassenden Konferenzunterbericht

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
<td><p>Gesamtzahl der Konferenzen, die durchgeführt wurden.</p></td>
</tr>
<tr class="even">
<td><p><strong>Konferenzsitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der Konferenzsitzungen. Eine einzelne Konferenz kann mehrere Sitzungen haben. Beispielsweise kann eine Konferenz sowohl eine Konferenzzustandsobjekt-Sitzung als auch eine MCU-Sitzung umfassen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungsfehlerrate insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Prozentsatz aller gescheiterten Konferenzen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Konferenzzustandsobjekt-Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der Konferenzzustandsobjekt-Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fehlerrate für Konferenzzustandsobjekt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Prozentsatz der gescheiterten Konferenzzustandsobjekt-Sitzungen.</p></td>
</tr>
<tr class="even">
<td><p>MCU-Sitzungen</p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der MCU-Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MCU-Fehlerrate</strong></p></td>
<td><p>Nein</p></td>
<td><p>Prozentsatz der gescheiterten MCU-Sitzungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>MCU-Sitzungen nach Modalität</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der MCU-Sitzungen, gruppiert nach Modalität (z. B. Chatkonferenz).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fehlerrate nach Modalität</strong></p></td>
<td><p>Nein</p></td>
<td><p>Prozentsatz der gescheiterten MCU-Sitzungen, gruppiert nach Modalität (z. B. Chatkonferenz).</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

