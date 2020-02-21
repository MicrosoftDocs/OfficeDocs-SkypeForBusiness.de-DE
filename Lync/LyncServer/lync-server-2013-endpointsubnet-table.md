---
title: 'Lync Server 2013: EndpointSubnet-Tabelle'
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
ms.openlocfilehash: d9619eb758f95c3d43d1db09a4e6dc64c36a6931
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="endpointsubnet-table-in-lync-server-2013"></a><span data-ttu-id="5fe23-102">EndpointSubnet-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fe23-102">EndpointSubnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fe23-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5fe23-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5fe23-p101">Bei der EndpointSubnet-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für ein von Endpunkten erfasstes Subnetz.</span><span class="sxs-lookup"><span data-stu-id="5fe23-p101">The EndpointSubnet table is a supporting table. Each record represents one subnet captured from endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fe23-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="5fe23-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5fe23-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="5fe23-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5fe23-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="5fe23-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5fe23-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="5fe23-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fe23-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="5fe23-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="5fe23-111">int</span><span class="sxs-lookup"><span data-stu-id="5fe23-111">int</span></span></p></td>
<td><p><span data-ttu-id="5fe23-112">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="5fe23-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5fe23-113">Ganzzahlige Darstellung des Subnetzes.</span><span class="sxs-lookup"><span data-stu-id="5fe23-113">Integer representation for the subnet.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fe23-114"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="5fe23-114"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="5fe23-115">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="5fe23-115">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fe23-116">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="5fe23-116">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

