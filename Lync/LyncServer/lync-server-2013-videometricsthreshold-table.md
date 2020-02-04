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
ms.openlocfilehash: 93dc2fd539ccc24717939ccfa2ca93032fd9f25b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="8cc95-102">VideoMetricsThreshold-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cc95-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cc95-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8cc95-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8cc95-104">Die VideoMetricsThreshold-Tabelle enthält die optimalen und akzeptablen Werte für die Qualität der bei Videoanrufen verwendeten Metriken für die Erfahrung.</span><span class="sxs-lookup"><span data-stu-id="8cc95-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8cc95-105"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8cc95-106"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8cc95-107"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8cc95-108"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8cc95-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="8cc95-110">int</span><span class="sxs-lookup"><span data-stu-id="8cc95-110">int</span></span></p></td>
<td><p><span data-ttu-id="8cc95-111">Primary</span><span class="sxs-lookup"><span data-stu-id="8cc95-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="8cc95-112">Der Typ des Anrufs, der getätigt wurde.</span><span class="sxs-lookup"><span data-stu-id="8cc95-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cc95-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="8cc95-114">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="8cc95-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cc95-115">Der Standardwert ist 0,05.</span><span class="sxs-lookup"><span data-stu-id="8cc95-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cc95-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="8cc95-117">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="8cc95-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cc95-118">Der Standardwert ist 0,10.</span><span class="sxs-lookup"><span data-stu-id="8cc95-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cc95-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="8cc95-120">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="8cc95-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cc95-121">Der Standardwert ist 5,0.</span><span class="sxs-lookup"><span data-stu-id="8cc95-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cc95-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="8cc95-123">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="8cc95-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cc95-124">Der Standardwert ist 10,0.</span><span class="sxs-lookup"><span data-stu-id="8cc95-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cc95-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="8cc95-126">Dezimal (9; 4)</span><span class="sxs-lookup"><span data-stu-id="8cc95-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cc95-127">Der Standardwert ist 12,0000.</span><span class="sxs-lookup"><span data-stu-id="8cc95-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cc95-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="8cc95-129">Dezimal (9; 4)</span><span class="sxs-lookup"><span data-stu-id="8cc95-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cc95-130">Der Standardwert ist 7,0000.</span><span class="sxs-lookup"><span data-stu-id="8cc95-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cc95-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="8cc95-132">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="8cc95-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cc95-133">Der Standardwert ist 5,0.</span><span class="sxs-lookup"><span data-stu-id="8cc95-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cc95-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="8cc95-135">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="8cc95-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cc95-136">Der Standardwert ist 10.0/</span><span class="sxs-lookup"><span data-stu-id="8cc95-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cc95-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="8cc95-138">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="8cc95-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cc95-139">Der Standardwert ist 5,0.</span><span class="sxs-lookup"><span data-stu-id="8cc95-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cc95-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="8cc95-141">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="8cc95-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cc95-142">Der Standardwert ist 10,0.</span><span class="sxs-lookup"><span data-stu-id="8cc95-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cc95-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="8cc95-144">foat</span><span class="sxs-lookup"><span data-stu-id="8cc95-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cc95-145">Der Standardwert ist 0,05.</span><span class="sxs-lookup"><span data-stu-id="8cc95-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cc95-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="8cc95-147">float</span><span class="sxs-lookup"><span data-stu-id="8cc95-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cc95-148">Der Standardwert ist 0,10.</span><span class="sxs-lookup"><span data-stu-id="8cc95-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cc95-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="8cc95-150">float</span><span class="sxs-lookup"><span data-stu-id="8cc95-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cc95-151">Der Standardwert ist 12.</span><span class="sxs-lookup"><span data-stu-id="8cc95-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cc95-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="8cc95-153">float</span><span class="sxs-lookup"><span data-stu-id="8cc95-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cc95-154">Der Standardwert ist 7.</span><span class="sxs-lookup"><span data-stu-id="8cc95-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cc95-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="8cc95-156">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="8cc95-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cc95-157">Der Standardwert ist 5,00.</span><span class="sxs-lookup"><span data-stu-id="8cc95-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cc95-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="8cc95-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="8cc95-159">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="8cc95-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cc95-160">Der Standardwert ist 10,00.</span><span class="sxs-lookup"><span data-stu-id="8cc95-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

