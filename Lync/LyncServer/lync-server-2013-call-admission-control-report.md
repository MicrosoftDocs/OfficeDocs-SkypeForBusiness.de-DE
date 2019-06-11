---
title: 'Lync Server 2013: Bericht zur Anruf Zulassungs Steuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f31159742757b7ef8b6889b7961bad747b1f6d2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a>Bericht zur Anruf Zulassungs Steuerung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-29_

Der Bericht über Anrufsteuerung bietet Informationen über Peer-to-Peer- und Konferenzsitzungen, die unter Beschränkungen durchgeführt wurden, die über die Anrufsteuerung eingeführt wurden. Die in Microsoft lync Server 2010 eingeführte Anruf Zulassungs Steuerung bietet Administratoren die Möglichkeit, Kommunikationssitzungen basierend auf Bandbreiteneinschränkungen zuzulassen (oder nicht zulassen). Beispielsweise kann ein Administrator Richtlinien erstellen, die die verfügbare Bandbreite für Sprach- und Videoanrufe beschränken. Sobald diese Bandbreitengrenze erreicht ist, können keine neuen Sprach- oder Videoanrufe mehr getätigt werden, bis einer der aktuellen Anrufe beendet worden ist und damit die erforderlichen Netzwerkressourcen freigegeben worden sind.

<div>

## <a name="accessing-the-call-admission-control-report"></a>Öffnen des Berichts über Anrufsteuerung

Auf den Bericht über Anrufsteuerung greifen Sie über die Startseite für Überwachungsberichte zu. Vom Bericht über Anrufsteuerung aus können Sie einen Drilldown zu einem der folgenden Berichte durchführen:

  - Konferenzdetailbericht – Zum Öffnen dieses Berichts klicken Sie auf die Metrik „Details“ einer Konferenzsitzung.

  - Detailbericht über Peer-to-Peer-Sitzungen – Zum Öffnen dieses Berichts klicken Sie auf die Metrik „Details“ für eine Peer-to-Peer-Sitzung.

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a>Optimales Nutzen des Berichts über Anrufsteuerung

Zum Abrufen einer Liste der Anrufe, bei denen wegen nicht ausreichender Bandbreite ein Fehler auftrat, wählen Sie in der Dropdownliste „Anrufkategorie“ den Eintrag „Anrufe, die aufgrund der Anrufsteuerung abgelehnt werden“ aus. Die meisten der zurückgegebenen Anrufe haben wahrscheinlich die Diagnose-ID 5:

Nicht genügend Bandbreite zum Herstellen der Sitzung. PSTN-Umleitung wird versucht.

Dies weist darauf hin, dass Beschränkungen der Anrufsteuerung verhindert haben, dass der Anruf im VoIP-Netzwerk ausgeführt werden konnte.

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Der Anrufsteuerungsbericht ermöglicht Ihnen beispielsweise das Filtern von Anrufen nach dem Benutzer, der den Anruf initiiert hat oder nach dem angerufenen Benutzer. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Anrufsteuerungsbericht verwenden können.

### <a name="call-admission-control-report-filters"></a>Anrufsteuerungsbericht - Filter

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
<td><p><strong>Pool</strong></p></td>
<td><p>Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder Edgeservers. Sie können einen einzelnen Pool auswählen oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Aktivitätstyp</strong></p></td>
<td><p>Aktivitätstyp. Wählen Sie eine der folgenden Aktivitäten aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Peer-to-Peer</p></li>
<li><p>Konferenz</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Anrufkategorie</strong></p></td>
<td><p>Gibt den Grund für die Verwendung der Anrufsteuerung bei einem Anruf an. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Anruf durch Anrufsteuerung abgelehnt</p></li>
<li><p>Anrufe durch Anrufsteuerung über PSTN umgeleitet</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Metriken für Peer-to-Peer-Sitzungen

In der folgenden Tabelle sind die im Anrufsteuerungsbericht für Peer-to-Peer-Sitzungen (d. h. Sitzungen mit nur zwei Teilnehmern) enthaltenen Informationen aufgeführt.

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
<td><p><strong>Detail</strong></p></td>
<td><p>Nein</p></td>
<td><p>Wenn Sie auf dieses Element klicken, zeigt der Bericht einen detaillierten Peer-to-Peer-Sitzungsbericht für die angegebene Sitzung an.</p></td>
</tr>
<tr class="even">
<td><p><strong>Absenderbenutzer</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse des Benutzers, der die Sitzung initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>An Benutzer</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalitäten</strong></p></td>
<td><p>Ja</p></td>
<td><p>Kommunikationsmodalitäten (z. B. Audio und Video), die bei der Sitzung verwendet wurden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Einladungszeitpunkt</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die ursprüngliche Sitzungseinladung an den Benutzer gesendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Antwortzeitpunkt</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Annahme der Einladung empfangen wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Endzeitpunkt</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Sitzung endete.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Ja</p></td>
<td><p>Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>Metriken für Konferenzsitzungen

In der folgenden Tabelle sind die im Anrufsteuerungsbericht für Konferenzsitzungen (d. h. Sitzungen mit mindestens drei Teilnehmern) enthaltenen Informationen aufgeführt.

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
<td><p><strong>Konferenz-URI</strong></p></td>
<td><p>Ja</p></td>
<td><p>Eindeutige ID für die Konferenz. Wenn Sie auf dieses Element klicken, zeigt der Bericht die einzelnen Konferenzteilnehmer an.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organisator</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse des Benutzers, der die Sitzung organisiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Ja</p></td>
<td><p>In der Konferenz verwendeter Edgeserver.</p></td>
</tr>
<tr class="even">
<td><p><strong>Startzeitpunkt</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Endzeitpunkt</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a>Metriken für einzelne Konferenzteilnehmer

In der folgenden Tabelle sind die im Anrufsteuerungsbericht für einzelne Konferenzteilnehmer enthaltenen Informationen aufgeführt.

### <a name="metrics-for-individual-conference-participants"></a>Metriken für einzelne Konferenzteilnehmer

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
<td><p><strong>Rolle</strong></p></td>
<td><p>Nein</p></td>
<td><p>Rolle (z. B. Referent) des Konferenzteilnehmers.</p></td>
</tr>
<tr class="even">
<td><p><strong>Teilnehmer</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Adresse des Konferenzteilnehmers.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Verbindung</strong></p></td>
<td><p>Nein</p></td>
<td><p>Netzwerkverbindungen (in der Regel „From Internal“ oder „From External“) des Teilnehmers.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalität</strong></p></td>
<td><p>Nein</p></td>
<td><p>Konferenztyp (z. B. A/V-Konferenzen).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Beitrittszeitpunkt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>Beendigungszeitpunkt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer die Konferenz verlassen hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Nein</p></td>
<td><p>Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

