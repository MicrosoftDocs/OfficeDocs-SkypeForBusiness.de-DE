---
title: 'Lync Server 2013: McuJoinsAndLeaves-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae21b9a8ec2107d8a2bd0a99f1e21d6f182a830e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a>McuJoinsAndLeaves-Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Kombination aus einem Benutzer-Join oder-Leave und dem Konferenzserver. Wenn ein Benutzer beispielsweise einer Konferenz beitreten, die Webkonferenzen und Audio/Video-Elemente umfasst, wird ein Datensatz für den Webkonferenz Beitritt dieses Benutzers erstellt, und es wird ein anderer Datensatz für die Teilnahme an Audio/Videokonferenzen des Benutzers erstellt.


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
<td><p>Zeitpunkt der Konferenzinstanz. Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>ID zur Identifikation der Konferenzinstanz. Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-conferences-table.md">in der Tabelle "Konferenzen" in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>Eindeutige Zahl, die diesen Benutzer identifiziert. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Wenn ein Benutzer auf mehreren Computern oder Geräten gleichzeitig angemeldet ist, identifiziert McuUserInstance die Benutzer/Geräte-Kombination eindeutig.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsFromPstn</strong></p></td>
<td><p>Bit</p></td>
<td><p> </p></td>
<td><p>Gibt an, ob der Benutzer von einem PSTN Beitritt oder nicht.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>Eindeutige Zahl, die diesen Konferenzserver identifiziert. Weitere Informationen finden Sie <a href="lync-server-2013-mcus-table.md">in der Tabelle "MCU" in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Fremd</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung. Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID zur Identifikation der Sitzung. Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p> </p></td>
<td><p>Die Zeit, zu der dieser Benutzer diesem Konferenzserver Beitritt.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p> </p></td>
<td><p>Die Zeit, die dieser Benutzer diesen Konferenzserver verlässt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Bezeichner, der die Versionsnummer der Client Software angibt, die in der Konferenz verwendet wird. Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

