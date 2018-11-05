---
title: SessionDetails-Ansicht
TOCTitle: SessionDetails-Ansicht
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49890995
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# SessionDetails-Ansicht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der Ansicht **SessionDetails** werden Informationen über Peer-to-Peer-Sitzungen gespeichert, z.\&nbsp;B. ein VoIP-VoIP-Telefongespräch, eine Sofortnachrichtensitzung mit zwei Teilnehmern oder ein anderer Sitzungstyp. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung. Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der Tabelle <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID zur Identifizierung der Sitzung. Wird in Verbindung mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt der ersten INVITE-Anforderung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Benutzers, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Benutzers, der der Sitzung beigetreten ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Typ des URI des Benutzers, der die Sitzung gestartet hat. Weitere Informationen finden Sie in der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Typ des URI des Benutzers, der der Sitzung beigetreten ist. Weitere Informationen finden Sie in der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Mandant des Benutzers, der die Sitzung gestartet hat. Weitere Informationen finden Sie in der <a href="lync-server-2013-tenants-table.md">Tenants-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Mandant des Benutzers, der der Sitzung beigetreten ist. Weitere Informationen finden Sie in der <a href="lync-server-2013-tenants-table.md">Tenants-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Eindeutiger Bezeichner des Endpunkts des Benutzers, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Eindeutiger Bezeichner des Endpunkts des Benutzers, der der Sitzung beigetreten ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
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
<td><p>Client, den der Benutzer verwendet, der die Sitzung gestartet hat. Ausführliche Informationen finden Sie in der <a href="lync-server-2013-useragentdef-table.md">UserAgentDef-Tabelle</a>.</p></td>
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
<td><p><strong>ToClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Client, den der Benutzer verwendet, der der Sitzung beigetreten ist. Ausführliche Informationen finden Sie in der <a href="lync-server-2013-useragentdef-table.md">UserAgentDef-Tabelle</a>.</p></td>
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
<td><p>Typ des URI des Zielbenutzers der Sitzung. Weitere Informationen finden Sie in der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Benutzers, in dessen Namen die Sitzung gestartet worden ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnnnBehalfOfUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Typ des URI des Benutzers, in dessen Namen die Sitzung gestartet worden ist. Weitere Informationen finden Sie in der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Mandant des Benutzers, in dessen Namen die Sitzung gestartet worden ist. Weitere Informationen finden Sie in der <a href="lync-server-2013-tenants-table.md">Tenants-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Benutzers, der die Sitzung weitergeleitet hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Typ des URI des Benutzers, der die Sitzung weitergeleitet hat. Weitere Informationen finden Sie in der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Mandant des Benutzers, der die Sitzung weitergeleitet hat. Weitere Informationen finden Sie in der <a href="lync-server-2013-tenants-table.md">Tenants-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar(775)</p></td>
<td><p>SIP-Dialog-ID. Das Format lautet wie folgt:</p>
<p><strong>dialog;from-tag;to-tag</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>GUID zum Korrelieren mehrerer Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt des Dialogs, der durch die Sitzung ersetzt worden ist. Wird in Verbindung mit <strong>ReplaceDialogIdSeq</strong> verwendet, um einen durch die Sitzung ersetzten Dialog eindeutig zu identifizieren. Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID zur Identifizierung der Sitzung. Wird in Verbindung mit <strong>ReplaceDialogIdTime</strong> verwendet, um einen durch die Sitzung ersetzten Dialog eindeutig zu identifizieren. Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplacesDialogId</strong></p></td>
<td><p>varchar(775)</p></td>
<td><p>SIP-Dialog-ID, die durch die Sitzung ersetzt wird. Das Format lautet wie folgt:</p>
<p><strong>dialog;from-tag;to-tag</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt der Antwort auf die erste INVITE-Nachricht. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
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
<td><p>bit</p></td>
<td><p>Gibt an, ob der Benutzer, der die Sitzung gestartet hat, über das interne Netzwerk angemeldet war.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsToInternal</strong></p></td>
<td><p>bit</p></td>
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
<td><p><strong>Location</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>Standort des Notrufs.</p></td>
</tr>
</tbody>
</table>

