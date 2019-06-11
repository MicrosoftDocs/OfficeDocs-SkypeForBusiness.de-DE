---
title: 'Lync Server 2013: Peer-to-Peer-Sitzungs Detail Bericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec73febb248a8b61979c0aad2df6977c9feccb91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a>Peer-zu-Peer-Sitzungs Detail Bericht in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-06_

Der Detailbericht über Peer-to-Peer-Sitzungen gibt detaillierte Informationen über eine Peer-to-Peer-Sitzung zurück. Wenn Sie beispielsweise eine Sofortnachrichtensitzung auswählen, gibt der Bericht Ihnen die Anzahl an Nachrichten an, die jeweils von den beiden an der Sitzung beteiligten Benutzern gesendet wurden.

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a>Zugriff auf den Detailbericht über Peer-to-Peer-Sitzungen

Sie können über die folgenden Berichte (die alle über die Startseite für Überwachungsberichte aufgerufen werden können) auf den Detailbericht über Peer-to-Peer-Sitzungen zugreifen:

  - Inventurbericht über IP-Telefone

  - Bericht über Benutzeraktivität

  - Bericht über Anrufsteuerung

  - Fehlerlistenbericht

Im Bericht Peer-to-Peer-Sitzungsdetails können Sie auf den [Diagnosebericht in lync Server 2013](lync-server-2013-diagnostic-report.md) zugreifen, indem Sie auf die Metrik für den Diagnosebericht (Details) klicken. Sie können zudem auf den Bericht über häufigste Fehler zugreifen, indem Sie auf eine der folgenden beiden Metriken klicken:

  - Reaktion

  - Diagnose-ID

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>Optimale Verwendung des Detailberichts über Peer-to-Peer-Sitzungen

Der Detailbericht über Peer-to-Peer-Sitzungen enthält zahlreiche Metriken, mit denen die Systemadministratoren möglicherweise zum Teil nicht vertraut sind. Häufig können Sie jedoch ein Tooltip mit einer kurzen Beschreibung der Metrik anzeigen, indem Sie den Mauszeiger über die Bezeichnung der jeweiligen Metrik bewegen.

Beachten Sie, dass die tatsächlichen Metriken, die in einem bestimmten Bericht angezeigt werden, von der ausgewählten Peer-to-Peer-Sitzung abhängen. So wird für eine Audio-/Videositzung ein anderer Satz an Metriken ausgegeben als für eine Sofortnachrichtensitzung.

Sie können den Mauszeiger auch über die Antwortcode- und Diagnose-ID-Metriken bewegen, um eine Beschreibung der folgenden Werte anzuzeigen:

</div>

<div>

## <a name="filters"></a>Filter

Keine. Der Detailbericht über Peer-to-Peer-Sitzungen kann nicht gefiltert werden.

</div>

<div>

## <a name="session-information-metrics"></a>Sitzungsinformationen - Metriken

In der folgenden Tabelle sind die Informationen aufgelistet, die im Detailbericht über Peer-to-Peer-Sitzungen angegeben werden.

