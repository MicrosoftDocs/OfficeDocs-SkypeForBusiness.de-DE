---
title: 'Lync Server 2013: Diagnosebericht über Peer-to-Peer-Aktivität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53e47232a6345749f78f6136929209722a83621e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524392"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a>Diagnosebericht über Peer-to-Peer-Aktivitäten in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Der Diagnosebericht über Peer-zu-Peer-Aktivitäten enthält Informationen dazu, ob die Peer-zu-Peer-Sitzungen erfolgreich waren oder ob Fehler aufgetreten sind. Beachten Sie, dass Microsoft lync Server 2013 zwischen verschiedenen Arten von Fehlern unterscheidet:

  - **Erwarteter Fehler**. Ein erwarteter Fehler ist normalerweise nur im technischsten Sinn ein Fehler. Nehmen wir beispielsweise an, Sie rufen jemanden an, aber er ist nicht im Büro und kann das Telefon nicht beantworten. Da der Anruf nicht beantwortet wurde, wird der Anruf technisch als Fehler betrachtet. Auf der anderen Seite war dies ein erwarteter Fehler: Microsoft lync Server 2013 erwartet nicht, dass Sie das Telefon beantworten, wenn Sie nicht zur Verfügung stehen, um das Telefon zu beantworten. Ebenso tritt ein erwarteter Fehler auf, wenn Sie versuchen, eine Sofortnachricht an einen Benutzer zu senden, der offline ist, oder nur an einem Telefon angemeldet ist, das keine Chatnachrichten unterstützt.

  - **Unerwarteter Fehler**: Ein unerwarteter Fehler ist genau das, was der Name aussagt: Ein Fehler, der gemessen an den Umständen nicht zu erwarten ist. Angenommen, Sie rufen eine Person an, und die Person kann den Anruf annehmen. Nehmen wir beispielsweise an, Sie rufen jemanden an, und diese Person steht zur Verfügung, um den Anruf entgegenzunehmen. Wenn lync Server 2013 jedoch versucht, Ihren Anruf an Voicemail weiterzuleiten, schlägt der Anruf fehl, da die Konnektivität mit Exchange Unified Messaging verloren gegangen ist. Das ist ein unerwarteter Fehler: Es kann davon ausgegangen werden, dass Anrufe immer an die Voicemail weitergeleitet werden können. Allgemein gilt die Regel, dass unerwartete Fehler richtige Fehler sind: Es handelt sich dabei um Probleme, die durch Schulung der Benutzer oder ähnliche Maßnahmen nicht behoben werden können.

Beachten Sie, dass die Metriken für "Erfolg", "Erwarteter Fehler" und "Unerwarteter Fehler" nicht zwangsläufig identisch mit der Metrik unter "Sitzungen insgesamt" sind. In der obigen Abbildung sind beispielsweise die folgenden Werte enthalten:


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


Wenn Sie 2024 + 469 + 16 hinzufügen, erhalten Sie insgesamt 2.509 Sitzungen, doch in der Spalte Gesamt Sitzungen werden insgesamt 2.521 Sitzungen angezeigt. Die "fehlenden" 12 Sitzungen sind Sitzungen, die vom System nicht als erfolgreich oder nicht erfolgreich kategorisiert werden konnten. Dies ist manchmal der Fall, wenn ein Drittanbieterprodukt einen neuen Diagnosecode einführt, der lync Server nicht vertraut ist. Wenn dies geschieht, können mit diesem Produkt erstellte Anrufe und das melden dieses Diagnosecodes nicht immer als ein Erfolg, ein erwarteter Fehler oder ein unerwarteter Fehler kategorisiert werden.

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>Zugreifen auf den Diagnosebericht über Peer-zu-Peer-Aktivitäten

Auf den Diagnosebericht über Peer-zu-Peer-Aktivitäten greifen Sie über die Homepage für Überwachungsberichte zu. Sie können auf den [Bericht über Fehlerverteilung in lync Server 2013](lync-server-2013-failure-distribution-report.md) zugreifen, indem Sie auf eine der folgenden Metriken klicken:

  - Anzahl der unerwarteten Fehler

  - Anzahl der erwarteten Fehler

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>Optimales Verwenden des Diagnoseberichts über Peer-zu-Peer-Aktivitäten

Es gibt mehrere Möglichkeiten, wie Sie den Diagnosebericht über Peer-zu-Peer-Aktivitäten filtern können, aber die Filteroptionen sind standardmäßig ausgeblendet. Um die verfügbaren Filteroptionen anzuzeigen, klicken Sie im Berichtfenster oben rechts auf die Schaltfläche zum Ein- und Ausblenden der Parameter. Danach können Sie die Filteroptionen verwenden.

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise ansehen. Beispielsweise können Sie im Diagnosebericht über Peer-zu-Peer-Aktivitäten nach Kriterien wie etwa Sitzungsmodalität (z. B. Sofortnachrichten, Dateiübertragung oder Anwendungsfreigabe) filtern. Sie können auch auswählen, wie Daten gruppiert werden sollen. In diesem Fall werden Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Diagnosebericht über Peer-zu-Peer-Aktivitäten verwenden können.

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a>Filter im Diagnosebericht über Peer-zu-Peer-Aktivitäten

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
<tr class="odd">
<td><p><strong>Modalität</strong></p></td>
<td><p>Gibt den Typ der Kommunikationsaktivität an, die stattgefunden hat. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Alle</p></li>
<li><p>Sofortnachrichten</p></li>
<li><p>Dateiübertragung</p></li>
<li><p>Anwendungsfreigabe</p></li>
<li><p>Audio</p></li>
<li><p>Video</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a>Metrik (pro Modalität)

In der folgenden Tabelle werden die Metriken aufgelistet, die im Diagnosebericht über Peer-zu-Peer-Aktivitäten für jede Modalität angegeben werden.

### <a name="metrics-per-modality"></a>Metrik (pro Modalität)

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
<td><p>Die Gesamtzahl der erfolgreichen Peer-zu-Peer-Sitzungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prozentsatz der erfolgreichen Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Peer-zu-Peer-Sitzungen, die ohne nennenswerte Probleme ausgeführt wurden. Errechnet sich durch Dividieren der Anzahl der erfolgreichen Sitzungen durch die Gesamtzahl der Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anzahl der erwarteten Fehler</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Sitzungen, bei denen ein &quot; Erwarteter Fehler &quot; aufgetreten ist.</p>
<p>Ein erwarteter Fehler ist ein Fehler, dessen Auftreten erwartet wird. Wenn beispielsweise ein Benutzer seinen Status auf Nicht stören festgelegt hat, ist zu erwarten, dass jeder Anruf an diesen Benutzer fehlschlägt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prozentsatz der erwarteten Fehler</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein erwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der erwarteten Fehler durch die Gesamtzahl der Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anzahl der unerwarteten Fehler</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Sitzungen, bei denen ein &quot; unerwarteter Fehler &quot; aufgetreten ist.</p>
<p>Ein unerwarteter Fehler ist ein Fehler, der in einem System auftritt, das abgesehen davon anscheinend intakt ist. Beispielsweise sollte ein Anruf nicht beendet werden, wenn der Anrufer in der Warteschleife platziert ist. Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prozentsatz der unerwarteten Fehler</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein unerwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der unerwarteten Fehler durch die Gesamtzahl der Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

