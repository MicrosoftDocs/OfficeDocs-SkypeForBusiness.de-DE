---
title: 'Lync Server 2013: EndpointSubnet-Tabelle'
description: 'Lync Server 2013: EndpointSubnet-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: EndpointSubnet table
ms:assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398933(v=OCS.15)
ms:contentKeyID: 48185514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63e7d3c908a55ae866ed8e330cc8742b9f6a0096
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575611"
---
# <a name="endpointsubnet-table-in-lync-server-2013"></a><span data-ttu-id="d70e8-103">EndpointSubnet-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d70e8-103">EndpointSubnet table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d70e8-104">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d70e8-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d70e8-p101">Bei der EndpointSubnet-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für ein von Endpunkten erfasstes Subnetz.</span><span class="sxs-lookup"><span data-stu-id="d70e8-p101">The EndpointSubnet table is a supporting table. Each record represents one subnet captured from endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d70e8-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="d70e8-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d70e8-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="d70e8-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d70e8-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="d70e8-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d70e8-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="d70e8-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d70e8-111"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="d70e8-111"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="d70e8-112">int</span><span class="sxs-lookup"><span data-stu-id="d70e8-112">int</span></span></p></td>
<td><p><span data-ttu-id="d70e8-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="d70e8-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d70e8-114">Ganzzahlige Darstellung des Subnetzes.</span><span class="sxs-lookup"><span data-stu-id="d70e8-114">Integer representation for the subnet.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e8-115"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="d70e8-115"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="d70e8-116">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d70e8-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d70e8-117">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="d70e8-117">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

