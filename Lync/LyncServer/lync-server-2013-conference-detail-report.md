---
title: 'Lync Server 2013: Konferenz Detail Bericht'
description: 'Lync Server 2013: Konferenz Detail Bericht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07c50b545f4a9ee3308a840fc2aa5a15e617a5bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577631"
---
# <a name="conference-detail-report-in-lync-server-2013"></a>Konferenz Detail Bericht in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

Der detaillierte Konferenzbericht enthält ausführliche Informationen zu allen Benutzern, die an einer Konferenz teilgenommen haben. Sie können beispielsweise Informationen wie Datum und Uhrzeit, an dem bzw. zu der ein Benutzer einer Konferenz beigetreten ist und die Konferenz verlassen hat, sowie den Benutzer-Agent des Endpunkts anzeigen, mit dem der Benutzer mit der Konferenz verbunden wurde. Darüber hinaus können Sie Informationen zu der Rolle des Benutzers in den einzelnen Konferenzen (z. B. Referent oder Teilnehmer) anzeigen. Der vielleicht wichtigste Aspekt ist, dass Sie auf einen Blick erkennen können, welche Benutzer der Konferenz erfolgreich beigetreten und sie abgeschlossen haben und welche Benutzer der Konferenz nicht beitreten konnten und sie daher nicht abgeschlossen haben.

<div>

## <a name="accessing-the-conference-detail-report"></a>Zugreifen auf den detaillierten Konferenzbericht

Auf den detaillierten Konferenzbericht kann über die folgenden Berichte zugegriffen werden:

  - Der [anrufsteuerungsbericht in lync Server 2013](lync-server-2013-call-admission-control-report.md) (durch Klicken auf die Metrik "Detail" für eine Konferenz)

  - Der [fehlerlistenbericht in lync Server 2013](lync-server-2013-failure-list-report.md) (durch Klicken auf die Konferenz Metrik)

  - Der [Bericht über Benutzeraktivität in lync Server 2013](lync-server-2013-user-activity-report.md) (durch Klicken auf die Metrik Konferenz-URI)

Aus dem Konferenz Detail Bericht können Sie auf den [Diagnosebericht in lync Server 2013](lync-server-2013-diagnostic-report.md) zugreifen, indem Sie auf die Metrik für den Diagnosebericht (Detail) klicken.

</div>

<div>

## <a name="filters"></a>Filter

Keine. Der detaillierte Konferenzbericht lässt sich nicht filtern.

</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Informationen aus dem Abschnitt zu Konferenzinformationen des detaillierten Konferenzberichts aufgeführt.

### <a name="conference-information-metrics"></a>Konferenzinformationen – Metriken

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
<td></td>
<td><p>Der Konferenz zugewiesener URI. Beispiel:</p>
<p>SIP: kmyer@litwareinc. com; GRUU; Opaque = App: conf: Focus: ID: drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool-FQDN</strong></p></td>
<td></td>
<td><p>Vollqualifizierter Domänenname des Registrierungspools oder Edgeservers in einer Sitzung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Beginn</strong></p></td>
<td></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organisator</strong></p></td>
<td></td>
<td><p>SIP-Adresse des Benutzers, der die Sitzung organisiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Endzeit</strong></p></td>
<td></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle werden die Informationen aus dem Abschnitt zur Konferenzteilnahme des detaillierten Konferenzberichts aufgeführt.

### <a name="conference-participation-metrics"></a>Konferenzteilnahme – Metriken

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
<td><p><strong>Benutzende</strong></p></td>
<td></td>
<td><p>SIP-Adresse des Benutzers, der an der Konferenz teilgenommen hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rolle</strong></p></td>
<td></td>
<td><p>Rolle (z. B. Referent) des Konferenzteilnehmers.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Konnektivität</strong></p></td>
<td></td>
<td><p>Netzwerkverbindungen (in der Regel "From Internal" oder "From External") des Teilnehmers.</p></td>
</tr>
<tr class="even">
<td><p>Zeitpunkt des Beitritts</p></td>
<td></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Zeitpunkt der Beendigung</strong></p></td>
<td></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer die Konferenz verlassen hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Benutzer-Agent</strong></p></td>
<td></td>
<td><p>ID für die vom Endpunkt des Teilnehmers verwendete Software.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Diagnoseberichte</strong></p></td>
<td></td>
<td><p>Enthält Diagnose- und Problembehandlungsinformationen, einschließlich SIP-Antwortcodes, Diagnoseheader, Zeitpunkt des Konferenzbeitritts und Diagnose-IDs für fehlgeschlagene Sitzungen.</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle sind die Informationen aufgeführt, die im Abschnitt "Konferenz Modalitäten" des Konferenz Detail Berichts angegeben sind.

### <a name="conference-modalities-metrics"></a>Konferenzmodalitäten – Metriken

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
<td><p><strong>Benutzende</strong></p></td>
<td></td>
<td><p>SIP-Adresse des Benutzers, der an der Konferenz teilgenommen hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Zeitpunkt des Beitritts</strong></p></td>
<td></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Zeitpunkt der Beendigung</strong></p></td>
<td></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der ein Teilnehmer die Konferenz verlassen hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Konferenzserver-URI</strong></p></td>
<td></td>
<td><p>URI für den in der Konferenz verwendeten Konferenzserver.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Diagnoseberichte</strong></p></td>
<td></td>
<td><p>Enthält Diagnose- und Problembehandlungsinformationen, einschließlich SIP-Antwortcodes, Diagnoseheader, Zeitpunkt des Konferenzbeitritts und Diagnose-IDs für fehlgeschlagene Sitzungen.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

