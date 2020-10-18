---
title: 'Lync Server 2013: Diagnosebericht'
description: 'Lync Server 2013: Diagnosebericht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 198b836437285b464ba9172e59c9a60ed0a53b65
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576251"
---
# <a name="diagnostic-report-in-lync-server-2013"></a>Diagnosebericht in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-07_

Der Diagnosebericht enthält Diagnose- und Problembehandlungsinformationen der fehlerhaften Sitzung. Er enthält sowohl die während einer fehlerhaften Sitzung berichtete Diagnose-ID als auch den Diagnoseheader. Die Diagnose-ID ist ein eindeutiger Bezeichner (in der Form eines Headers vom Typ "ms-diagnostics") der an eine SIP-Nachricht angefügt wird, während der Diagnoseheader eine begleitende Beschreibung für die Diagnose-ID bietet. Der Bericht enthält möglicherweise auch wertvolle Details für die Problembehandlung, die der Reporting-Komponente bekannt sind. Beispielsweise:

  - Der vom PSTN-Gateway bereitgestellte Ursachencode, der den Fehler generiert hat. Wenn ein ausgehender Anruf im Telefonfestnetz nicht getätigt werden kann, wird automatisch ein ISUP-Ursachencode (ISDN User Part) generiert. Beispielsweise kann ein PSTN-Gateway den Ursachencode 34 senden, um anzuzeigen, dass keine Verbindung bzw. kein Kanal zum Tätigen des Anrufs verfügbar war.

  - FQDN des Peers, Port und Winsock-Fehler für Verbindungsfehler.

  - Namen, die für DNS-Auflösungsfehler ermittelt werden. Die DNS-Auflösung findet immer dann statt, wenn ein Client einen Namenserver kontaktiert und die IP-Adresse anfordert, die dem angegebenen Gerätenamen entspricht.

<div>

## <a name="accessing-the-diagnostic-report"></a>Zugreifen auf den Diagnosebericht

Auf den Diagnosebericht kann zugegriffen werden, indem Sie im [Detailbericht über Peer-to-Peer-Sitzungen in lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) oder im Konferenz Detailbericht auf die Metrik für den Diagnosebericht (Detail) klicken.

</div>

<div>

## <a name="filters"></a>Filter

Keine. Sie können den Diagnosebericht nicht filtern.

</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die im Diagnosebericht enthaltenen Informationen für jeden Anruf aufgeführt.

### <a name="diagnostic-report-metrics"></a>Metriken des Diagnoseberichts

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
<td><p><strong>Berichtszeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Datum und Uhrzeit der Aufzeichnung des Berichts.</p></td>
</tr>
<tr class="even">
<td><p><strong>Antwortcode</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Antwortcode, der bei einem Sitzungsfehler gesendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anforderungstyp</strong></p></td>
<td><p>Nein</p></td>
<td><p>Typ der fehlerhaften SIP-Anforderung. Beispielsweise: INVITE, BYE oder SERVICE.</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>Nein</p></td>
<td><p>Ursache des Fehlers.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Von Benutzer-URI</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Adresse des Benutzers, der die Sitzung initiiert hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Von Benutzer-Agent</strong></p></td>
<td><p>Nein</p></td>
<td><p>Software, die vom Endpunkt des Benutzers, der den Anruf initiiert hat, verwendet wird.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Nein</p></td>
<td><p>Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Inhaltstyp</strong></p></td>
<td><p>Nein</p></td>
<td><p>Typ der fehlerhaften Medieninhalte. Ein gebräuchlicher Inhaltstyp ist beispielsweise Application/sdp. SDP (Session Description Protocol) ist ein Standardinternetprotokoll, das für Sitzungsankündigungen, Sitzungseinladungen und andere Formen von Einladungen für Multimediasitzungen verwendet wird.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anwendung</strong></p></td>
<td><p>Nein</p></td>
<td><p>Anwendung, die am Fehler beteiligt ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>An Benutzer-URI</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Adresse des Benutzers, der zur Sitzung eingeladen wurde.</p></td>
</tr>
<tr class="odd">
<td><p>Zeitpunkt des Beitritts für die Konferenz (ms)</p></td>
<td><p>Nein</p></td>
<td><p>Gesamtdauer (in Millisekunden), die der Benutzer benötigt, um an der Konferenz teilzunehmen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnoseheader</strong></p></td>
<td><p>Nein</p></td>
<td><p>Beschreibung der Diagnose-ID.</p></td>
</tr>
</tbody>
</table>


Eine Liste der Diagnosefehler finden Sie auf der [Kopfzeilenseite der MS-Diagnostics](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

