---
title: 'Lync Server 2013: ErrorDef-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorDef table
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48184403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6db93ea1b09e50d48ee5e0276d90e3db3975e9fe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a>ErrorDef-Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-05-25_

In der ErrorDef-Tabelle werden Informationen zu den einzelnen Fehlertypen gespeichert, die möglicherweise auftreten. Jeder Datensatz ist eine Art von Fehler.


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
<td><p><strong>ErrorID</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige ID-Nummer, die diese Art von Fehler identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Standard mäßiger SIP-Antwortcode, der diesem Fehler zugeordnet ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Microsoft-Diagnose-ID.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallTypeId</strong></p></td>
<td><p>Int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Typ des Anrufs. Weitere Informationen finden Sie <a href="lync-server-2013-calltype-table.md">in der CallType-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varbinary (33)</p></td>
<td><p> </p></td>
<td><p>Der Typ der fehlgeschlagenen Anforderung.</p>
<p>Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varbinary (257)</p></td>
<td><p> </p></td>
<td><p>Der Inhaltstyp der fehlgeschlagenen Anforderung.</p>
<p>Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

