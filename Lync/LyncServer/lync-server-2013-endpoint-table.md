---
title: 'Lync Server 2013: Endpoint-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cedf4d85cefd8a9fefb9f0ee4608f4a290fdc09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="55a4a-102">Endpoint-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55a4a-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55a4a-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="55a4a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="55a4a-104">Die Endpunkt Tabelle ist eine unterstützende Tabelle, in der Informationen zu den Endpunkten gespeichert werden, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="55a4a-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="55a4a-105">Jeder Datensatz in der Tabelle steht für einen Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="55a4a-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55a4a-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="55a4a-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="55a4a-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="55a4a-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="55a4a-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="55a4a-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="55a4a-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="55a4a-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55a4a-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="55a4a-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="55a4a-111">int</span><span class="sxs-lookup"><span data-stu-id="55a4a-111">int</span></span></p></td>
<td><p><span data-ttu-id="55a4a-112">Primary</span><span class="sxs-lookup"><span data-stu-id="55a4a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="55a4a-113">Eindeutige Zahl, die diesen Endpunkt kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="55a4a-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55a4a-114"><strong>Name</strong></span><span class="sxs-lookup"><span data-stu-id="55a4a-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="55a4a-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="55a4a-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55a4a-116">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="55a4a-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="55a4a-117">Endpunktname</span><span class="sxs-lookup"><span data-stu-id="55a4a-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55a4a-118"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="55a4a-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="55a4a-119">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="55a4a-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="55a4a-120">Betriebssystem (OS) des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="55a4a-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55a4a-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="55a4a-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="55a4a-122">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="55a4a-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="55a4a-123">Der CPU-Name des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="55a4a-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55a4a-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="55a4a-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="55a4a-125">smallint</span><span class="sxs-lookup"><span data-stu-id="55a4a-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="55a4a-126">Die Anzahl von CPU-Kernen des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="55a4a-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55a4a-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="55a4a-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="55a4a-128">int</span><span class="sxs-lookup"><span data-stu-id="55a4a-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="55a4a-129">CPU-Prozessorgeschwindigkeit des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="55a4a-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55a4a-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="55a4a-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="55a4a-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="55a4a-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="55a4a-132">Bit-Flag, das angibt, ob das System in einer virtualisierten Umgebung ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="55a4a-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="55a4a-133">0x0000 – keine</span><span class="sxs-lookup"><span data-stu-id="55a4a-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="55a4a-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="55a4a-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="55a4a-135">0x0002 – VMware</span><span class="sxs-lookup"><span data-stu-id="55a4a-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="55a4a-136">0x0004 – virtueller PC</span><span class="sxs-lookup"><span data-stu-id="55a4a-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="55a4a-137">0x0008 – xen-PC</span><span class="sxs-lookup"><span data-stu-id="55a4a-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

