---
title: 'Lync Server 2013: Bericht zur Konferenz Aktivität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c098bc3a1c8b937b72707c76a3943866ad7b9fbb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a>Bericht zur Konferenz Aktivität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Mit dem Konferenzaktivitätsbericht können Fragen wie diese leicht beantwortet werden: Wie viele Konferenzen werden täglich gehalten und wann werden diese Konferenzen gehalten? Derartige Informationen sind an sich nützlich und können außerdem für die Problembehandlung verwendet werden. Nehmen wir z. B. an, dass sich Benutzer darüber beschweren, dass das Netzwerk mittags besonders langsam zu sein scheint. Ein kurzer Blick auf die Berichte der Konferenz Aktivitäten deutet möglicherweise auf einen möglichen Grund hin: Es werden weit mehr Konferenzen zwischen den Stunden 10:00 und 2:00 Uhr und dann zu einem anderen Zeitpunkt geplant.

Verursacht das langsame Netzwerk Probleme, können Sie Benutzern empfehlen, Konferenzen zu Tageszeiten mit weniger Datenauslastung abzuhalten.

<div>

## <a name="accessing-the-conference-activity-report"></a>Zugreifen auf den Konferenzaktivitätsbericht

Der Zugriff auf den Bericht zur Konferenz Aktivität erfolgt über den [Konferenz Zusammenfassungsbericht in lync Server 2013](lync-server-2013-conference-summary-report.md) , indem Sie auf eine der folgenden Metriken klicken:

  - Konferenzen insgesamt

  - Teilnehmer insgesamt

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a>Optimales Verwenden des Konferenzaktivitätsberichts

Standardmäßig wird im Konferenzaktivitätsbericht die Gesamtanzahl der Konferenzen für den angegebenen Zeitraum (z. B. die Gesamtanzahl der Konferenzen pro Tag oder die Gesamtanzahl der Konferenzen pro Stunde eines Tages). Sie können jedoch auch die Gesamtanzahl der Teilnehmer für den Zeitraum oder die Gesamtanzahl der Teilnehmerminuten anzeigen. Klicken Sie dazu auf die Schaltfläche zum Ein- und Ausblenden der Parameter, um die Filteroptionen anzuzeigen und wählen Sie dann eine der folgenden Optionen aus der Dropdownliste „Bericht nach“ aus:

  - Teilnehmeranzahl

  - Teilnehmerminuten

  - Konferenzanzahl

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Konferenzaktivitätsbericht verwenden können.

### <a name="conference-activity-report-filters"></a>Filter im Konferenzaktivitätsbericht

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
<td><p><strong>Bericht nach</strong></p></td>
<td><p>Gibt die Werte an, die in dem Bericht verwendet werden sollen. Sie können einen der folgenden Werte auswählen:</p>
<ul>
<li><p>Teilnehmeranzahl</p></li>
<li><p>Teilnehmerminuten</p></li>
<li><p>Konferenzanzahl</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a>Metriken für Konferenzen nach Pool

In der folgenden Tabelle werden die Metriken aufgelistet, die im Konferenzaktivitätsbericht für jeden Pool angegeben werden.

### <a name="metrics-for-conferences-by-pool"></a>Metriken für Konferenzen nach Pool

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
<td><p>Name des in der Konferenz verwendeten Registrierungspools oder Edgeservers.</p></td>
</tr>
<tr class="even">
<td><p><strong>Datum/Uhrzeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Zeitpunkt (Datum und Uhrzeit), zu dem die Konferenz stattfand.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der Teilnehmer, der Teilnehmerminuten oder der Konferenzen.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a>Metriken für Konferenzen nach Servertyp

In der folgenden Tabelle werden die Metriken aufgelistet, die im Konferenzaktivitätsbericht für jeden Servertyp angegeben werden.

### <a name="metrics-for-conferences-by-server-type"></a>Metriken für Konferenzen nach Servertyp

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
<td><p><strong>Konferenzservertyp</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Typ des Servers, der in der Konferenz verwendet wird, in der Regel einer der folgenden:</p>
<ul>
<li><p>Webkonferenzserver</p></li>
<li><p>Sofortnachrichten-Konferenzserver</p></li>
<li><p>Telefonkonferenzserver</p></li>
<li><p>A/V-Konferenzserver</p></li>
<li><p>Anwendungsfreigabe</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Datum/Uhrzeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Zeitpunkt (Datum und Uhrzeit), zu dem die Konferenz stattfand.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der Teilnehmer, der Teilnehmerminuten oder der Konferenzen.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

