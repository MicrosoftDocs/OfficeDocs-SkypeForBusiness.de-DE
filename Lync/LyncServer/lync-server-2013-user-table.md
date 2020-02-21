---
title: 'Lync Server 2013: user-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f3ea921981726ad1865741a1e8e37f82f8ac125
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a>Benutzertabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

Bei der User-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin wird eine Liste der verschiedenen Benutzer gespeichert, die an in der Datenbank aufgezeichneten Sitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Benutzer.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Spalte</strong></th>
<th><strong>Datentyp</strong></th>
<th><strong>Schlüssel/Index</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diesen Benutzer identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>uri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Eigen</p></td>
<td><p>URI-Zeichenfolge</p></td>
</tr>
<tr class="odd">
<td><p><strong>URI</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>1 ist ein unbekannter URI-Typ.</p>
<p>2 ist ein Benutzer-URI.</p>
<p>4 ist ein Konferenz-URI.</p>
<p>8 ist ein Telefon-URI.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Mandant des Benutzers. Verweis von der tenant-Tabelle.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastPoorCallTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td></td>
<td><p>Letzter Zeitstempel, an dem der Benutzer einen Anruf mit schlechter Audioqualität geführt hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

