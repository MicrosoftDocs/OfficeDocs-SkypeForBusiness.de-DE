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
ms.openlocfilehash: b68c50fc17199c68a69c5a7c6dd6abc8a5bd1dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a>SessionDetails-Tabelle in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Jeder Datensatz stellt eine Peer-to-Peer-Sitzung dar, bei der es sich um einen VoIP-VoIP-Telefonanruf, eine Chatsitzung mit zwei Teilnehmern oder eine andere Art von Sitzung handeln kann. Sie können eine Tabellen Verknüpfung mit der [Medientabelle in lync Server 2013](lync-server-2013-media-table.md) ausführen, um die Details der einzelnen Medien zu finden, die an dieser Sitzung beteiligt sind.

Beachten Sie, dass die IsUser1IntegratedWithDeskPhone-und IsUser2IntegratedWithDeskPhone-Felder aus der SessionDetails-Tabelle gelöscht wurden, die in Microsoft lync Server 2013 verwendet wurde.


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
<td><p>datetime</p></td>
<td><p>Primär, fremd</p></td>
<td><p>Uhrzeit der Sitzungsanforderung. Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, fremd</p></td>
<td><p>Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Sitzung eindeutig zu identifizieren. * Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td></td>
<td><p>Eine GUID zum Korrelieren mehrerer Sitzungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID-Nummer, die das Dialogfeld identifiziert, das durch die aktuelle Sitzung ersetzt wurde. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit <strong>ReplacesDialogIdTime</strong> verwendet, um eine Sitzung, die durch diese Sitzung ersetzt wird, eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Benutzer1</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID eines Benutzers in der Sitzung. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2Id</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID des anderen Benutzers in der Sitzung. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User1EndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>GUID, die den vom ersten Benutzer in der Sitzung verwendeten Endpunkt identifiziert.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2EndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>GUID, die den vom zweiten Benutzer in der Sitzung verwendeten Endpunkt identifiziert.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Das Original für Benutzer-URI in der SIP-Anforderung. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionStartedById</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID des Benutzers, der die Sitzung gestartet hat. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Gibt die ID des Benutzers an, der der Anrufer im Auftrag ist. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID des Benutzers, auf den der Anruf verweist. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerID</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID des für diese Sitzung verwendeten Front-End-Servers. Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool-Nr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID des Pools, in dem die Sitzung erfasst wurde. Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeID</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Inhaltstyp, der in der Sitzung verwendet wird. Weitere Informationen finden Sie <a href="lync-server-2013-contenttypes-table.md">in der Tabelle "ContentTypes" in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Von Benutzer1 verwendete Client Version. Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der ClientVersions-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User2ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Von User2 verwendete Client Version. Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der ClientVersions-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Von Benutzer1 verwendeter Edgeserver Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User2EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Von User2 verwendeter Edgeserver. Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUser1Internal</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Gibt an, ob Benutzer1 intern angemeldet ist oder nicht.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUser2Internal</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Gibt an, ob User2 intern angemeldet ist oder nicht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Einladen</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Der Zeitpunkt der ersten INVITE-Anforderung. Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info). Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</p></td>
</tr>
<tr class="even">
<td><p><strong>Webantworten</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Der Zeitpunkt der Antwort auf die erste Einladungsnachricht. Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Response Code</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>SIP-Antwortcode für die Sitzungseinladung Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden. Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</p></td>
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
<td><p>Die Anzahl der Nachrichten, die von Benutzer1 während der Sitzung gesendet wurden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2MessageCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Die Anzahl der Nachrichten, die von User2 während der Sitzung gesendet wurden.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Uhrzeit am Ende der Sitzung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaTypes</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ein Bit-Satz, der den Medientyp dieser Sitzung angibt. Aufgelistet sind die Definitionen der Typen:</p>
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
<td><p>8</p></td>
</tr>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>16</p></td>
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
<td><p>Ein Bit-Satz, der die Benutzer1-Attribute angibt. Die folgenden Attributdefinitionen werden aufgelistet:</p>
<ul>
<li><p>0x01-integriert mit dem Desktoptelefon</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>User2Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Ein Bit-Satz, der die User2-Attribute angibt. Die folgenden Attributdefinitionen werden aufgelistet:</p>
<ul>
<li><p>0x01-integriert mit dem Desktoptelefon</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Ein Bit-Satz, der die anrufattribute angibt. Die folgenden Attributdefinitionen werden aufgelistet:</p>
<ul>
<li><p>0x01-wiederholte Sitzung</p></li>
<li><p>0x02 – ein Anruf, der von einem Agenten im Auftrag einer Reaktionsgruppe durchgeführt wurde</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Verarbeitet</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Für die interne Verwendung durch den Überwachungsdienst.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>


\*Bei den meisten Sitzungen erhält SessionIdSeq den Wert 1. Wenn mehrere Sitzungen genau zur gleichen Zeit beginnen, ist der SessionIdSeq für einen 1, für einen anderen wird 2 usw.

</div>

<span> </span>

</div>

</div>

</div>

