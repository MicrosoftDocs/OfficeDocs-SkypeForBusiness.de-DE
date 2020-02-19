---
title: 'Lync Server 2013: Endpunkt Tabelle'
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
ms.openlocfilehash: 33b2f42f1cd122f9f19cfbf04a1c255894ce6e97
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="83746-102">Endpunkt Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83746-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83746-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="83746-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="83746-104">Die Endpunkt Tabelle ist eine unterstützende Tabelle, in der Informationen zu den Endpunkten gespeichert werden, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="83746-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="83746-105">Jeder Datensatz in der Tabelle stellt einen Endpunkt dar.</span><span class="sxs-lookup"><span data-stu-id="83746-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83746-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="83746-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="83746-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="83746-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="83746-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="83746-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="83746-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="83746-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83746-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="83746-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="83746-111">int</span><span class="sxs-lookup"><span data-stu-id="83746-111">int</span></span></p></td>
<td><p><span data-ttu-id="83746-112">Primary</span><span class="sxs-lookup"><span data-stu-id="83746-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="83746-113">Eindeutige Zahl, die diesen Endpunkt identifiziert.</span><span class="sxs-lookup"><span data-stu-id="83746-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83746-114"><strong>Name</strong></span><span class="sxs-lookup"><span data-stu-id="83746-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="83746-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="83746-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83746-116">Eigen</span><span class="sxs-lookup"><span data-stu-id="83746-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="83746-117">Endpunktname.</span><span class="sxs-lookup"><span data-stu-id="83746-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83746-118"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="83746-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="83746-119">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="83746-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="83746-120">Betriebssystem (OS) des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="83746-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83746-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="83746-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="83746-122">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="83746-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="83746-123">CPU-Name des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="83746-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83746-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="83746-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="83746-125">smallint</span><span class="sxs-lookup"><span data-stu-id="83746-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="83746-126">Die Anzahl der CPU-Kerne des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="83746-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83746-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="83746-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="83746-128">int</span><span class="sxs-lookup"><span data-stu-id="83746-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="83746-129">CPU-Prozessorgeschwindigkeit des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="83746-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83746-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="83746-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="83746-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="83746-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="83746-132">Bit-Flag, das angibt, ob das System in einer virtualisierten Umgebung läuft:</span><span class="sxs-lookup"><span data-stu-id="83746-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="83746-133">0x0000 – keine</span><span class="sxs-lookup"><span data-stu-id="83746-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="83746-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="83746-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="83746-135">0x0002 – VMware</span><span class="sxs-lookup"><span data-stu-id="83746-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="83746-136">0x0004 – virtueller PC</span><span class="sxs-lookup"><span data-stu-id="83746-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="83746-137">0x0008 – xen-PC</span><span class="sxs-lookup"><span data-stu-id="83746-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

