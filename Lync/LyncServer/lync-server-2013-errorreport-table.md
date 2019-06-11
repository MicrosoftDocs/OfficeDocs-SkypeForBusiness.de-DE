---
title: 'Lync Server 2013: ErrorReport-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0fc30d4686ffcc1d1cda0474b3b01a645c94be5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a>ErrorReport-Tabelle in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

In der errorreport-Tabelle werden Informationen zu Fehlern gespeichert, die aufgetreten sind. Bei jedem Datensatz handelt es sich um ein Fehlerereignis. Die Fehler werden entweder vom CDR-Agent, der auf dem Front-End-Server ausgeführt wird, erfasst oder vom Client gesendet.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Schlüssel/Index</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Fehlerzeit</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Das Datum und die Uhrzeit, zu der der Fehler aufgetreten ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Die ID-Nummer, um den Fehlerbericht zu identifizieren. Wird in Verbindung mit <strong>Fehler</strong> Zeit verwendet, um einen Fehlerbericht eindeutig zu identifizieren.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorID</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Eindeutige ID des Fehlertyps. Weitere Informationen finden Sie <a href="lync-server-2013-errordef-table.md">in der ErrorDef-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Benutzer, der die Anforderung initiiert hat, die den Fehler verursacht hat. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Touser-Nr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Zielbenutzer für die Anforderung, die den Fehler verursacht hat. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Konferenz-URI im Zusammenhang mit dem Fehler. Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> . Wenn ConferenceUriId nicht NULL ist, ist in der Regel entweder FromUserId oder touser-Wert NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionID</strong></p></td>
<td><p>datetime</p></td>
<td><p>Fremd</p></td>
<td><p>Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>SourceID</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wird). Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Serverkomponente gesendet wird). Weitere Informationen finden Sie <a href="lync-server-2013-application-table.md">in der Anwendungstabelle in lync Server 2013</a> .</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>Bild</p></td>
<td><p> </p></td>
<td><p>Weitere Informationen zum Fehler.</p>
<p>Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die Client Version des Endpunkts, der den Fehlerbericht sendet. Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der ClientVersions-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Der Fehlerbericht, der vom auf dem Front-End-Server ausgeführten CDR-Agent erfasst oder vom Client gesendet wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>Kennzeichnen</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Für die spätere Verwendung reserviert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Telemetrie</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>Eindeutiger Bezeichner, in dem die Verknüpfungszeit Informationen für die verschiedenen an einer Konferenz beteiligten Komponenten korreliert werden.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Zeit (in Millisekunden), die für eine bestimmte Komponente erforderlich ist, um an einer Konferenz teilzunehmen.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerID</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Stellt den vollqualifizierten Domänennamen des Servers dar, der den Fehlerbericht generiert hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool-Nr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Stellt den vollqualifizierten Domänennamen des Pools dar, in dem der Fehlerbericht generiert wurde.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

