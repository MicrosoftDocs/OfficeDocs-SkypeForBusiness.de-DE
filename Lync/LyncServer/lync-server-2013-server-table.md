---
title: 'Lync Server 2013: Server Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d95ca6af9a3e762a39142fcaf754d810050d83d3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="e4e2f-102">Server Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4e2f-102">Server table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4e2f-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e4e2f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e4e2f-p101">Bei der Server-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Server.</span><span class="sxs-lookup"><span data-stu-id="e4e2f-p101">The Server table is a supporting table. Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4e2f-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="e4e2f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e4e2f-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="e4e2f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e4e2f-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="e4e2f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e4e2f-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="e4e2f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4e2f-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="e4e2f-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e4e2f-111">int</span><span class="sxs-lookup"><span data-stu-id="e4e2f-111">int</span></span></p></td>
<td><p><span data-ttu-id="e4e2f-112">Primary</span><span class="sxs-lookup"><span data-stu-id="e4e2f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e4e2f-113">Eindeutige Zahl, die den Server identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e4e2f-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4e2f-114"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="e4e2f-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="e4e2f-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e4e2f-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e4e2f-116">Index</span><span class="sxs-lookup"><span data-stu-id="e4e2f-116">index</span></span></p></td>
<td><p><span data-ttu-id="e4e2f-117">MAC-Adresszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e4e2f-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4e2f-118"><strong>Servertyp</strong></span><span class="sxs-lookup"><span data-stu-id="e4e2f-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="e4e2f-119">int</span><span class="sxs-lookup"><span data-stu-id="e4e2f-119">int</span></span></p></td>
<td><p><span data-ttu-id="e4e2f-120">Fremd</span><span class="sxs-lookup"><span data-stu-id="e4e2f-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e4e2f-121">1: Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="e4e2f-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="e4e2f-122">2: A/V-Konferenzserver16394: A/V-Edgedienst32769: Gateway</span><span class="sxs-lookup"><span data-stu-id="e4e2f-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4e2f-123"><strong>Poolname</strong></span><span class="sxs-lookup"><span data-stu-id="e4e2f-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="e4e2f-124">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="e4e2f-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e4e2f-p102">Pool, zu dem der Server gehört. Gilt nur für den A/V-Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="e4e2f-p102">Pool the server belongs to. Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4e2f-127"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="e4e2f-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="e4e2f-128">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="e4e2f-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e4e2f-129">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="e4e2f-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

