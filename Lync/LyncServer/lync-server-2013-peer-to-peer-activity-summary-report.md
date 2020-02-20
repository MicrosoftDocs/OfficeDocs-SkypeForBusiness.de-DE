---
title: 'Lync Server 2013: zusammenfassender Bericht über Peer-to-Peer-Aktivitäten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03a3015f24bae2595ac845c351c32ccb5d36c5f7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a>Zusammenfassender Bericht über Peer-to-Peer-Aktivitäten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-21_

Der zusammenfassende Bericht über Peer-to-Peer-Aktivitäten bietet eine Gesamtübersicht über Peer-zu-Peer-Kommunikationssitzungen. Eine Peer-to-Peer-Sitzung umfasst normalerweise nur zwei Benutzer und erfordert nicht die Verwendung der lync Server Konferenzdienste. Im Vergleich dazu umfasst eine Konferenz normalerweise mehr als zwei Benutzer und erfordert die Verwendung von Microsoft lync Server 2013 Konferenzdiensten. Die Konferenz Aktivität wird im zusammenfassenden Konferenzbericht aufgeführt.

Der zusammenfassende Bericht über Peer-to-Peer-Aktivität hilft Ihnen bei der Beantwortung von Fragen wie den folgenden:

  - Wie viele Peer-to-Peer-Chatnachrichten senden meine Benutzer an einem typischen Tag?

  - Nutzen meine Benutzer tatsächlich die lync Server Anwendungsfreigabe und Dateiübertragungsfunktionen?

  - Benutzer haben sich beklagt, dass das Netzwerk zu bestimmten Tageszeiten langsam erscheint. Wie viele Minuten sind Peer-to-Peer-Audio-und-Videositzungen während dieser Zeiträume gewidmet?

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>Zugriff auf den zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten

Sie greifen auf den Bericht über Peer-to-Peer-Aktivitätszusammenfassung auf der Startseite für Überwachungsberichte zu. Sie öffnen den [Bericht über Peer-zu-Peer-Chatnachrichten in lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) , indem Sie auf eine der folgenden Metriken klicken:

  - Gesamtanzahl der Peer-zu-Peer-Sofortnachrichtensitzungen

  - Gesamtanzahl der Peer-zu-Peer-Sofortnachrichten

Ebenso können Sie den Bericht über Peer-zu-Peer-sprach-und-Video Funktionen öffnen, indem Sie auf eine der folgenden Metriken klicken:

  - Peer-zu-Peer-Audiositzungen insgesamt

  - Gesamtdauer der Peer-to-Peer-Audiositzung in Minuten

  - Peer-zu-Peer-Audiositzungen insgesamt

  - Gesamtdauer der Peer-to-Peer-Audiositzung in Minuten

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Optimale Nutzung des Zusammenfassungsberichts über Peer-to-Peer-Aktivitäten

Am unteren Rand des Zusammenfassungsberichts über Peer-to-Peer-Aktivität finden Sie Gesamtwerte für Metriken wie Peer-to-Peer-Sofortnachrichtensitzungen und Peer-to-Peer-Chatnachrichten insgesamt. Dadurch wird eine kurze Zusammenfassung der detaillierten Informationen im Textkörper des Berichts bereitgestellt.

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im zusammenfassenden Bericht über Peer-to-Peer-Aktivität auswählen, wie Daten gruppiert werden sollen. In diesem Fall wird die Aktivität nach Stunde, Tag, Woche oder Monat gruppiert.

In der folgenden Tabelle sind die Filter aufgeführt, die Sie im zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten verwenden können.

### <a name="peer-to-peer-activity-summary-report-filters"></a>Berichtfilter für Peer-to-Peer-Aktivitätszusammenfassung

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
<p>17.7.2012 13:00 Uhr</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/17/12012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/13/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ziel</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>17.7.2012 13:00 Uhr</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/17/12012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/13/2012</p>
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
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Wenn Sie beispielsweise das tägliche Intervall mit dem Startdatum 7/17/12012 und dem Enddatum 2/28/2012 auswählen, werden die Daten für die Tage 8/7/12012 12:00 Uhr bis 9/7/12012 12:00 Uhr angezeigt (also insgesamt 31 Tage).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die Informationen aufgeführt, die im zusammenfassenden Bericht über Peer-to-Peer-Aktivität angegeben werden.

