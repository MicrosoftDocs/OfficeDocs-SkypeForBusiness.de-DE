---
title: 'Lync Server 2013: Servertabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 363c07a6ab3be8f5acdf0286a4223f96a8bd3700
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="07ab8-102">Servertabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07ab8-102">Server table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07ab8-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="07ab8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="07ab8-104">Die Server Tabelle ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="07ab8-104">The Server table is a supporting table.</span></span> <span data-ttu-id="07ab8-105">Jeder Datensatz steht für einen Server.</span><span class="sxs-lookup"><span data-stu-id="07ab8-105">Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07ab8-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="07ab8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="07ab8-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="07ab8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="07ab8-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="07ab8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="07ab8-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="07ab8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07ab8-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="07ab8-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="07ab8-111">int</span><span class="sxs-lookup"><span data-stu-id="07ab8-111">int</span></span></p></td>
<td><p><span data-ttu-id="07ab8-112">Primary</span><span class="sxs-lookup"><span data-stu-id="07ab8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="07ab8-113">Eindeutige Nummer, die den Server identifiziert.</span><span class="sxs-lookup"><span data-stu-id="07ab8-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07ab8-114"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="07ab8-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="07ab8-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="07ab8-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="07ab8-116">Index</span><span class="sxs-lookup"><span data-stu-id="07ab8-116">index</span></span></p></td>
<td><p><span data-ttu-id="07ab8-117">Mac-Adresszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="07ab8-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07ab8-118"><strong>Servertyp</strong></span><span class="sxs-lookup"><span data-stu-id="07ab8-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="07ab8-119">int</span><span class="sxs-lookup"><span data-stu-id="07ab8-119">int</span></span></p></td>
<td><p><span data-ttu-id="07ab8-120">Fremd</span><span class="sxs-lookup"><span data-stu-id="07ab8-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="07ab8-121">1: Vermittlungs Server</span><span class="sxs-lookup"><span data-stu-id="07ab8-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="07ab8-122">2: a/v Conferencing Server16394: a/v Edge service32769: Gateway</span><span class="sxs-lookup"><span data-stu-id="07ab8-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07ab8-123"><strong>Poolname</strong></span><span class="sxs-lookup"><span data-stu-id="07ab8-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="07ab8-124">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="07ab8-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="07ab8-125">Pool, zu dem der Server gehört.</span><span class="sxs-lookup"><span data-stu-id="07ab8-125">Pool the server belongs to.</span></span> <span data-ttu-id="07ab8-126">Gilt nur für den A/V-Konferenz Server.</span><span class="sxs-lookup"><span data-stu-id="07ab8-126">Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07ab8-127"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="07ab8-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="07ab8-128">datetime</span><span class="sxs-lookup"><span data-stu-id="07ab8-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="07ab8-129">Nur für interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="07ab8-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

