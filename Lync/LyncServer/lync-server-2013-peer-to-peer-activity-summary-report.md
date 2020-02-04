---
title: 'Lync Server 2013: Zusammenfassungsbericht für Peer-zu-Peer-Aktivitäten'
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
ms.openlocfilehash: d55c3d84fe48158490473c31e9782dc63e298310
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a>Zusammenfassungsbericht zur Peer-zu-Peer-Aktivität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-21_

Der zusammenfassende Bericht über Peer-to-Peer-Aktivität bietet eine Übersicht über Peer-to-Peer-Kommunikationssitzungen. Eine Peer-to-Peer-Sitzung umfasst in der Regel nur zwei Benutzer und erfordert keine Verwendung der lync Server-Konferenzdienste. Im Vergleich dazu umfasst eine Konferenz in der Regel mehr als zwei Benutzer und erfordert die Verwendung von Microsoft lync Server 2013-Konferenzdiensten. Konferenzaktivität wird im zusammenfassenden Konferenzbericht gemeldet.

Der zusammenfassende Bericht über Peer-to-Peer-Aktivität hilft Ihnen bei der Beantwortung der folgenden Fragen:

  - Wie viele Peer-to-Peer-Chatnachrichten senden meine Benutzer an einem normalen Tag?

  - Nutzen alle meine Benutzer tatsächlich die Vorteile der lync Server-Anwendungsfreigabe und der Dateiübertragungsfunktionen?

  - Die Benutzer haben sich darüber beklagt, dass das Netzwerk zu bestimmten Tageszeiten langsam ist. Wie viele Minuten werden in diesen Zeiten für Peer-to-Peer-Audio-/Videositzungen aufgewendet?

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>Zugriff auf den zusammenfassenden Bericht über Peer-to-Peer-Aktivität

Auf den zusammenfassenden Bericht über Peer-to-Peer-Aktivität greifen Sie über die Startseite für Überwachungsberichte zu. Sie öffnen den [Peer-zu-Peer-Chat Bericht in lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) , indem Sie auf eine der folgenden Metriken klicken:

  - Peer-to-Peer-Chatsitzungen insgesamt

  - Peer-to-Peer-Chatnachrichten insgesamt

Entsprechend können Sie den Bericht über Peer-to-Peer-Sprach- und -Videoaktivität öffnen, indem Sie auf eine der folgenden Metriken klicken:

  - Peer-to-Peer-Audiositzungen insgesamt

  - Gesamtdauer der Peer-to-Peer-Audiositzung in Minuten

  - Peer-to-Peer-Audiositzungen insgesamt

  - Gesamtdauer der Peer-to-Peer-Audiositzung in Minuten

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Optimale Nutzung des zusammenfassenden Berichts über Peer-to-Peer-Aktivität

Im unteren Bereich des zusammenfassenden Berichts über Peer-to-Peer-Aktivität finden Sie Gesamtwerte für Metriken wie z. B. „Peer-to-Peer-Chatsitzungen insgesamt“ und „Peer-to-Peer-Chatnachrichten insgesamt“. Dies ermöglicht einen schnellen Überblick über die detaillierten Informationen im eigentlichen Bericht.

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Mit dem zusammenfassenden Bericht über Peer-to-Peer-Aktivität können Sie beispielsweise wählen, wie Daten gruppiert werden sollen. In diesem Fall werden die Aktivitäten nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im zusammenfassenden Bericht über Peer-to-Peer-Aktivität verwenden können.

### <a name="peer-to-peer-activity-summary-report-filters"></a>Filter im zusammenfassenden Bericht über Peer-to-Peer-Aktivität

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
<p>7/17/12012 1:00 Uhr</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/17/12012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/13/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bis</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>7/17/12012 1:00 Uhr</p>
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
<li><p>Stündlich (maximal 25 Stunden können angezeigt werden)</p></li>
<li><p>Täglich (maximal 31 Tage können angezeigt werden)</p></li>
<li><p>Wöchentlich (maximal 12 Wochen können angezeigt werden)</p></li>
<li><p>Monatlich (maximal 12 Monate können angezeigt werden)</p></li>
</ul>
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Wenn Sie beispielsweise das Tagesintervall mit einem Anfangstermin von 7/17/12012 und einem Enddatum von 2/28/2012 auswählen, werden die Daten für die Tage 8/7/12012 12:00 Uhr bis 9/7/12012 12:00 Uhr angezeigt (also insgesamt 31 Tage).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden Metriken aufgelistet, die im zusammenfassenden Bericht über Peer-to-Peer-Aktivität angegeben werden.

### <a name="peer-to-peer-activity-summary-report-metrics"></a>Metriken im zusammenfassenden Bericht über Peer-to-Peer-Aktivität

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
<td><p>Gibt das auf der Filtersymbolleiste gewählte Zeitintervall an. Sie können gegebenenfalls auf ein bestimmtes Zeitintervall klicken, um ausführliche Informationen zu diesem Intervall anzuzeigen. Wenn Sie beispielsweise das Tagesintervall verwenden und auf 7/17/12012 klicken, wird eine stündliche Aufschlüsselung der Benutzer Registrierungs Aktivität für dieses Datum angezeigt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Peer-to-Peer-Sitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der abgehaltenen Peer-to-Peer-Sitzungen, unabhängig vom Sitzungstyp.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Peer-to-Peer-Chatsitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der Peer-to-Peer-Chatnachrichtensitzungen. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Chatnachrichten für den gewählten Zeitraum angezeigt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Peer-to-Peer-Chatnachrichten insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der in Peer-to-Peer-Sitzungen gesendeten Chatnachrichten. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Chatnachrichten für den gewählten Zeitraum angezeigt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Peer-to-Peer-Audiositzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der Peer-to-Peer-Audioanrufe. Wenn Sie auf dieses Feld klicken, wird der Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für den gewählten Zeitraum angezeigt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gesamtdauer der Peer-to-Peer-Audiositzung in Minuten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtdauer der Peer-to-Peer-Audiositzungen. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für den gewählten Zeitraum angezeigt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Durchschnittliche Dauer der Peer-to-Peer-Audiositzung in Minuten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Durchschnittliche Dauer einer Peer-to-Peer-Audiositzung. Wird errechnet, indem die Gesamtdauer der Audiositzungen durch die Gesamtanzahl der Audiositzungen geteilt wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>Peer-to-Peer-Videositzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der Peer-to-Peer-Videoanrufe. Beachten Sie, dass Videositzungen auch als Audiositzungen zählen; jede Videositzung zählt als eine Videositzung und eine Audiositzung. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für den gewählten Zeitraum angezeigt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gesamtdauer der Peer-to-Peer-Videositzung in Minuten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtdauer der Peer-to-Peer-Videositzungen. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-to-Peer-Sprach- und -Videoaktivität für den gewählten Zeitraum angezeigt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Durchschnittliche Dauer der Peer-to-Peer-Videositzung in Minuten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Durchschnittliche Dauer einer Peer-to-Peer-Videositzung. Wird errechnet, indem die Gesamtdauer der Videositzungen durch die Gesamtanzahl der Videositzungen geteilt wird.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Peer-to-Peer-Dateiübertragungssitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der Peer-to-Peer-Sitzungen mit Dateiübertragungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Peer-to-Peer-Anwendungsfreigabesitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der Peer-to-Peer-Sitzungen mit Anwendungsfreigabe.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

