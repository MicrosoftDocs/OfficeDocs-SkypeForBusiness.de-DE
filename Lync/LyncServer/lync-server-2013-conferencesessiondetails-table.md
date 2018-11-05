---
title: 'Lync Server 2013: ConferenceSessionDetails-Tabelle'
TOCTitle: ConferenceSessionDetails-Tabelle
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412741(v=OCS.15)
ms:contentKeyID: 49294915
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ConferenceSessionDetails-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Jeder Datensatz steht für eine Konferenzsitzung, bei der es sich entweder um die Sitzung mit Konferenzzustandsobjekt oder die Sitzung mit einem spezifischen Konferenzserver handelt.


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
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung; wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenzsitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>ID zur Identifikation der Sitzung. Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Konferenzsitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Konferenz-URI mit Konferenzzustandsobjekt für diese Sitzung. Weitere Informationen finden Sie in der <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris-Tabelle in Lync Server 2013</a>. Dieser URI ist ein auf dem Konferenzzustandsobjekt basierter Konferenz-URI.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>ID, die Instanzen sich wiederholender Konferenzen voneinander unterscheidet. Alle wiederholt auftretenden Konferenzinstanzen haben denselben ConferenceURI- aber einen unterschiedlichen ConfInstance-Wert.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Konferenz-URI des Konferenzservers für diese Sitzung. Weitere Informationen finden Sie in der <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris-Tabelle in Lync Server 2013</a>. Dieser URI ist der konferenzserverbasierte Konferenz-URI. Bei Konferenzsitzungen mit Konferenzzustandsobjekt ist diese Spalte NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID eines Benutzers in der Konferenzsitzung. Weitere Informationen finden Sie in der <a href="lync-server-2013-users-table.md">Users-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>Eine GUID zur Identifikation der Instanz des Endpunkts. Wenn sich beispielsweise ein Benutzer auf verschiedenen Computern über dasselbe Konto anmeldet, erhält jeder Computer eine andere Endpunkt-ID.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Gibt die ID des Benutzers an, in dessen Namen der Anrufer Anrufe entgegennimmt. Weitere Informationen finden Sie in der <a href="lync-server-2013-users-table.md">Users-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID des Benutzers, von dem der Anruf durchgestellt wurde. Weitere Informationen finden Sie in der <a href="lync-server-2013-users-table.md">Users-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Clientversion, die vom Konferenzbenutzer verwendet wird. Weitere Informationen finden Sie in der <a href="lync-server-2013-clientversions-table.md">ClientVersions-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Clientversion, die vom Konferenzserver verwendet wird. Weitere Informationen finden Sie in der <a href="lync-server-2013-clientversions-table.md">ClientVersions-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Fremd</p></td>
<td><p>ID zur Identifikation des Dialogs, der durch die aktuelle Sitzung ersetzt wurde. Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID zur Identifikation der Sitzung. Wird zusammen mit <strong>ReplacesDialogIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren, die durch diese Sitzung ersetzt wurde. Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Zeigt an, ob die Sitzung durch den A/V-Konferenzserver gestartet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Zeigt an, ob die Sitzung durch den Konferenzserver beendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Tatsache, ob die Anmeldung des Benutzers intern erfolgte oder nicht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>SIP-Antwortcode (Session Initiation Protocol) auf die Sitzungseinladung. Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden. Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Diagnose-ID aus dem SIP-Header.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID des für diese Sitzung verwendeten Front-End-Servers. Weitere Informationen finden Sie in der <a href="lync-server-2013-servers-table.md">Servers-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID des Pools, in dem die Sitzung erfasst wurde. Weitere Informationen finden Sie in der <a href="lync-server-2013-pools-table.md">Pools-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der für den Anruf verwendete Vermittlungsserver. Weitere Informationen finden Sie in der <a href="lync-server-2013-mediationservers-table.md">MediationServers-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>GatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Das vom Anruf verwendete Gateway. Weitere Informationen finden Sie in der <a href="lync-server-2013-gateways-table.md">Gateways-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der vom Anruf verwendete Edgeserver. Weitere Informationen finden Sie in der <a href="lync-server-2013-edgeservers-table.md">EdgeServers-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>In der Sitzung verwendeter Inhaltstyp. Weitere Informationen finden Sie in der <a href="lync-server-2013-contenttypes-table.md">ContentTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Die Uhrzeit der ersten INVITE-Anforderung. Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden. Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Die Uhrzeit der ersten SIP RESPONSE. Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden. Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Der Zeitpunkt des Sitzungsendes.</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Fremd</p></td>
<td><p>Enthält den MCU URI-Typwert aus der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>. Dieses Feld dient zur Verbesserung der Abfrageleistung.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Ein Bitsatz, der die Benutzerattribute angibt. Die folgenden Attributdefinitionen werden aufgeführt:</p>
<ul>
<li><p>Integrated with desktop phone - 1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Ein Bitsatz, der die Anrufattribute angibt. Die folgenden Attributdefinitionen werden aufgeführt:</p>
<ul>
<li><p>Retried Session - 1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\*Bei den meisten Sitzungen weist **SessionIdSeq** den Wert 1 auf. Wenn mehrere Sitzungen genau zur selben Zeit gestartet werden, ist **SessionIdSeq** für die eine Sitzung 1, für die andere Sitzung 2 usw.

