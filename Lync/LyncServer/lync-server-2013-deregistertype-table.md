---
title: 'Lync Server 2013: DeRegisterType-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97d25ded1a281df0774644cd0d69f5e12d9c85a7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a>DeRegisterType-Tabelle in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Die Tabelle "deregistertype" ist eine statische Tabelle, in der die Liste der möglichen Benutzer deregister-Typen wie "Client initiiert", "Registrierung abgelaufen" oder "Client reagiert nicht mehr" gespeichert ist.


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
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Zulässige Werte:</p>
<ul>
<li><p>0-unbekannt</p></li>
<li><p>1-Client initiierte Deregistrierung</p></li>
<li><p>2 – Registrierung abgelaufen</p></li>
<li><p>3 – Client stürzte ab</p></li>
<li><p>4 – Benutzerattribute geändert</p></li>
<li><p>5 – bevorzugte Registrierungsstelle geändert</p></li>
<li><p>6 – Legacy-Client im Survival-Modus</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

