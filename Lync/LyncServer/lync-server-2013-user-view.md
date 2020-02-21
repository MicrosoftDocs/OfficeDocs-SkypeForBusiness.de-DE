---
title: 'Lync Server 2013: Benutzeransicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12499f63e262d681297b8289231f58262ba75999
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-view-in-lync-server-2013"></a>Benutzeransicht in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

In der Benutzeransicht werden Informationen über Benutzer gespeichert, die an Anrufen oder Sitzungen teilnehmen, welche über Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.


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
<td><p>UserId</p></td>
<td><p>int</p></td>
<td><p>Eindeutige Zahl, die diesen Benutzer identifiziert.</p></td>
</tr>
<tr class="even">
<td><p>UserUri</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Benutzers</p></td>
</tr>
<tr class="odd">
<td><p>TenantKey</p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Mandant des Benutzers. Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>URI</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Benutzer-URI-Typ. Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

