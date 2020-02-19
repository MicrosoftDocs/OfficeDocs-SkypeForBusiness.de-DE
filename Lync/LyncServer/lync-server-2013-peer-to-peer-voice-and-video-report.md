---
title: 'Lync Server 2013: Bericht über Peer-zu-Peer-sprach-und-Video Funktion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 880104d0809b0135c74c72a80eefb7d4bb0ed709
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a>Bericht über Peer-zu-Peer-sprach-und-Video Funktion in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-21_

Der Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität bietet eine detaillierte Aufstellung der Sprach- und -Videoanrufe für einen bestimmten Zeitraum (z. B. Anrufe pro Stunde oder Anrufe pro Tag). Darüber hinaus können Sie mit diesem Bericht alle getätigten Sprach- und Videoanrufe oder aber nur die erfolgreichen bzw. fehlgeschlagenen Anrufe anzeigen. In diesem Bericht werden die Anrufinformationen in den folgenden Kategorien angezeigt:

  - Anrufe pro Pool

  - Aufrufe pro Anruftyp (beispielsweise ein lync-zu-lync-Anruf im Vergleich zu einem lync-Anruf an eine Person im PSTN-Netzwerk)

  - Anrufe pro Zugriffstyp (beim internen Netzwerk angemeldete Benutzer bzw. beim externen Netzwerk angemeldete Benutzer)

  - Anrufe pro Vermittlungsserver

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>So greifen Sie auf den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität zu

Auf den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität können Sie nur zugreifen, indem Sie den zusammenfassenden Bericht über Peer-zu-Peer-Aktivität öffnen und dann auf die folgenden Metriken klicken:

  - Peer-zu-Peer-Audiositzungen insgesamt

  - Gesamtdauer der Peer-zu-Peer-Audiositzung in Minuten

  - Peer-zu-Peer-Videositzungen insgesamt

  - Gesamtdauer der Peer-zu-Peer-Videositzung in Minuten

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>So nutzen Sie den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität optimal

Es gibt eine Reihe von Möglichkeiten, um den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität zu filtern. Diese Filteroptionen sind jedoch standardmäßig ausgeblendet. Zum Anzeigen der verfügbaren Filteroptionen klicken Sie auf die Schaltfläche **Parameter ein-/ausblenden** in der oberen rechten Ecke des Berichtfensters.

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität verwenden können.

### <a name="peer-to-peer-voice-and-video-report-filters"></a>Filter im Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität

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
<p>07.07.2012 13:00:00 Uhr</p>
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
<td><p><strong>Medientyp</strong></p></td>
<td><p>Gibt den Typ der in der Sitzung verwendeten Medien an. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>In beide Richtungen</p></li>
<li><p>Audio</p></li>
<li><p>Video</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Anrufanordnung</strong></p></td>
<td><p>Gibt an, ob die Sitzung erfolgreich oder fehlerhaft war. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Alle</p></li>
<li><p>Erfolgreiche Anrufe</p></li>
<li><p>Fehlerhafte Anrufe</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Bericht nach:</strong></p></td>
<td><p>Gibt die Werte an, die in dem Bericht verwendet werden sollen. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Sitzungsanzahl</p></li>
<li><p>Anrufminuten</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Metriken für den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität nach Pool

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität für jeden Pool angegeben werden.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Metriken für den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität nach Pool

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
<td><p><strong>Pool</strong></p></td>
<td><p>Nein</p></td>
<td><p>Name des registrierungspools oder Edgeserver, der für den Anruf verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>Datum/Uhrzeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf stattfand.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Metriken für den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität nach Anruftyp

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität für jeden Anruftyp angegeben werden.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Metriken für den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität nach Anruftyp

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
<td><p><strong>Anruftyp</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gibt den Typ des Anrufs an, der ausgeführt wurde. Folgende Werte sind möglich:</p>
<ul>
<li><p>UC-zu-UC</p></li>
<li><p>UC-zu-PSTN</p></li>
<li><p>PSTN-zu-UC</p></li>
<li><p>PSTN-zu-PSTN</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Datum/Uhrzeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf stattfand.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Metriken für den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität nach Zugriffstyp

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität für jeden Netzwerkzugriffstyp angegeben werden.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Metriken für den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität nach Zugriffstyp

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
<td><p><strong>Zugriffstyp</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gibt an, ob die Clients am internen oder am externen Netzwerk angemeldet wurden, als der Anruf getätigt wurde. Diese Metrik hat normalerweise einen der folgenden Werte:</p>
<ul>
<li><p>Intern</p></li>
<li><p>Extern</p></li>
<li><p>Gemischt</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Datum/Uhrzeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf stattfand.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Metriken für den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität nach Vermittlungsserver

In der folgenden Tabelle sind die Informationen aufgeführt, die im Bericht über Peer-zu-Peer-sprach-und-Video Daten für jede Vermittlungsserver angegeben werden.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Metriken für den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität nach Vermittlungsserver

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
<td><p><strong>Vermittlungsserver</strong></p></td>
<td><p>Nein</p></td>
<td><p>Name des Vermittlungsserver.</p></td>
</tr>
<tr class="even">
<td><p><strong>Datum/Uhrzeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf stattfand.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

