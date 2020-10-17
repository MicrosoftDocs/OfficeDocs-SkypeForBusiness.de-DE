---
title: 'Lync Server 2013: NetworkConnectionDetail-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: NetworkConnectionDetail table
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48185170
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1dad115cb658289e20cf376c246c4e546bc0642
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505442"
---
# <a name="networkconnectiondetail-table-in-lync-server-2013"></a>NetworkConnectionDetail-Tabelle in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

Die NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungs-IDs, die anderweitig in der Quality of Experience-Datenbank verwendet werden, Netzwerkverbindungstypen zu. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.


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
<td><p><strong>NetworkConnectionDetailKey</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutiger Bezeichner für den Netzwerkverbindungstyp.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkConnectionDetail</strong></p></td>
<td><p>varchar (256)</p></td>
<td><p>Eigen</p></td>
<td><p>Netzwerkverbindungstyp, der NetworkConnectionDetailKey entspricht. Gültige Werte sind:</p>
<ol>
<li><p>0 – Wired</p></li>
<li><p>1 – WiFi</p></li>
<li><p>2 – Ethernet</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

