---
title: 'Lync Server 2013: errorreport-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b50a2615fe83ed481d9642ac6895120f20b9fd0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a>ErrorReport-Ansicht in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-22_

In der errorreport-Ansicht werden Informationen zu den gemeldeten Fehlern gespeichert. Bei jedem Datensatz handelt es sich um ein Fehlerereignis. Die Fehler werden entweder vom CDR-Agent, der auf dem Front-End-Server ausgeführt wird, erfasst oder vom Client gesendet. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.


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
<td><p><strong>Fehlerzeit</strong></p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt des Fehlers. Wird in Verbindung mit ErrorReportSeq verwendet, um einen Fehler eindeutig zu identifizieren.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Die ID-Nummer, um den Fehler zu identifizieren. Wird in Verbindung mit Fehlerzeit verwendet, um einen Fehler eindeutig zu identifizieren.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>Diagnose-ID für den Fehlerbericht.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Der URI des Benutzers, der den Fehler ausgelöst hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Typ des URIs des Benutzers, der den Fehler ausgelöst hat. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Mandant des Benutzers, der den Fehler ausgelöst hat. Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Touri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Der URI des Benutzers, der das Ziel des Fehlerberichts war.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Typ des URIs des Benutzers, der auf den Fehlerbericht ausgerichtet ist. Weitere Informationen finden Sie in der UriTypes-Tabelle.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Mandant des Benutzers, der auf den Fehlerbericht abzielt. Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Der URI der Konferenz, die das Ziel des Fehlerberichts war.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der URI-Typ der Konferenz, die das Ziel des Fehlerberichts war. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionID</strong></p></td>
<td><p>datetime</p></td>
<td><p>Die Uhrzeit der Sitzungsanforderung, von der der Fehlerbericht stammt. Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Die ID-Nummer, mit der die Sitzungsanforderung identifiziert wird, von der der Fehlerbericht stammt. Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Dialogfeld-Nr</strong></p></td>
<td><p>varstring (775)</p></td>
<td><p>SIP-Dialogfeld-ID der Sitzung, die den Fehler ausgelöst hat. Das Format lautet:</p>
<p>Dialogfeld; from-Tag; to-Tag</p>
<p>Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</p>
<p>Umwandlung (Umwandlung (extern-als varbinary (max)) als varchar (max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Die Version des Clients, die von dem Benutzer verwendet wird, der den Fehler verursacht hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Clienttyp</strong></p></td>
<td><p>int</p></td>
<td><p>Der Client, der vom Benutzer verwendet wird, der den Fehler ausgelöst hat. Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Der Name der Kategorie des Clients, der vom Benutzer verwendet wird, der den Fehler ausgelöst hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Quelle</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Name des Servers, der den Fehler verursacht hat (wenn der Bericht von einer Serverkomponente gesendet wurde).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anwendung</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Name der Anwendung, die den Fehler verursacht hat (wenn der Bericht von einer Serverkomponente gesendet wurde).</p></td>
</tr>
<tr class="even">
<td><p><strong>Response Code</strong></p></td>
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
<td><p>Inhaltstyp der fehlgeschlagenen Anforderung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Sitzungstyp. Weitere Informationen finden Sie in der Tabelle "CallType" <a href="lync-server-2013-calltype-table.md">in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Telemetrie</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Eindeutiger Bezeichner, in dem die Verknüpfungszeit Informationen für die verschiedenen an einer Konferenz beteiligten Komponenten korreliert werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rüstzeit</strong></p></td>
<td><p>int</p></td>
<td><p>Zeit (in Millisekunden), die für eine bestimmte Komponente erforderlich ist, um an einer Konferenz teilzunehmen.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob der Fehlerbericht vom auf dem Front-End-Server ausgeführten CDR-Agent erfasst oder vom Client gesendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Kennzeichnen</strong></p></td>
<td><p>smallint</p></td>
<td><p>Für die spätere Verwendung reserviert.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Weitere Informationen zum Fehler.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>Vollständig qualifizierter Domänenname des Front-End-Servers, der den Bericht übermittelt hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>Vollständig qualifizierter Domänenname des Pools, der den Front-End-Server enthält, der den Bericht übermittelt hat.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

