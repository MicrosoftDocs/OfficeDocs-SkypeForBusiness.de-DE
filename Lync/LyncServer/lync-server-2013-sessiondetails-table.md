---
title: 'Lync Server 2013: SessionDetails-Tabelle'
TOCTitle: SessionDetails-Tabelle
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398589(v=OCS.15)
ms:contentKeyID: 49294447
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# SessionDetails-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Jeder Eintrag steht für eine Peer-zu-Peer-Sitzung, die ein Telefonanruf von VoIP zu VoIP, eine Sofortnachrichtensitzung mit zwei Teilnehmern oder eine andere Art von Sitzung sein kann. Sie können eine Tabellenverbindung mit [Media-Tabelle in Lync Server 2013](lync-server-2013-media-table.md) durchführen, um Details zu allen in dieser Sitzung verwendeten Medien anzuzeigen.

Beachten Sie, dass die Felder „IsUser1IntegratedWithDeskPhone“ und „IsUser2IntegratedWithDeskPhone“ aus der in Microsoft Lync Server 2013 verwendeten Tabelle „SessionDetails“ entfernt wurden.


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
<td><p>datetime</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung. Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>ID zur Identifikation der Sitzung. Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.* Weitere Informationen finden Sie unter <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>Ein GUID für die Korrelation mehrerer Sitzungen.</p></td>
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
<td><p><strong>User1Id</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID eines Benutzers in der Sitzung. Weitere Informationen finden Sie unter <a href="lync-server-2013-users-table.md">Users-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2Id</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID des anderen Benutzers in der Sitzung. Weitere Informationen finden Sie unter <a href="lync-server-2013-users-table.md">Users-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>User1EndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>GUID, die den Endpunkt angibt, der vom ersten Benutzer in der Sitzung verwendet wird.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2EndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>GUID, die den Endpunkt angibt, der vom zweiten Benutzer in der Sitzung verwendet wird.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der ursprüngliche „An Benutzer“-URI in der SIP-Anforderung. Weitere Informationen finden Sie unter <a href="lync-server-2013-users-table.md">Users-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionStartedById</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID des Benutzers, der die Sitzung gestartet hat. Weitere Informationen finden Sie unter <a href="lync-server-2013-users-table.md">Users-Tabelle in Lync Server 2013</a>.</p></td>
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
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID des für diese Sitzung verwendeten Front-End-Servers. Weitere Informationen finden Sie in der <a href="lync-server-2013-servers-table.md">Servers-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID des Pools, in dem die Sitzung erfasst wurde. Weitere Informationen finden Sie in der <a href="lync-server-2013-pools-table.md">Pools-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeID</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>In der Sitzung verwendeter Inhaltstyp. Weitere Informationen finden Sie in der <a href="lync-server-2013-contenttypes-table.md">ContentTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Von Benutzer1 verwendete Clientversion. Weitere Informationen finden Sie unter <a href="lync-server-2013-clientversions-table.md">ClientVersions-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>User2ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Von Benutzer2 verwendete Clientversion. Weitere Informationen finden Sie unter <a href="lync-server-2013-clientversions-table.md">ClientVersions-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Von Benutzer1 verwendeter Edgeserver. Weitere Informationen finden Sie unter <a href="lync-server-2013-edgeservers-table.md">EdgeServers-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>User2EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Von Benutzer2 verwendeter Edgeserver. Weitere Informationen finden Sie unter <a href="lync-server-2013-edgeservers-table.md">EdgeServers-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUser1Internal</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Gibt an, ob Benutzer1 ein interner oder externer Benutzer ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUser2Internal</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Gibt an, ob Benutzer2 ein interner oder externer Benutzer ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Der Zeitpunkt der ersten INVITE-Anforderung. Dieses Feld wird normalerweise von Daten aufgefüllt, die von der urspünglichen INVITE-Nachricht in der Sitzung generiert werden. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Die Zeit bis zur Antwort auf die erste INVITE-Anforderung. Dieses Feld wird normalerweise von Daten aufgefüllt, die von der ursprünglichen INVITE-Nachricht in der Sitzung generiert werden. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Diagnose-ID aus dem SIP-Header.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallPriority</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Anrufpriorität. Weitere Informationen finden Sie unter <a href="lync-server-2013-callpriorities-table.md">CallPriorities-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>User1MessageCount</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Anzahl der von Benutzer1 während der Sitzung gesendeten Nachrichten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2MessageCount</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Anzahl der von Benutzer2 während der Sitzung gesendeten Nachrichten.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Uhrzeit am Ende der Sitzung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaTypes</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Ein Bit-Satz, der den Medientyp dieser Sitzung angibt. Die Definitionen folgender Typen sind aufgeführt:</p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Instant Messaging</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>FILE_TRANSFER</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>REMOTE_ASSISTANCE</p></td>
<td><p>4</p></td>
</tr>
<tr class="even">
<td><p>APP_SHARING</p></td>
<td><p>8</p></td>
</tr>
<tr class="odd">
<td><p>AUDIO</p></td>
<td><p>16</p></td>
</tr>
<tr class="even">
<td><p>VIDEO</p></td>
<td><p>32</p></td>
</tr>
<tr class="odd">
<td><p>APP_INVITE</p></td>
<td><p>64</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>User1Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Ein Bit-Satz, der die Attribute von Benutzer1 angibt. Die Definitionen folgender Typen sind aufgeführt:</p>
<ul>
<li><p>0x01 - Mit dem Desktoptelefon integriert</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>User2Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Ein Bit-Satz, der die Attribute von Benutzer2 angibt. Die Definitionen folgender Typen sind aufgeführt:</p>
<ul>
<li><p>0x01 - Mit dem Desktoptelefon integriert</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Ein Bitsatz, der die Anrufattribute angibt. Die folgenden Attributdefinitionen werden aufgeführt:</p>
<ul>
<li><p>0x01 - Sitzung mit Wiederholungsversuch</p></li>
<li><p>0x02 - Von Agent getätigter Anruf im Namen einer Reaktionsgruppe</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Processed</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Für die interne Verwendung durch den Überwachungsdienst.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>


\*Bei den meisten Sitzungen weist **SessionIdSeq** den Wert 1 auf. Wenn mehrere Sitzungen genau zur selben Zeit gestartet werden, ist **SessionIdSeq** für die eine Sitzung 1, für die andere Sitzung 2 usw.

