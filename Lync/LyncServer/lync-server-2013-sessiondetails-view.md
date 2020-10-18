---
title: 'Lync Server 2013: SessionDetails-Ansicht'
description: 'Lync Server 2013: SessionDetails-Ansicht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c9f657257e54389defb805919be61adbdecad74
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573241"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a>SessionDetails-Ansicht in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

In der SessionDetails-Ansicht werden Informationen über Peer-to-Peer-Sitzungen gespeichert, bei denen es sich um einen VoIP-VoIP Telefonanruf, eine Sofortnachrichtensitzung mit zwei Teilnehmern oder eine andere Art von Sitzung handeln kann. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.


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
<td><p><strong>SessionID</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung. Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> Tabelle.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID zur Identifikation der Sitzung. Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Invitezeit</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Zeitpunkt der ersten INVITE-Anforderung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Benutzers, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Touri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Benutzers, der der Sitzung beigetreten ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Typ des URI des Benutzers, der die Sitzung gestartet hat. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Typ des URI des Benutzers, der der Sitzung beigetreten ist. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Mandant des Benutzers, der die Sitzung gestartet hat. Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Mandant des Benutzers, der der Sitzung beigetreten ist. Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Eindeutiger Bezeichner des Endpunkts des Benutzers, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Toendpointo</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Eindeutiger Bezeichner des Endpunkts des Benutzers, der der Sitzung beigetreten ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Endzeitpunkt der Sitzung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMessageCount</strong></p></td>
<td><p>int</p></td>
<td><p>Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMessageCount</strong></p></td>
<td><p>int</p></td>
<td><p>Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der der Sitzung beigetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Version des Clients, die der Benutzer verwendet, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Client, den der Benutzer verwendet, der die Sitzung gestartet hat. Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Name der Kategorie des Clients, den der Benutzer verwendet, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Version des Clients, die der Benutzer verwendet, der der Sitzung beigetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Toclienttype</strong></p></td>
<td><p>int</p></td>
<td><p>Client, den der Benutzer verwendet, der der Sitzung beigetreten ist. Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Name der Kategorie des Clients, den der Benutzer verwendet, der der Sitzung beigetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TargetUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Zielbenutzers der Sitzung.</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUriType</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Typ des URI des Zielbenutzers der Sitzung. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Benutzers, in dessen Namen die Sitzung gestartet worden ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnnnBehalfOfUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Typ des URI des Benutzers, in dessen Namen die Sitzung gestartet worden ist. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Mandant des Benutzers, in dessen Namen die Sitzung gestartet worden ist. Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Benutzers, der die Sitzung weitergeleitet hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Typ des URI des Benutzers, der die Sitzung weitergeleitet hat. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Mandant des Benutzers, der die Sitzung weitergeleitet hat. Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ID</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>SIP-Dialog-ID. Das Format lautet wie folgt:</p>
<p>Dialogfeld; from-Tag; to-Tag</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>GUID zum Korrelieren mehrerer Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Zeitpunkt des Dialogs, der durch die Sitzung ersetzt wurde. Wird in Verbindung mit ReplaceDialogIdSeq verwendet, um ein Dialogfeld eindeutig zu identifizieren, das durch die Sitzung ersetzt wird. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID zur Identifikation der Sitzung. Wird in Verbindung mit ReplaceDialogIdTime verwendet, um ein Dialogfeld eindeutig zu identifizieren, das durch die Sitzung ersetzt wird. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplacesDialogId</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>SIP-Dialog-ID, die durch die Sitzung ersetzt wird. Das Format lautet wie folgt:</p>
<p>Dialogfeld; from-Tag; to-Tag</p></td>
</tr>
<tr class="even">
<td><p><strong>Webantworten</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Zeitpunkt der Antwort auf die erste INVITE-Nachricht. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-Nr</strong></p></td>
<td><p>int</p></td>
<td><p>Diagnose-ID, die aus SIP-Headern erfasst wird.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Typ des Inhalts für die Sitzung.</p></td>
</tr>
<tr class="even">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Vollqualifizierter Domänenname des Front-End-Servers, der die Daten für die Sitzung erfasst hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Vollqualifizierter Domänenname des Pools, der die Daten für die Sitzung erfasst hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEdgeServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Vollqualifizierter Domänenname des Edgeservers, den der Benutzer verwendet, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToEdgeServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Vollqualifizierter Domänenname des Edgeservers, den der Benutzer verwendet, der der Sitzung beigetreten ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsFromInternal</strong></p></td>
<td><p>Bit</p></td>
<td><p>Gibt an, ob der Benutzer, der die Sitzung gestartet hat, über das interne Netzwerk angemeldet war.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsToInternal</strong></p></td>
<td><p>Bit</p></td>
<td><p>Gibt an, ob der Benutzer, der der Sitzung beigetreten ist, über das interne Netzwerk angemeldet war.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Anrufpriorität der Sitzung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat. Die folgenden Attributdefinitionen sind zulässig:</p>
<p>0x01 - Mit dem Desktoptelefon integriert</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat. Die folgenden Attributdefinitionen sind zulässig:</p>
<p>0x01 - Mit dem Desktoptelefon integriert</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Gibt die Anrufattribute an. Die folgenden Attributdefinitionen sind zulässig:</p>
<p>0x01 - Sitzung mit Wiederholungsversuch</p>
<p>0x02 - Ein vom Agent im Namen einer Reaktionsgruppe getätigter Anruf</p></td>
</tr>
<tr class="even">
<td><p><strong>Ort</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Standort des Notrufs.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

