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
ms.openlocfilehash: ebfc08cd5a27527d5afebdae8b2fea8335f93dcb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510232"
---
# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="f249e-102">Server Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f249e-102">Server table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f249e-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f249e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f249e-p101">Bei der Server-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Server.</span><span class="sxs-lookup"><span data-stu-id="f249e-p101">The Server table is a supporting table. Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f249e-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="f249e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f249e-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="f249e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f249e-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="f249e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f249e-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="f249e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f249e-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="f249e-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f249e-111">int</span><span class="sxs-lookup"><span data-stu-id="f249e-111">int</span></span></p></td>
<td><p><span data-ttu-id="f249e-112">Primary</span><span class="sxs-lookup"><span data-stu-id="f249e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f249e-113">Eindeutige Zahl, die den Server identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f249e-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f249e-114"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="f249e-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="f249e-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f249e-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f249e-116">Index</span><span class="sxs-lookup"><span data-stu-id="f249e-116">index</span></span></p></td>
<td><p><span data-ttu-id="f249e-117">MAC-Adresszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f249e-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f249e-118"><strong>Servertyp</strong></span><span class="sxs-lookup"><span data-stu-id="f249e-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="f249e-119">int</span><span class="sxs-lookup"><span data-stu-id="f249e-119">int</span></span></p></td>
<td><p><span data-ttu-id="f249e-120">Fremd</span><span class="sxs-lookup"><span data-stu-id="f249e-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f249e-121">1: Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="f249e-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="f249e-122">2: A/V-Konferenzserver16394: A/V-Edgedienst32769: Gateway</span><span class="sxs-lookup"><span data-stu-id="f249e-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f249e-123"><strong>Poolname</strong></span><span class="sxs-lookup"><span data-stu-id="f249e-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="f249e-124">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="f249e-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f249e-p102">Pool, zu dem der Server gehört. Gilt nur für den A/V-Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="f249e-p102">Pool the server belongs to. Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f249e-127"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="f249e-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="f249e-128">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="f249e-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f249e-129">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="f249e-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

