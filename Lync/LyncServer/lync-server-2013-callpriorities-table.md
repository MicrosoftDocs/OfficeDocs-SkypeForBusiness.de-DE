---
title: 'Lync Server 2013: CallPriorities-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallPriorities table
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48183275
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2be19538e065a1f9a25dd58da93b2752a27333e9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="callpriorities-table-in-lync-server-2013"></a>CallPriorities-Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Die CallPriorities-Tabelle ist eine statische Tabelle, in der die Liste der möglichen Aufrufprioritäten wie "emergency", "urgent" oder "normal" gespeichert ist.


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
<td><p><strong>Prioritäts-Nr</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>Priority</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Gültige Werte:</p>
<ul>
<li><p>0 – Unbekannt</p></li>
<li><p>1 – Nicht dringend</p></li>
<li><p>2 – Normal</p></li>
<li><p>3 – Dringend</p></li>
<li><p>4 – Notfall</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

