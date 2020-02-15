---
title: 'Lync Server 2013: Tabelle "Konferenzen"'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 218879c8e2c64178fc140d46199529f86ec7dc31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a>Konferenz Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Jeder Datensatz in dieser Tabelle enthält Anrufdetails zu einer Konferenz.


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
<td><p>Primary</p></td>
<td><p>Zeitpunkt, zu dem die Konferenzanforderung vom KDS-Agent erfasst wurde. Wird nur als Primärschlüssel verwendet, um eine Konferenz Instanz eindeutig zu identifizieren.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>ID zur Identifikation der Sitzung. Wird in Verbindung mit <strong>SessionID</strong> verwendet, um eine Konferenz Instanz eindeutig zu identifizieren. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Konferenz-URI Weitere Informationen finden Sie <a href="lync-server-2013-conferenceuris-table.md">in der ConferenceUris-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p> </p></td>
<td><p>Nützlich für wiederkehrende Konferenzen; jede Instanz einer wiederkehrenden Konferenz hat dieselbe <strong>ConferenceUri</strong>, jedoch eine andere <strong>ConfInstance</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p> </p></td>
<td><p>Startzeit der Konferenz.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p> </p></td>
<td><p>Startzeit der Konferenz.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool-Nr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID-Nummer zum Identifizieren des Pools, in dem die Konferenz erfasst wurde. Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizer-Nr</strong></p></td>
<td><p>Int</p></td>
<td><p>Fremd</p></td>
<td><p>ID-Nummer zum Identifizieren des Organisator-URI dieser Konferenz. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Wert</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Eine Bitmaske, die Konferenz Attribute enthält. Die folgenden Werte sind möglich:</p>
<ul>
<li><p>0X01</p></li>
<li><p>Synthetischen</p></li>
<li><p>Transaktion</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Verarbeitet</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Internes Feld, das vom Überwachungsdienst verwendet wird.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>


\*Für die meisten Sitzungen wird SessionIdSeq den Wert 1 haben. Wenn zwei Sitzungen genau zur gleichen Zeit beginnen, ist der SessionIdSeq für einen 1, und für den anderen werden 2 usw.

</div>

<span> </span>

</div>

</div>

</div>

