---
title: 'Lync Server 2013: Bericht über die häufigsten Fehler'
description: 'Lync Server 2013: Bericht "Top Failures".'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 768c9a99916dece9eb76877b0cd65b057697ff95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561271"
---
# <a name="top-failures-report-in-lync-server-2013"></a>Bericht über die häufigsten Fehler in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Der Bericht über häufigste Fehler bietet einen Überblick über die am häufigsten gemeldeten Fehler mit Trenddarstellung.

  - **Diagnose-ID**. Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.

  - **Antwortcode**. In SIP-Kommunikationssitzungen werden Antwortcodes verwendet, um auf SIP-Anforderungen zu reagieren. Nehmen wir beispielsweise an, dass Ken die INVITE-Anforderung an Pilar Ackerman sendet (angenommen, Ken Myers ruft Pilar Ackerman an). Wenn Pilar antwortet, sendet Ihr Telefon den Antwortcode 200 (OK) und lässt Ken Telefon wissen, dass Pilar geantwortet hat. Der Bericht "Top Failures" enthält nur Antwortcodes, die als Reaktion auf einen Anruf Fehler gesendet wurden. In lync Server werden nicht alle im Verlauf eines Anrufs ausgestellten Antwortcodes protokolliert.

Informationen werden nicht nur für die Gesamtzahl an Sitzungen, in denen ein Fehler aufgetreten ist, gemeldet, sondern auch für die Gesamtzahl der Benutzer, die von den Fehlern betroffen waren.

<div>

## <a name="accessing-the-top-failures-report"></a>Zugriff auf den Bericht über häufigste Fehler

Der Zugriff auf den Bericht über häufigste Fehler erfolgt von der Überwachungsberichte-Startseite aus. Durch Klicken auf die Metrik "gemeldete Sitzungen" gelangen Sie zum [Bericht über Fehlerverteilung in lync Server 2013](lync-server-2013-failure-distribution-report.md).

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a>Beste Nutzung des Berichts häufigster Fehler

Der Bericht häufigster Fehler ist in einer Hinsicht ungewöhnlich: Er ermöglicht Ihnen gleichzeitig, nach bis zu 5 Diagnose-IDs zu filtern (normalerweise kann nur nach einem Element gleichzeitig gefiltert werden, z. B. nach der SIP-Adresse des Benutzers). Um nach mehreren Diagnose-IDs zu filtern, geben Sie einfach alle IDs durch Kommas getrennt in das Feld "Diagnose-IDs" ein (Sie können, müssen aber nicht nach jedem Komma ein Leerzeichen einfügen). Beispiel:

1011, 2412, 1033, 52116, 1008

Wenn Sie dies tun, werden nur fehlerhafte Anrufe, die mindestens eine dieser fünf Diagnose-IDs gemeldet haben, angezeigt.

Wenn Sie Ihre Maus über einen Antwortcode bewegen, wird eine QuickInfo angezeigt, die Ihnen mitteilt, was der jeweilige Antwortcode bedeutet. Wenn Sie beispielsweise die Maus über den Antwortcode 486 bewegen, wird folgende Meldung angezeigt:

Ausgelastet.

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie die zurückgegebenen Daten im Bericht über häufigste Fehler nach Kriterien wie dem Aktivitätstyp (Peer-zu-Peer-Sitzung oder Konferenzsitzung) oder dem SIP-Antwortcode für die fehlgeschlagene Sitzung filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Ereignisse nach Stunde, Tag, Woche oder Monat zusammengefasst

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über häufigste Fehler verwenden können.

### <a name="top-failures-report-filters"></a>Filter im Bericht über häufigste Fehler

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
<td><p><strong>Aktivitätstyp</strong></p></td>
<td><p>Aktivitätstyp. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Alle</p></li>
<li><p>Peer-to-Peer</p></li>
<li><p>Konferenz</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Modalität</strong></p></td>
<td><p>Derzeit ist nur die Option <strong>[Alle]</strong> verfügbar.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder des Edgeservers. Sie können entweder einen einzelnen Pool auswählen oder auf <strong>[Alle]</strong> klicken, um Daten für alle Pools anzuzeigen. Diese Dropdownliste wird automatisch anhand der Datensätze in der Datenbank aufgefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Kategorie</strong></p></td>
<td><p>Der Typ des aufgetretenen Fehlers. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Erwartete und unerwartete Fehler</p></li>
<li><p>Unerwarteter Fehler</p></li>
</ul>
<p>Ein &quot; Erwarteter Fehler &quot; ist ein Fehler, der voraussichtlich eintreten wird. Hat beispielsweise ein Benutzer seinen Status auf "Nicht stören" gesetzt, ist zu erwarten, dass alle Anrufe an diesen Benutzer fehlschlagen. Ein &quot; unerwarteter Fehler &quot; ist ein Fehler, der in einem ansonsten fehlerhaften System auftritt. Beispielsweise sollte ein Anruf nicht abgebrochen werden, während der Anrufer sich in der Warteschleife befindet. Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Antwortcode</strong></p></td>
<td><p>Der SIP-Antwortcode, der gesendet wird, wenn die Konferenz fehlschlägt. Geben Sie den vollständigen Antwortcode ein. Beispiel:</p>
<p>400</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Der eindeutige Bezeichner (im Format eines ms-diagnostics-Headers), der an eine SIP-Nachricht angehängt ist und häufig Informationen enthält, die bei der Problembehandlung hilfreich sind. Diagnoseheader sind optional (es gibt auch SIP-Sitzungen, die keinen solchen Header enthalten), und Diagnose-IDs werden nur für Sitzungen zurückgegeben, bei denen ein Problem aufgetreten ist.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über häufigste Fehler angegeben werden.

### <a name="top-failures-report-metrics"></a>Metriken im Bericht über häufigste Fehler

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
<td><p><strong>Rank</strong></p></td>
<td><p>Ja</p></td>
<td><p>Der relative Rang basierend auf der Anzahl der gemeldeten Sitzungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gemeldete Sitzungen</strong></p></td>
<td><p>Ja</p></td>
<td><p>Die Gesamtzahl der fehlerhaften Sitzungen basierend auf der Diagnose-ID und dem SIP-Antwortcode.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Betroffene Benutzer</strong></p></td>
<td><p>Ja</p></td>
<td><p>Die Gesamtzahl der Benutzer, die von der fehlerhaften Sitzung betroffen waren.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fehlerinformationen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Genaue Angaben zu dem Fehler, u. a. die Diagnose-ID, der SIP-Antwortcode und eine Beschreibung der Ursache des Sitzungsfehlers.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Trend in der Vergangenheit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Eine grafische Darstellung der fehlerhaften Sitzungen über einen bestimmten Zeitraum.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

