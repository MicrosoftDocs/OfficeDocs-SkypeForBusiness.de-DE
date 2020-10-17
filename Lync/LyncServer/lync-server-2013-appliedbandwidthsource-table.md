---
title: 'Lync Server 2013: AppliedBandwidthSource-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppliedBandwidthSource table
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425725(v=OCS.15)
ms:contentKeyID: 48183638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 289e3b2093bea001ee684945f17aee2ecb84927d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504992"
---
# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a><span data-ttu-id="57dee-102">AppliedBandwidthSource-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57dee-102">AppliedBandwidthSource table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57dee-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="57dee-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="57dee-p101">Bei der AppliedBandwidthSource-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Quelle.</span><span class="sxs-lookup"><span data-stu-id="57dee-p101">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57dee-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="57dee-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="57dee-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="57dee-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="57dee-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="57dee-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="57dee-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="57dee-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57dee-110"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="57dee-110"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="57dee-111">int</span><span class="sxs-lookup"><span data-stu-id="57dee-111">int</span></span></p></td>
<td><p><span data-ttu-id="57dee-112">Primary</span><span class="sxs-lookup"><span data-stu-id="57dee-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="57dee-113">Eindeutige Zahl, die diese Quelle identifiziert.</span><span class="sxs-lookup"><span data-stu-id="57dee-113">Unique number identifying the source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57dee-114"><strong>AppliedBandwidthSource</strong></span><span class="sxs-lookup"><span data-stu-id="57dee-114"><strong>AppliedBandwidthSource</strong></span></span></p></td>
<td><p><span data-ttu-id="57dee-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="57dee-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="57dee-116">Eigen</span><span class="sxs-lookup"><span data-stu-id="57dee-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="57dee-p102">Dies ist die Quelle der vorgegebenen Bandbreitenbeschränkung. Sie beschreibt den Ursprung der Bandbreitenbeschränkung (z. B."Policy Server", "TURN Server" oder "Modality").</span><span class="sxs-lookup"><span data-stu-id="57dee-p102">This is the source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