### <a name="session-information-metrics"></a>Sitzungsinformationen - Metriken

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
<td><p><strong>Pool-FQDN</strong></p></td>
<td><p>Vollqualifizierter Domänenname (FQDN) des Registrar-Pools oder Edgeservers in der Sitzung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Einladungszeitpunkt</strong></p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Sitzungseinladung ursprünglich gesendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Antwortzeitpunkt</strong></p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Annahme der Einladung empfangen wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Absenderbenutzer</strong></p></td>
<td><p>SIP-Adresse des Benutzers, der die Sitzung initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Von Benutzeragent</strong></p></td>
<td><p>Software, die vom Endpunkt des Benutzers, der die Sitzung initiiert hat, verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>Interner Absenderbenutzer</strong></p></td>
<td><p>Gibt an, ob der Benutzer, der die Sitzung initiiert hat, am internen Netzwerk angemeldet war.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Absenderbenutzer mit Telefonapparat</strong></p></td>
<td><p>Gibt an, ob der Endpunkt des Benutzers, der die Sitzung initiiert hat, mit seinem Desktoptelefon integriert ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sitzungspriorität</strong></p></td>
<td><p>Die der Sitzung zugewiesene Priorität. Gültige Prioritäten sind „Unbekannt“, „Nicht dringend“, „Normal“, „Dringend“ und „Notfall“.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Antwortcode</strong></p></td>
<td><p>SIP-Antwortcode, der bei einem Sitzungsfehler gesendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Front-End</strong></p></td>
<td><p>Name des in der Konferenz verwendeten Front-End-Servers.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Erfassungszeitpunkt</strong></p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Sitzungsinformationen erfasst wurden.</p></td>
</tr>
<tr class="even">
<td><p><strong>Endzeitpunkt</strong></p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Sitzung endete.</p></td>
</tr>
<tr class="odd">
<td><p><strong>An Benutzer</strong></p></td>
<td><p>SIP-Adresse des Benutzers, der zur Sitzung eingeladen wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Empfängerbenutzeragent</strong></p></td>
<td><p>Die vom Endpunkt des Benutzers verwendete Software, der zur Teilnahme an der Sitzung eingeladen wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Interner Empfängerbenutzer</strong></p></td>
<td><p>Gibt an, ob der Benutzer, der zur Teilnahme an der Sitzung eingeladen wurde, am internen Netzwerk angemeldet war.</p></td>
</tr>
<tr class="even">
<td><p><strong>Empfängerbenutzer mit Telefonapparat</strong></p></td>
<td><p>Gibt an, ob der Endpunkt des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde, mit seinem Desktoptelefon integriert ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Wiederholungsversuch der Sitzung</strong></p></td>
<td><p>Gibt an, ob die Sitzung ein Wiederholungsversuch einer zuvor fehlgeschlagenen Sitzung ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Halten Sie den Mauszeiger über die ID-Nummer, um zusätzliche Information zu dieser ID anzuzeigen.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a>Metriken für Modalitäten

In der folgenden Tabelle sind die Informationen aufgelistet, die im Detailbericht über Peer-to-Peer-Sitzungen zu jeder Sitzungsmodalität angegeben werden.

### <a name="metrics-for-modalities"></a>Metriken für Modalitäten

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
<td><p><strong>Modalitäten</strong></p></td>
<td><p>Nein</p></td>
<td><p>In der Sitzung verwendete Modalitäten, z. B. Chat, Audio oder Dateiübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nachrichten von Absenderbenutzer</strong></p></td>
<td><p>Nein</p></td>
<td><p>Anzahl der gesendeten Nachrichten des Benutzers, der die Sitzung initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nachrichten an Empfängerbenutzer</strong></p></td>
<td><p>Nein</p></td>
<td><p>Anzahl der gesendeten Nachrichten des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a>Metriken für Diagnoseberichte

In der folgenden Tabelle sind die Informationen aufgelistet, die im Detailbericht über Peer-to-Peer-Sitzungen zu jeden Diagnosebericht angegeben werden.

### <a name="metrics-for-diagnostic-reports"></a>Metriken für Diagnoseberichte

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
<td><p>Klicken Sie auf dieses Element, um den Diagnosebericht für die Sitzung anzuzeigen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Berichtszeitpunkt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Datum und Uhrzeit der Aufzeichnung des Berichts.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anforderung</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Anforderungstyp, z. B. INVITE oder BYE.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Nein</p></td>
<td><p>Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Inhaltstyp</strong></p></td>
<td><p>Nein</p></td>
<td><p>In der Konferenz verwendeter Medieninhaltstyp. Ein gängiger Inhaltstyp ist beispielsweise „Application/sdp“. SDP (Session Description Protocol) ist ein Standardinternetprotokoll, das für Sitzungsankündigungen, Sitzungseinladungen und andere Formen des Multimediasitzungsaufbaus verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>Berichtet von</strong></p></td>
<td><p>Nein</p></td>
<td><p>Computer (d. h. Client oder Server), der das Problem berichtet hat.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

