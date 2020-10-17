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
ms.openlocfilehash: 3a71e59b6cf9b4143a5b984cc7b169279aa2cb57
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533322"
---
# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="ff66c-102">Endpunkt Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff66c-102">Endpoint table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff66c-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ff66c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ff66c-104">Die Endpunkt Tabelle ist eine unterstützende Tabelle, in der Informationen zu den Endpunkten gespeichert werden, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="ff66c-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ff66c-105">Jeder Datensatz in der Tabelle stellt einen Endpunkt dar.</span><span class="sxs-lookup"><span data-stu-id="ff66c-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff66c-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="ff66c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ff66c-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="ff66c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ff66c-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="ff66c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ff66c-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="ff66c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff66c-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="ff66c-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ff66c-111">int</span><span class="sxs-lookup"><span data-stu-id="ff66c-111">int</span></span></p></td>
<td><p><span data-ttu-id="ff66c-112">Primary</span><span class="sxs-lookup"><span data-stu-id="ff66c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ff66c-113">Eindeutige Zahl, die diesen Endpunkt identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ff66c-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff66c-114"><strong>Name</strong></span><span class="sxs-lookup"><span data-stu-id="ff66c-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="ff66c-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ff66c-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ff66c-116">Eigen</span><span class="sxs-lookup"><span data-stu-id="ff66c-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="ff66c-117">Endpunktname.</span><span class="sxs-lookup"><span data-stu-id="ff66c-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff66c-118"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="ff66c-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="ff66c-119">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="ff66c-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ff66c-120">Betriebssystem (OS) des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="ff66c-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff66c-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="ff66c-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="ff66c-122">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="ff66c-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ff66c-123">CPU-Name des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="ff66c-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff66c-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="ff66c-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="ff66c-125">smallint</span><span class="sxs-lookup"><span data-stu-id="ff66c-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ff66c-126">Die Anzahl der CPU-Kerne des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="ff66c-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff66c-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="ff66c-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="ff66c-128">int</span><span class="sxs-lookup"><span data-stu-id="ff66c-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ff66c-129">CPU-Prozessorgeschwindigkeit des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="ff66c-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff66c-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ff66c-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ff66c-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="ff66c-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ff66c-132">Bit-Flag, das angibt, ob das System in einer virtualisierten Umgebung läuft:</span><span class="sxs-lookup"><span data-stu-id="ff66c-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="ff66c-133">0x0000 – keine</span><span class="sxs-lookup"><span data-stu-id="ff66c-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="ff66c-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="ff66c-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="ff66c-135">0x0002 – VMware</span><span class="sxs-lookup"><span data-stu-id="ff66c-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="ff66c-136">0x0004 – virtueller PC</span><span class="sxs-lookup"><span data-stu-id="ff66c-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="ff66c-137">0x0008 – xen-PC</span><span class="sxs-lookup"><span data-stu-id="ff66c-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

