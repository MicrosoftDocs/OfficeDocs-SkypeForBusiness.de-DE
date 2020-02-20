---
title: 'Lync Server 2013: SessionDetails-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b27721923e265bbb687b5df42b32e0fb6f25e92e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a>SessionDetails-Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Jeder Eintrag steht für eine Peer-zu-Peer-Sitzung, die ein Telefonanruf von VoIP zu VoIP, eine Sofortnachrichtensitzung mit zwei Teilnehmern oder eine andere Art von Sitzung sein kann. Sie können einen Tabellen Beitritt mit der [Medientabelle in lync Server 2013](lync-server-2013-media-table.md) durchführen, um die Details der einzelnen Medien zu finden, die an dieser Sitzung beteiligt sind.

Beachten Sie, dass die Felder IsUser1IntegratedWithDeskPhone und IsUser2IntegratedWithDeskPhone aus der SessionDetails-Tabelle gelöscht wurden, die in Microsoft lync Server 2013 verwendet wurde.


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
<td><p><strong>SessionID</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung. Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>ID zur Identifikation der Sitzung. Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. * Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td></td>
<td><p>Ein GUID für die Korrelation mehrerer Sitzungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Fremd</p></td>
<td><p>ID zur Identifikation des Dialogs, der durch die aktuelle Sitzung ersetzt wurde. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID zur Identifikation der Sitzung. Wird zusammen mit <strong>ReplacesDialogIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren, die durch diese Sitzung ersetzt wurde. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User1</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID eines Benutzers in der Sitzung. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2Id</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID des anderen Benutzers in der Sitzung. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User1EndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>GUID, die den Endpunkt angibt, der vom ersten Benutzer in der Sitzung verwendet wird.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2EndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>GUID, die den Endpunkt angibt, der vom zweiten Benutzer in der Sitzung verwendet wird.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der ursprüngliche „An Benutzer“-URI in der SIP-Anforderung. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionStartedById</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID des Benutzers, der die Sitzung gestartet hat. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Gibt die ID des Benutzers an, der durch den Anrufer vertreten wird. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID des Benutzers, der den Anruf weiterleitet. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerID</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID des für diese Sitzung verwendeten Front-End-Servers. Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool-Nr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID des Pools, in dem die Sitzung erfasst wurde. Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeID</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>In der Sitzung verwendeter Inhaltstyp. Weitere Informationen finden Sie <a href="lync-server-2013-contenttypes-table.md">in der ContentTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Von Benutzer1 verwendete Clientversion. Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User2ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Von Benutzer2 verwendete Clientversion. Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Von Benutzer1 verwendeter Edgeserver. Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User2EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Von Benutzer2 verwendeter Edgeserver. Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUser1Internal</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Gibt an, ob Benutzer1 ein interner oder externer Benutzer ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUser2Internal</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Gibt an, ob Benutzer2 ein interner oder externer Benutzer ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Invitezeit</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td></td>
<td><p>Die Uhrzeit der ersten INVITE-Anforderung. Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt. Dieses Feld wird normalerweise von Daten aufgefüllt, die von der ursprünglichen INVITE-Nachricht in der Sitzung generiert werden. Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>Webantworten</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td></td>
<td><p>Die Zeit bis zur Antwort auf die erste INVITE-Anforderung. Dieses Feld wird normalerweise von Daten aufgefüllt, die von der ursprünglichen INVITE-Nachricht in der Sitzung generiert werden. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-Nr</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Vom SIP-Header erfasste Diagnose-ID.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallPriority</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Anrufpriorität. Weitere Informationen finden Sie <a href="lync-server-2013-callpriorities-table.md">in der CallPriorities-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User1MessageCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Anzahl der von Benutzer1 während der Sitzung gesendeten Nachrichten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2MessageCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Anzahl der von Benutzer2 während der Sitzung gesendeten Nachrichten.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td></td>
<td><p>Uhrzeit am Ende der Sitzung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Mediatypes zu bestimmen</strong></p></td>
<td><p>int</p></td>
<td></td>
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
<td><p>Chat</p></td>
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
<td><p>8 </p></td>
</tr>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>16 </p></td>
</tr>
<tr class="even">
<td><p>Video</p></td>
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
<td></td>
<td><p>Ein Bit-Satz, der die Attribute von Benutzer1 angibt. Die Definitionen folgender Typen sind aufgeführt:</p>
<ul>
<li><p>0x01 – Mit Desktoptelefon integriert</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>User2Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Ein Bit-Satz, der die Attribute von Benutzer2 angibt. Die Definitionen folgender Typen sind aufgeführt:</p>
<ul>
<li><p>0x01 – Mit Desktoptelefon integriert</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Ein Bit-Satz, der die Anrufattribute angibt. Die Definitionen folgender Attribute sind aufgeführt:</p>
<ul>
<li><p>0x01 – Wiederholungsversuch der Sitzung</p></li>
<li><p>0x02 – Von Agent getätigter Anruf im Namen einer Reaktionsgruppe</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Verarbeitet</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Für die interne Verwendung durch den Überwachungsdienst.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>


\*Für die meisten Sitzungen wird SessionIdSeq den Wert 1 haben. Wenn mehrere Sitzungen zum selben Zeitpunkt gestart werden, lautet der Wert für eine Sitzung 1, für eine weitere Sitzung 2, usw.

</div>

<span> </span>

</div>

</div>

</div>

