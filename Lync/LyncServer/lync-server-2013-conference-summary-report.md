---
title: 'Lync Server 2013: Zusammenfassender Konferenzbericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3ad7208095473529204fd69db631718d8bd774e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a>Zusammenfassender Konferenzbericht in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-09-03_

Der "Zusammenfassende Konferenzbericht" gibt Ihnen einen Überblick über Ihre Onlinekonferenzsitzungen. Eine Konferenz umfasst normalerweise mehr als 2 Benutzer und erfordert die Verwendung von Microsoft lync Server 2013 Konferenzdiensten. Im Vergleich dazu sind an einer Peer-zu-Peer-Sitzung nur 2 Benutzer beteiligt, ohne dass die Konferenzdienste von Lync Server benötigt werden. Peer-zu-Peer-Aktivitäten werden im [zusammenfassenden Bericht über Peer-zu-Peer-Aktivitäten in lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md)angezeigt.

Im zusammenfassenden Konferenzbericht erfahren Sie nicht nur, wie viele Konferenzen in einem bestimmten Zeitraum abgehalten wurden (stündlich, täglich, wöchentlich, monatlich), sondern auch die Gesamtzahl der Personen, die an diesen Konferenzen teilgenommen haben, und die Gesamtzahl der einmaligen Konferenz. Organisatoren.

Ein "eindeutiger” Organisator kann jeder sein, der mindestens eine Konferenz plant. Wenn zum Beispiel Pilar Ackerman eine Konferenz plant, zählt sie als ein eindeutiger Organisator. Wenn Ken Myer 148 Konferenzen plant, zählt auch er als ein eindeutiger Organisator. So sind in der Tabelle unten 8 geplante Konferenzen aufgeführt, jedoch nur 3 eindeutige Organisatoren (Ken Myer, Pilar Ackerman und David Ahs).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Konferenzorganisator</th>
<th>Konferenzdatum</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>07.07.2012 10:00 Uhr</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>07.07.2012 10:00 Uhr</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>07.07.2012 11:00:00 Uhr</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>07.07.2012 11:00:00 Uhr</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>07.07.2012 13:00</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>07.07.2012 14:00:00 Uhr</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>02.07.2012 10:00 Uhr</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>02.07.2012 10:00 Uhr</p></td>
</tr>
</tbody>
</table>


Der "Zusammenfassende Konferenzbericht" zeigt auch an, bei wie vielen Konferenzen Audio- und/oder Videofunktionen genutzt wurden.

<div>

## <a name="accessing-the-conference-summary-report"></a>Zugriff auf den "Zusammenfassenden Konferenzbericht"

Auf den "Zusammenfassenden Konferenzbericht" können Sie über die Startseite "Monitoring-Berichte" zugreifen. Sie können weiter zum Konferenzaktivitätsbericht aufschlüsseln, indem Sie auf eine der folgenden Metriken klicken:

  - Konferenzen insgesamt

  - Teilnehmer insgesamt

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a>Optimale Nutzung des "Zusammenfassenden Konferenzberichts"

Unten im Bericht können Sie die Gesamtwerte der meisten im "Zusammenfassenden Konferenzbericht" verwendeten Metriken finden. Führen Sie einen Bildlauf nach unten durch, wenn Sie zum Beispiel wissen möchten, wie viele Konferenzen insgesamt in einem bestimmten Zeitraum abgehalten wurden oder wie viele Personen an diesen Konferenzen teilgenommen haben. Eine Metrik, zu der es unten im Bericht keine Gesamtsumme gibt, ist die Zahl aller eindeutigen Konferenzorganisatoren. Der Grund dafür lautet: Angenommen, Sie schauen die Daten eines Monats durch. An einem Tag gab es 34 eindeutige Konferenzorganisatoren, an einem anderen dagegen 27. Bedeutet das nun, dass es in diesen zwei Tagen insgesamt 61 eindeutige Konferenzorganisatoren gab? Nicht unbedingt. Schließlich können einige oder alle der 27 Organisatoren des ersten Tages auch zu den 34 Personen gehören, die an dem zweiten Tag Konferenzen organisiert haben. So haben zum Beispiel in diesem einfachen Bericht die Organisatoren Ken Myer und Pilar Ackerman sowohl am 07.07.2012 als auch am 02.07.2012 Konferenzen geplant:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Konferenzorganisator</th>
<th>Konferenzdatum</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>07.07.2012 10:00 Uhr</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>07.07.2012 10:00 Uhr</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>07.07.2012 11:00:00 Uhr</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>07.07.2012 11:00:00 Uhr</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>07.07.2012 13:00</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>07.07.2012 14:00:00 Uhr</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>02.07.2012 10:00 Uhr</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>02.07.2012 10:00 Uhr</p></td>
</tr>
</tbody>
</table>


