---
title: 'Lync Server 2013: errorreport-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1fe360726c94062391a4559f73a375d68b5f384
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a>ErrorReport-Ansicht in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-22_

In der errorreport-Ansicht werden Informationen zu gemeldeten Fehlern gespeichert. Bei jedem Datensatz handelt es sich um ein Fehlerereignis. Die Fehler werden entweder von dem auf dem Front-End-Server ausgeführten KDS-Agent erfasst oder vom Client gesendet. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Fehler</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Zeitpunkt des Fehlers. Wird zusammen mit "ErrorReportSeq" verwendet, um einen Fehler eindeutig zu bestimmen.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID-Nummer zum Bestimmen des Fehlers. Wird zusammen mit "ErrorTime" verwendet, um einen Fehler eindeutig zu bestimmen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>Diagnose-ID für den Fehlerbericht.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Benutzers, von dem der Fehler stammt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URI-Typ des Benutzers, der den Fehler ausgelöst hat. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Mandant des Benutzers, der den Fehler ausgelöst hat. Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Touri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Benutzers, der das Ziel des Fehlerberichts war.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URI-Typ des Benutzers, der das Ziel des Fehlerberichts ist. Weitere Informationen finden Sie in der UriTypes Table.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Mandant des Benutzers, der den Fehlerbericht abzielt. Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI der Konferenz, die das Ziel des Fehlerberichts war.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URI-Typ der Konferenz, die das Ziel des Fehlerberichts war. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionID</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung, von der der Fehlerbericht stammt. Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID-Nummer zum Identifizieren der Sitzungsanforderung, von der der Fehlerbericht stammt. Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ID</strong></p></td>
<td><p>varstring (775)</p></td>
<td><p>SIP-Dialogfeld-ID der Sitzung mit Ursprung des Fehlers. Das Format lautet wie folgt:</p>
<p>Dialogfeld; from-Tag; to-Tag</p>
<p>Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</p>
<p>Umwandlung (Umwandlung (extern-als varbinary (max)) als varchar (max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Version des Clients, die von dem Benutzer verwendet wird, der den Fehler ausgelöst hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Client, der vom Benutzer verwendet wird, der den Fehler ausgelöst hat. Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Name der Kategorie des Clients, der vom Benutzer verwendet wird, der den Fehler ausgelöst hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Name des Servers, von dem der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Name der Anwendung, von der der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>SIP-Antwortcode für die Sitzung der SIP-Nachricht, die den Fehlerbericht enthält.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Der Typ der fehlgeschlagenen Anforderung.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Der Inhaltstyp der fehlgeschlagenen Anforderung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Der Sitzungstyp. Weitere Informationen finden Sie <a href="lync-server-2013-calltype-table.md">in der CallType-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Telemetrie</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Eindeutiger Bezeichner, der die Informationen über den Zeitpunkt des Beitritts für verschiedene in einer Konferenz beteiligten Komponenten korreliert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rüstzeit</strong></p></td>
<td><p>int</p></td>
<td><p>Für eine bestimmte Komponente erforderliche Zeit (in Millisekunden), um an einer Konferenz teilzunehmen.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>Bit</p></td>
<td><p>Gibt an, ob der Fehlerbericht vom auf dem Front-End-Server ausgeführten KDS-Agent erfasst oder vom Client gesendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Wert</strong></p></td>
<td><p>smallint</p></td>
<td><p>Reserviert für zukünftige Verwendung.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Zusätzliche Informationen zu dem Fehler.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Frontend</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>Vollqualifizierter Domänenname des Front-End-Servers, der den Bericht übermittelt hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>Vollqualifizierter Domänenname des Pools mit dem Front-End-Server, der den Bericht übermittelt hat.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

