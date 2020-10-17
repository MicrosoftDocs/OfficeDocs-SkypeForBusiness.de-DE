---
title: 'Lync Server 2013: ConferenceSessionDetails-Tabelle'
description: 'Lync Server 2013: ConferenceSessionDetails-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d101eb1607e366ab814e60acaeee80820fe87c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566781"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a>ConferenceSessionDetails-Tabelle in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

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
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionID</strong></p></td>
<td><p>DateTime</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung; wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenzsitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>ID zur Identifikation der Sitzung. Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Konferenzsitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> . *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Konferenz-URI mit Konferenzzustandsobjekt für diese Sitzung. Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> . Dieser URI ist ein auf dem Konferenzzustandsobjekt basierter Konferenz-URI.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>ID, die Instanzen sich wiederholender Konferenzen voneinander unterscheidet. Jede wiederkehrende Konferenz weist denselben ConferenceURI, jedoch einen eigenen ConfInstance-Wert auf.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Konferenz-URI des Konferenzservers für diese Sitzung. Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> . Dieser URI ist der konferenzserverbasierte Konferenz-URI. Bei Konferenzsitzungen mit Konferenzzustandsobjekt ist diese Spalte NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID eines Benutzers in der Konferenzsitzung. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td></td>
<td><p>Eine GUID zur Identifikation der Instanz des Endpunkts. Wenn sich beispielsweise ein Benutzer auf verschiedenen Computern über dasselbe Konto anmeldet, erhält jeder Computer eine andere Endpunkt-ID.</p></td>
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
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Clientversion, die vom Konferenzbenutzer verwendet wird. Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Clientversion, die vom Konferenzserver verwendet wird. Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</p></td>
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
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Zeigt an, ob die Sitzung durch den A/V-Konferenzserver gestartet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Zeigt an, ob die Sitzung durch den Konferenzserver beendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Tatsache, ob die Anmeldung des Benutzers intern erfolgte oder nicht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>SIP-Antwortcode (Session Initiation Protocol) auf die Sitzungseinladung. Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit Datum und Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-Nr</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Diagnose-ID aus dem SIP-Header.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerID</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID des für diese Sitzung verwendeten Front-End-Servers. Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool-Nr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID des Pools, in dem die Sitzung erfasst wurde. Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der für den Anruf verwendete Vermittlungsserver. Weitere Informationen finden Sie <a href="lync-server-2013-mediationservers-table.md">in der MediationServers-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Gatewayserver</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Das vom Anruf verwendete Gateway. Weitere Informationen finden Sie <a href="lync-server-2013-gateways-table.md">in der Tabelle Gateways in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der vom Anruf verwendete Edgeserver. Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>In der Sitzung verwendeter Inhaltstyp. Weitere Informationen finden Sie <a href="lync-server-2013-contenttypes-table.md">in der ContentTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Invitezeit</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td></td>
<td><p>Die Uhrzeit der ersten INVITE-Anforderung. Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden. Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>Webantworten</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td></td>
<td><p>Die Uhrzeit der ersten SIP RESPONSE. Dieses Feld wird in der Regel durch Daten gefüllt, die aus der ersten INVITE-Nachricht in der Sitzung erzeugt werden. Falls keine INVITE-Nachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (BYE, CANCEL, MESSAGE oder INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td></td>
<td><p>Der Zeitpunkt des Sitzungsendes.</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Fremd</p></td>
<td><p>Enthält den MCU-URI-Typ-Wert aus der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in lync Server 2013</a>. Dieses Feld dient zur Verbesserung der Abfrageleistung.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Ein Bitsatz, der die Benutzerattribute angibt. Die folgenden Attributdefinitionen werden aufgeführt:</p>
<ul>
<li><p>Integrated with desktop phone - 1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Ein Bitsatz, der die Anrufattribute angibt. Die folgenden Attributdefinitionen werden aufgeführt:</p>
<ul>
<li><p>Retried Session - 1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\* Für die meisten Sitzungen wird SessionIdSeq den Wert 1 haben. Wenn mehrere Sitzungen zum selben Zeitpunkt gestart werden, lautet der Wert für eine Sitzung 1, für eine weitere Sitzung 2, usw.

</div>

<span> </span>

</div>

</div>

</div>

