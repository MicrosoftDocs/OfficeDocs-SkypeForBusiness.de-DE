---
title: 'Lync Server 2013: SessionDetails-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd3902fd35679366e905c04e99ff1e72b2ece86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a>SessionDetails-Ansicht in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

In der SessionDetails-Ansicht werden Informationen zu Peer-to-Peer-Sitzungen gespeichert, bei denen es sich um einen VoIP-VoIP-Anruf, eine Chatsitzung mit zwei Teilnehmern oder eine andere Art von Sitzung handeln kann. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.


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
<td><p>datetime</p></td>
<td><p>Uhrzeit der Sitzungsanforderung. Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der Tabelle <a href="lync-server-2013-dialogs-table.md">Dialogfelder in der lync Server 2013</a> -Tabelle.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Einladen</strong></p></td>
<td><p>datetime</p></td>
<td><p>Uhrzeit der ersten INVITE-Anforderung. Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info). Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Der URI des Benutzers, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Touri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Der URI des Benutzers, der der Sitzung beigetreten ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Typ des URIs des Benutzers, der die Sitzung gestartet hat. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Typ des URIs des Benutzers, der der Sitzung beigetreten ist. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Der Mandant des Benutzers, der die Sitzung gestartet hat. Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Mandant des Benutzers, der der Sitzung beigetreten ist. Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Eindeutiger Bezeichner des Endpunkts des Benutzers, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Endpunkt-Nr</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Eindeutiger Bezeichner des Endpunkts des Benutzers, der der Sitzung beigetreten ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Endzeit der Sitzung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMessageCount</strong></p></td>
<td><p>int</p></td>
<td><p>Die Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMessageCount</strong></p></td>
<td><p>int</p></td>
<td><p>Die Anzahl der Nachrichten, die von dem Benutzer gesendet wurden, der der Sitzung beigetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Die Version des Clients, die von dem Benutzer verwendet wird, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Der Client, der von dem Benutzer verwendet wird, der die Sitzung gestartet hat. Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Der Name der Kategorie des Clients, der vom Benutzer verwendet wird, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Die Version des Clients, die von dem Benutzer verwendet wird, der der Sitzung beigetreten ist</p></td>
</tr>
<tr class="odd">
<td><p><strong>Toclienttype</strong></p></td>
<td><p>int</p></td>
<td><p>Der Client, der von dem Benutzer verwendet wird, der der Sitzung beigetreten ist. Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Der Name der Kategorie des Clients, der von dem Benutzer verwendet wird, der der Sitzung beigetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TargetUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Der URI des Zielbenutzers der Sitzung.</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUriType</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Der Typ des URIs des Zielbenutzers für die Sitzung. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Der URI des Benutzers, in dessen Auftrag die Sitzung gestartet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnnnBehalfOfUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Typ des URIs des Benutzers, in dessen Auftrag die Sitzung gestartet wurde. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Mandant des Benutzers, dessen Namen für die Sitzung gestartet wurde. Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Der URI des Benutzers, der die Sitzung angewiesen hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Typ des URIs des Benutzers, der die Sitzung angewiesen hat. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Mandant des Benutzers, der die Sitzung angewiesen hat. Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Dialogfeld-Nr</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>SIP-Dialogfeld-ID. Das Format lautet:</p>
<p>Dialogfeld; from-Tag; to-Tag</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>GUID, die verwendet wird, um mehrere Sitzungen zu korrelieren.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Uhrzeit des Dialogs, der durch die Sitzung ersetzt wurde. Wird in Verbindung mit ReplaceDialogIdSeq verwendet, um ein durch die Sitzung Ersetztes Dialogfeld eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit ReplaceDialogIdTime verwendet, um ein durch die Sitzung Ersetztes Dialogfeld eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplacesDialogId</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>SIP-Dialog-ID, die die Sitzung ersetzt. Das Format lautet:</p>
<p>Dialogfeld; from-Tag; to-Tag</p></td>
</tr>
<tr class="even">
<td><p><strong>Webantworten</strong></p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt der Antwort auf die erste Einladungsnachricht. Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Response Code</strong></p></td>
<td><p>int</p></td>
<td><p>SIP-Antwortcode für die Sitzungseinladung Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-Nr</strong></p></td>
<td><p>int</p></td>
<td><p>Von SIP-Headern erfasste Diagnose-ID.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Typ des Inhalts für die Sitzung.</p></td>
</tr>
<tr class="even">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN des Front-End-Servers, der die Daten für die Sitzung erfasst hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der FQDN des Pools, in dem die Daten für die Sitzung erfasst wurden.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEdgeServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der FQDN des Edge-Servers, der vom Benutzer verwendet wird, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToEdgeServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN des Edge-Servers, der vom Benutzer verwendet wird, der die Sitzung gestartet hat</p></td>
</tr>
<tr class="even">
<td><p><strong>IsFromInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob der Benutzer, der die Sitzung gestartet hat, sich über das interne Netzwerk angemeldet hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsToInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob der Benutzer, der der Sitzung beigetreten ist, aus dem internen Netzwerk angemeldet ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Anrufpriorität der Sitzung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat. Die folgenden Attributdefinitionen sind zulässig:</p>
<p>0x01-integriert mit dem Desktoptelefon</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Gibt die Attribute des Benutzers an, der die Sitzung gestartet hat. Die folgenden Attributdefinitionen sind zulässig:</p>
<p>0x01-integriert mit dem Desktoptelefon</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Gibt die anrufattribute an. Die folgenden Attributdefinitionen sind zulässig:</p>
<p>0x01-wiederholte Sitzung</p>
<p>0x02 – ein Anruf, der von einem Agenten im Auftrag einer Reaktionsgruppe durchgeführt wurde</p></td>
</tr>
<tr class="even">
<td><p><strong>Standort</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Ort des Notrufs.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