Wenn Sie genauer wissen möchten, wie viele eindeutige Konferenzorganisatoren es insgesamt gab, ändern Sie einfach den Zeitraum. Schauen Sie zum Beispiel die Daten nach Monaten anstatt nach Tagen aufgeschlüsselt durch.

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Zusammenfassenden Konferenzbericht festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Konferenzen nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Konferenzbericht verwenden können.

### <a name="conference-summary-report-filters"></a>Filter im Zusammenfassenden Konferenzbericht

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
<li><p>Monatlich (maximal 12 Monate können angezeigt werden)</p></li>
</ul>
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall "Täglich" mit dem Startdatum "07.07.2012" und dem Enddatum "28.09.2012" ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2011 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Konferenzbericht angegeben werden.

### <a name="conference-summary-report-metrics"></a>Metriken im Zusammenfassenden Konferenzbericht

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
<td><p>Gibt das Zeitintervall an, das Sie auf der Symbolleiste für Filter ausgewählt haben. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das Intervall "Täglich" verwenden und auf "07.07.2012" klicken, sehen Sie die nach Stunden aufgeschlüsselten Benutzerregistrierungsaktivitäten an diesem Tag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Konferenzen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Konferenzen (unabhängig vom Konferenztyp), die stattfanden. Wenn Sie auf dieses Element klicken, wird der Konferenzaktivitätsbericht für die ausgewählte Zeitspanne eingeblendet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Teilnehmer insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Personen, die an den Konferenzen teilnahmen. Wenn Sie auf dieses Element klicken, wird der Konferenzaktivitätsbericht für die ausgewählte Zeitspanne eingeblendet.</p></td>
</tr>
<tr class="even">
<td><p><strong>Durchschnittliche Anzahl der Teilnehmer pro Konferenz</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die durchschnittliche Anzahl der Personen, die an einer Konferenz teilnahmen. Errechnet sich durch Dividieren der Gesamtzahl der Konferenzen durch die Gesamtzahl der Teilnehmer.</p></td>
</tr>
<tr class="odd">
<td><p><strong>A/V-Konferenzen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Konferenzen mit Audio oder Video.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gesamtdauer der A/V-Konferenzen in Minuten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Minuten, die für Konferenzen mit Audio bzw. aufgewendet wurden.</p>
<p>Die Gesamtzahl der a/v-Konferenz Minuten enthält eine Zusammenfassung aller audiovisuellen Konferenztypen, einschließlich: a/v-Konferenzen; Chat Konferenzen; App-Freigabe Konferenzen; Datenkonferenzen; und PSTN-Konferenzen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gesamtdauer (in Minuten), die Teilnehmer in der A/V-Konferenz verbleiben</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Minuten, die Teilnehmer in Konferenzen mit Audio bzw. Video verbrachten. Beispiel: Angenommen, ein Benutzer verbringt 5 Minuten in einer A/V-Konferenz, und ein zweiter Benutzer verbringt 3 Minuten in der gleichen Konferenz. Dann ergibt dies eine Gesamtdauer von 5 + 3 = 8 Minuten.</p></td>
</tr>
<tr class="even">
<td><p><strong>Durchschnittliche Dauer der A/V-Konferenzen in Minuten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die durchschnittliche Anzahl der Minuten pro A/V-Konferenz.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Eindeutige Konferenzorganisatoren insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Benutzer, die mindestens eine Konferenz organisiert haben. Benutzer, die mehr als eine Konferenz organisiert haben, zählen als ein eindeutiger Organisator, genauso wie Benutzer, die nur eine einzige Konferenz organisiert haben.</p></td>
</tr>
<tr class="even">
<td><p><strong>Konferenznachrichten insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Sofortnachrichten, die während Konferenzen gesendet wurden.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

