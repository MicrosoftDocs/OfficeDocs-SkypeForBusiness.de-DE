---
title: 'Lync Server 2013: Subnet-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d684efa2d4bd68880a3838893e5c5cfe2a1a3cc2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519432"
---
# <a name="subnet-table-in-lync-server-2013"></a>Subnet-Tabelle in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

Bei der Subnet-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für ein Subnetz in der Netzwerkkonfigurationseinstellung.


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
<td><p><strong>SubnetIP</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Ganzzahlige Darstellung der Subnetz-IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Subnetzmaske</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Subnetzmaske</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Referenziert aus der <a href="lync-server-2013-usersite-table.md">UserSite-Tabelle in lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SubnetDescription</strong></p></td>
<td><p>nvarchar (512)</p></td>
<td></td>
<td><p>Beschreibung des Subnetzes.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

