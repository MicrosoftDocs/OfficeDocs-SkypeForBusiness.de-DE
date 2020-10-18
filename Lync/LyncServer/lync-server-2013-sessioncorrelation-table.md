---
title: 'Lync Server 2013: SessionCorrelation-Tabelle'
description: 'Lync Server 2013: SessionCorrelation-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionCorrelation table
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48183267
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814b7e8539d89f87e7df60ceb03e70800553fb55
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579661"
---
# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="ae681-103">SessionCorrelation-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae681-103">SessionCorrelation table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae681-104">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ae681-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ae681-105">Die SessionCorrelation-Tabelle ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ae681-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="ae681-106">Jeder Datensatz stellt eine CorrelationId dar, die zum Korrelieren mehrerer Sitzungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ae681-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae681-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="ae681-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ae681-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="ae681-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ae681-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="ae681-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ae681-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="ae681-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae681-111"><strong>Prüfsumme</strong></span><span class="sxs-lookup"><span data-stu-id="ae681-111"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="ae681-112">int</span><span class="sxs-lookup"><span data-stu-id="ae681-112">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae681-113"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="ae681-113"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ae681-114">int</span><span class="sxs-lookup"><span data-stu-id="ae681-114">int</span></span></p></td>
<td><p><span data-ttu-id="ae681-115">Primary</span><span class="sxs-lookup"><span data-stu-id="ae681-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="ae681-116">Eindeutige Zahl, die diesen A/V-Konferenzserver identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ae681-116">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae681-117"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="ae681-117"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="ae681-118">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ae681-118">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae681-119">Eigen</span><span class="sxs-lookup"><span data-stu-id="ae681-119">Unique</span></span></p></td>
<td><p><span data-ttu-id="ae681-120">Korrelierte Sitzungen haben dieselbe Korrelations-ID.</span><span class="sxs-lookup"><span data-stu-id="ae681-120">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae681-121"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="ae681-121"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="ae681-122">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ae681-122">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae681-123">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="ae681-123">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

