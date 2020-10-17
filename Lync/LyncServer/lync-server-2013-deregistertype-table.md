---
title: 'Lync Server 2013: deregistertype-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c4aa5ea27cdf86d9c8e0c0cdf7260b20cca4478
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498962"
---
# <a name="deregistertype-table-in-lync-server-2013"></a>Deregistertype-Tabelle in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Bei der DeRegisterType-Tabelle handelt es sich um eine statische Tabelle, die eine Liste der möglichen Typen für eine Aufhebung der Registrierung von Benutzern speichert, wie zum Beispiel "Aufhebung der Registrierung durch den Client", "Registrierung abgelaufen" oder "Client reagiert nicht mehr".


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
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Zulässige Werte:</p>
<ul>
<li><p>0 -- Unbekannt</p></li>
<li><p>1 -- Aufhebung der Registrierung durch den Client</p></li>
<li><p>2 -- Registrierung abgelaufen</p></li>
<li><p>3 – Clientabsturz</p></li>
<li><p>4 -- Benutzerattribute geändert</p></li>
<li><p>5 – Bevorzugte Registrierungsstelle geändert</p></li>
<li><p>6 -- Legacyclient In Survival Mode</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

