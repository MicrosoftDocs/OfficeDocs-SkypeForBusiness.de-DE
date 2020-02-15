---
title: 'Lync Server 2013: VideoMetricsThreshold-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ffd2c289917c5ccf0ec3a484284fecca3323810
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="f71e2-102">VideoMetricsThreshold-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f71e2-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f71e2-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f71e2-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f71e2-104">Die Tabelle VideoMetricsThreshold enthält optimale und zulässige Werte für Quality of Experience-Metriken, die bei Videoanrufen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f71e2-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f71e2-105"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f71e2-106"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f71e2-107"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f71e2-108"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f71e2-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="f71e2-110">int</span><span class="sxs-lookup"><span data-stu-id="f71e2-110">int</span></span></p></td>
<td><p><span data-ttu-id="f71e2-111">Primary</span><span class="sxs-lookup"><span data-stu-id="f71e2-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="f71e2-112">Der Typ des getätigten Anrufs.</span><span class="sxs-lookup"><span data-stu-id="f71e2-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71e2-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="f71e2-114">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f71e2-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71e2-115">Der Standardwert lautet 0,05.</span><span class="sxs-lookup"><span data-stu-id="f71e2-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71e2-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="f71e2-117">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f71e2-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71e2-118">Der Standardwert lautet 0,10.</span><span class="sxs-lookup"><span data-stu-id="f71e2-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71e2-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="f71e2-120">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f71e2-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71e2-121">Der Standardwert lautet 5,0.</span><span class="sxs-lookup"><span data-stu-id="f71e2-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71e2-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="f71e2-123">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f71e2-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71e2-124">Der Standardwert lautet 10,0.</span><span class="sxs-lookup"><span data-stu-id="f71e2-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71e2-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="f71e2-126">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f71e2-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71e2-127">Der Standardwert lautet 12,0000.</span><span class="sxs-lookup"><span data-stu-id="f71e2-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71e2-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="f71e2-129">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f71e2-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71e2-130">Der Standardwert lautet 7,0000.</span><span class="sxs-lookup"><span data-stu-id="f71e2-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71e2-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="f71e2-132">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f71e2-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71e2-133">Der Standardwert lautet 5,0.</span><span class="sxs-lookup"><span data-stu-id="f71e2-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71e2-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="f71e2-135">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f71e2-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71e2-136">Der Standardwert lautet 10,0.</span><span class="sxs-lookup"><span data-stu-id="f71e2-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71e2-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="f71e2-138">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f71e2-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71e2-139">Der Standardwert lautet 5,0.</span><span class="sxs-lookup"><span data-stu-id="f71e2-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71e2-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="f71e2-141">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f71e2-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71e2-142">Der Standardwert lautet 10,0.</span><span class="sxs-lookup"><span data-stu-id="f71e2-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71e2-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="f71e2-144">foat</span><span class="sxs-lookup"><span data-stu-id="f71e2-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71e2-145">Der Standardwert lautet 0,05.</span><span class="sxs-lookup"><span data-stu-id="f71e2-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71e2-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="f71e2-147">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="f71e2-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71e2-148">Der Standardwert lautet 0,10.</span><span class="sxs-lookup"><span data-stu-id="f71e2-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71e2-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="f71e2-150">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="f71e2-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71e2-151">Der Standardwert lautet 12.</span><span class="sxs-lookup"><span data-stu-id="f71e2-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71e2-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="f71e2-153">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="f71e2-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71e2-154">Der Standardwert lautet 7.</span><span class="sxs-lookup"><span data-stu-id="f71e2-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71e2-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="f71e2-156">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f71e2-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71e2-157">Der Standardwert lautet 5,00.</span><span class="sxs-lookup"><span data-stu-id="f71e2-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71e2-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="f71e2-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="f71e2-159">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f71e2-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71e2-160">Der Standardwert lautet 10,00.</span><span class="sxs-lookup"><span data-stu-id="f71e2-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