### <a name="peer-to-peer-activity-summary-report-metrics"></a>Metriken für den zusammenfassenden Bericht über Peer-to-Peer-Aktivitäten

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
<td><p><strong>Stündlich</strong></p>
<p><strong>Täglich</strong></p>
<p><strong>Wöchentlich</strong></p>
<p><strong>Monatlich</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gibt das Zeitintervall an, das Sie auf der Symbolleiste für Filter ausgewählt haben. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das tägliche Intervall verwenden und auf 7/17/12012 klicken, wird eine stündliche Aufschlüsselung der Benutzer Registrierungs Aktivität für dieses Datum angezeigt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Peer-zu-Peer-Sitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der durchgeführten Peer-zu-Peer-Sitzungen, unabhängig vom Sitzungstyp.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gesamtanzahl der Peer-zu-Peer-Sofortnachrichtensitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Peer-zu-Peer-Chatsitzungen (Instant Messaging). Wenn Sie auf dieses Element klicken, zeigt der Bericht den Peer-to-Peer-Chat Bericht für den ausgewählten Zeitraum an.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gesamtanzahl der Peer-zu-Peer-Sofortnachrichten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der in Peer-zu-Peer-Sitzungen gesendeten Sofortnachrichten. Wenn Sie auf dieses Element klicken, zeigt der Bericht den Peer-to-Peer-Chat Bericht für den ausgewählten Zeitraum an.</p></td>
</tr>
<tr class="odd">
<td><p><strong><c0>Peer-zu-Peer-Audiositzungen insgesamt</c0></strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Peer-zu-Peer-Audioanrufe. Wenn Sie auf dieses Feld klicken, zeigt der Bericht den Bericht über Peer-zu-Peer-sprach-und-Video Daten für den ausgewählten Zeitraum an.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gesamtdauer der Peer-to-Peer-Audiositzung in Minuten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzeit Aufwand für Peer-to-Peer-audiositzungen. Wenn Sie auf dieses Element klicken, zeigt der Bericht den Bericht über Peer-zu-Peer-sprach-und-Video Informationen für den ausgewählten Zeitraum an.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Durchschnittliche Peer-to-Peer-Audiositzung Minuten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Durchschnittliche Zeitaufwand für Peer-to-Peer-audiositzungen. Wird berechnet, indem die Gesamtdauer der Audiositzung durch die Gesamtzahl der audiositzungen dividiert wird.</p></td>
</tr>
<tr class="even">
<td><p><strong><c0>Peer-zu-Peer-Videositzungen insgesamt</c0></strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Peer-zu-Peer-Videoanrufe. Beachten Sie, dass Videositzungen auch als audiositzungen gezählt werden: jede Videositzung wird als eine Video-und eine Audiositzung gezählt. Wenn Sie auf dieses Element klicken, zeigt der Bericht den Bericht über Peer-zu-Peer-sprach-und-Video Informationen für den ausgewählten Zeitraum an.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gesamtdauer der Peer-to-Peer-Videositzung in Minuten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzeit Aufwand für Peer-zu-Peer-Videositzungen. Wenn Sie auf dieses Element klicken, zeigt der Bericht den Bericht über Peer-zu-Peer-sprach-und-Video Informationen für den ausgewählten Zeitraum an.</p></td>
</tr>
<tr class="even">
<td><p><strong>Durchschnittliche Peer-to-Peer-Video Sitzungs Minuten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Durchschnittliche Zeitaufwand für Peer-zu-Peer-Videositzungen. Wird berechnet, indem die gesamte Video Sitzungszeit durch die Gesamtzahl der Videositzungen dividiert wird.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Peer-zu-Peer-Dateiübertragungssitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Peer-zu-Peer-Sitzungen, die Dateiübertragungen umfassten.</p></td>
</tr>
<tr class="even">
<td><p><strong>Peer-zu-Peer-Anwendungsfreigabesitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Peer-zu-Peer-Sitzungen, die die Anwendungsfreigabe umfassten.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

