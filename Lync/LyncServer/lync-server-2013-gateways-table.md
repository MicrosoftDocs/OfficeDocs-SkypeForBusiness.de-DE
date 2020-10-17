---
title: 'Lync Server 2013: Gateways-Tabelle'
description: 'Lync Server 2013: Gateways-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Gateways table
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412795(v=OCS.15)
ms:contentKeyID: 48185034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 869aee0227c64c17f7bdbbfd82acbd43ae029bac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567041"
---
# <a name="gateways-table-in-lync-server-2013"></a>Gateways-Tabelle in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2010-11-05_

Die Gateways-Tabelle ist eine unterstützende Tabelle. Jeder Datensatz speichert Informationen zu einem Gateway, das an PSTN-anrufen (Public Switched Telephone Network) beteiligt ist, die Datensätze in der Datenbank aufweisen.


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
<td><p><strong>Gatewayserver</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die dieses Gateway identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gateway</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p> </p></td>
<td><p>Name des Gateways.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

