---
title: 'Lync Server 2013: Endpunkt Tabelle'
description: 'Lync Server 2013: Endpunkt Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 614872eee41b5d8e56da4b96cf5bbe3a4a1cf4d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575621"
---
# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="3c912-103">Endpunkt Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c912-103">Endpoint table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c912-104">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3c912-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3c912-105">Die Endpunkt Tabelle ist eine unterstützende Tabelle, in der Informationen zu den Endpunkten gespeichert werden, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="3c912-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="3c912-106">Jeder Datensatz in der Tabelle stellt einen Endpunkt dar.</span><span class="sxs-lookup"><span data-stu-id="3c912-106">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c912-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="3c912-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3c912-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="3c912-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3c912-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="3c912-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3c912-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="3c912-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c912-111"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="3c912-111"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3c912-112">int</span><span class="sxs-lookup"><span data-stu-id="3c912-112">int</span></span></p></td>
<td><p><span data-ttu-id="3c912-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3c912-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="3c912-114">Eindeutige Zahl, die diesen Endpunkt identifiziert.</span><span class="sxs-lookup"><span data-stu-id="3c912-114">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c912-115"><strong>Name</strong></span><span class="sxs-lookup"><span data-stu-id="3c912-115"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="3c912-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3c912-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3c912-117">Eigen</span><span class="sxs-lookup"><span data-stu-id="3c912-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="3c912-118">Endpunktname.</span><span class="sxs-lookup"><span data-stu-id="3c912-118">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c912-119"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="3c912-119"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="3c912-120">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="3c912-120">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3c912-121">Betriebssystem (OS) des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="3c912-121">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c912-122"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="3c912-122"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="3c912-123">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="3c912-123">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c912-124">CPU-Name des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="3c912-124">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c912-125"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="3c912-125"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="3c912-126">smallint</span><span class="sxs-lookup"><span data-stu-id="3c912-126">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c912-127">Die Anzahl der CPU-Kerne des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="3c912-127">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c912-128"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="3c912-128"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="3c912-129">int</span><span class="sxs-lookup"><span data-stu-id="3c912-129">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c912-130">CPU-Prozessorgeschwindigkeit des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="3c912-130">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c912-131"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="3c912-131"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="3c912-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="3c912-132">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c912-133">Bit-Flag, das angibt, ob das System in einer virtualisierten Umgebung läuft:</span><span class="sxs-lookup"><span data-stu-id="3c912-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="3c912-134">0x0000 – keine</span><span class="sxs-lookup"><span data-stu-id="3c912-134">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="3c912-135">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="3c912-135">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="3c912-136">0x0002 – VMware</span><span class="sxs-lookup"><span data-stu-id="3c912-136">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="3c912-137">0x0004 – virtueller PC</span><span class="sxs-lookup"><span data-stu-id="3c912-137">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="3c912-138">0x0008 – xen-PC</span><span class="sxs-lookup"><span data-stu-id="3c912-138">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

