---
title: 'Lync Server 2013: McuJoinsAndLeaves-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4f3f73606cfd05df17022770da7dcd1f5266b21
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a>McuJoinsAndLeaves-Ansicht in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Die McuJoinsAndLeaves-Ansicht speichert Informationen zum Beitreten und Verlassen von Benutzern für einen Konferenzserver. Jeder Datensatz in dieser Ansicht enthält Anrufdetails über eine Kombination aus einem Benutzer, der einer Konferenz beitritt oder sie verlässt, und einem Konferenzserver. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.


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
<td><p>Zeitpunkt der Konferenzinstanz. Wird zusammen mit SessionIdSeq verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID zur Identifikation der Konferenzinstanz. Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUri</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Der URI des Konferenzservers, mit dem sich der Benutzer verbunden hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Der URI des Konferenzservers, mit dem sich der Benutzer verbunden hat. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Der URI des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Der Typ des URIs des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Der Mandant des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden. Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Die Version des URIs des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Der Client, der vom Benutzer, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden, verwendet wurde. Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Der Name der Kategorie des Clients, der vom Benutzer, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden, verwendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>Identifiziert die Kombination aus Benutzer/Gerät für Benutzer, die gleichzeitig auf mehreren Geräten angemeldet sind, eindeutig.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserFromPstn</strong></p></td>
<td><p>Bit</p></td>
<td><p>Bitwert, der angibt, ob ein Benutzer ein interner Benutzer ist oder nicht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung. Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID zur Identifikation der Sitzung. Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ID</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>SIP-DialogID der Sitzung. Das Format lautet: dialog;from-tag;to-tag.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Zeitpunkt, zu dem der Benutzer dem Konferenzserver beigetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Zeitpunkt, zu dem der Benutzer den Konferenzserver verlassen hat.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

