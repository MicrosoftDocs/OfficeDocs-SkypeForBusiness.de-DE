---
title: ConferenceSessionDetails-Ansicht
TOCTitle: ConferenceSessionDetails-Ansicht
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49890756
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ConferenceSessionDetails-Ansicht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der ConferenceSessionDetails-Ansicht werden Informationen über Sitzungen mit mehreren Teilnehmern gespeichert. Jeder Datensatz steht für eine Konferenzsitzung. Dabei kann es sich um die Sitzung mit Konferenzzustandsobjekt oder um die Sitzung mit einem bestimmten Konferenzserver handeln. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.


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
<td><p>Zeitpunkt der Sitzungsanforderung. Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen erhalten Sie unter <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Die ID zur Identifizierung der Sitzung. Wird zusammen mit SessionIdTime verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen erhalten Sie unter <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Der Zeitpunkt der ersten INVITE-Anforderung. Dieses Feld wird i. d. R. mit Daten aus der ersten INVITE-Nachricht in der Sitzung gefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) gefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>Die URI der Konferenz.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Typ der Konferenz-URI. Weitere Informationen finden Sie unter <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>ID zur Unterscheidung zwischen einzelnen Instanzen wiederkehrender Konferenzen. Jede wiederkehrende Konferenz weist denselben ConferenceURI, jedoch einen eigenen ConfInstance-Wert auf.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>Der URI des Konferenz-Servers.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Typ der Konferenz-Server-URIs. Weitere Informationen finden Sie unter <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>Der URI des Benutzers aus der Sitzung.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der URI-Typ des Benutzers aus der Sitzung. Weitere Informationen finden Sie unter <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Mandant des Benutzers aus der Sitzung. Weitere Informationen finden Sie unter <a href="lync-server-2013-tenants-table.md">Tenants-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Die eindeutige ID des Benutzers aus der Sitzung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Die Endzeit der Sitzung.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Die Version des Konferenzservers.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Der Typ des Konferenzservers. Weitere Informationen finden Sie unter <a href="lync-server-2013-useragentdef-table.md">UserAgentDef-Tabelle</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Die Kategorie des Konferenzservers.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Die Version des Clients für den Benutzer aus der Sitzung.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Der Client des Benutzers aus der Sitzung. Weitere Informationen finden Sie unter <a href="lync-server-2013-useragentdef-table.md">UserAgentDef-Tabelle</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Der Name der Kategorie für den Client des Benutzers aus der Sitzung.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>Der URI des Benutzers, in dessen Namen die Sitzung gestartet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Typ des URI für den Benutzer, in dessen Namen die Sitzung gestartet wurde. Weitere Informationen finden Sie unter <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Mandant des Benutzers, in dessen Namen die Sitzung gestartet wurde. Weitere Informationen finden Sie unter <a href="lync-server-2013-tenants-table.md">Tenants-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>Der URI des Benutzers, der auf die die Sitzung verwiesen hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Typ des URI für den Benutzer, der auf die Sitzung verwiesen hat. Weitere Informationen finden Sie unter <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUriTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Mandant des Benutzers, der auf die Sitzung verwiesen hat. Weitere Informationen finden Sie unter <a href="lync-server-2013-tenants-table.md">Tenants-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring(775)</p></td>
<td><p>Die ID des SIP-Dialogs im Format</p>
<p>:dialog;from-tag;to-tag</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Die ID-Nummer zum Identifizieren des Dialogs, der durch die aktuelle Sitzung ersetzt wurde. Weitere Informationen finden Sie unter <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Die ID zur Identifizierung der Sitzung. Wird zusammen mit ReplaceDialogIdTime verwendet, um eine Sitzung eindeutig zu identifizieren, die durch diese Sitzung ersetzt wurde. Weitere Informationen finden Sie unter <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplacesDialogId</strong></p></td>
<td><p>varchar(775)</p></td>
<td><p>Die ID des SIP-Dialogs, der durch die Sitzung ersetzt wird im Format:</p>
<p>dialog;from-tag;to-tag</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob die Sitzung vom Konferenzserver gestartet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob die Sitzung vom Konferenzserver beendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob sich der Benutzer aus dem internen Netzwerk angemeldet hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Der Zeitpunkt der Antwort auf die erste INVITE-Nachricht. Dieses Feld wird i. d. R. mit Daten aus der ersten INVITE-Nachricht in der Sitzung gefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) gefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Der SIP-Antwortcode für die Sitzungseinladung. Dieses Feld wird i. d. R. mit Daten aus der ersten INVITE-Nachricht in der Sitzung gefüllt. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) gefüllt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>Die Diagnose-ID aus den SIP-Sitzungsheadern.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Inhaltstyp der Sitzung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der FQDN des Front-End-Servers, der die Daten für die Sitzung erfasst hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der FQDN des Pools, der die Daten für die Sitzung erfasst hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Vermittlungsserver, der vom Benutzer aus der Sitzung verwendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gateway</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Das Gateway, das vom Benutzer aus der Sitzung verwendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der FQDN des Edge-Servers, der vom Benutzer aus der Sitzung verwendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Gibt die Attribute des Benutzers aus der Sitzung an. Folgende Attributdefinitionen sind zulässig:</p>
<p>0x01 - Integriert in Standardtelefon</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Gibt die Anrufattribute an. Folgende Attributdefinitionen sind zulässig:</p>
<p>0x01 - Retried Session0</p>
<p>x02 - Von Agent getätigter Anruf im Namen einer Reaktionsgruppe</p></td>
</tr>
</tbody>
</table>

