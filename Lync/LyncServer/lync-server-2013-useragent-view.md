---
title: 'Lync Server 2013: UserAgent-Ansicht'
description: 'Lync Server 2013: UserAgent-Ansicht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9fc5ef2ec01b50f3714dca3690d0844286baaef5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558861"
---
# <a name="useragent-view-in-lync-server-2013"></a>UserAgent-Ansicht in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-03_

Die UserAgent-Ansicht speichert Informationen über die Benutzeragenten, die an Sitzungen teilgenommen haben und die über Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.


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
<td><p>UserAgentKey</p></td>
<td><p>int</p></td>
<td><p>Eindeutige Zahl, die diesen Benutzer-Agent identifiziert.</p></td>
</tr>
<tr class="even">
<td><p>UserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Zeichenfolge des Benutzer-Agents.</p></td>
</tr>
<tr class="odd">
<td><p>UAType</p></td>
<td><p>smallint</p></td>
<td><p>Benutzeragententyp. Weitere Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>UACategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Die Kategorie, der der Benutzer-Agent angehört. Beispielsweise weist der Benutzer-Agent Conferencing_Attendant_1.0 eine UACategory von CAA auf.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

