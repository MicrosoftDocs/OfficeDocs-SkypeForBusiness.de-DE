---
title: 'Lync Server 2013: VideoMetricsThreshold-Tabelle'
description: 'Lync Server 2013: VideoMetricsThreshold-Tabelle.'
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
ms.openlocfilehash: 93cdd6fb4c3c54ac1470499490f36fee87ba283d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568001"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="d962e-103">VideoMetricsThreshold-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d962e-103">VideoMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d962e-104">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d962e-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d962e-105">Die Tabelle VideoMetricsThreshold enthält optimale und zulässige Werte für Quality of Experience-Metriken, die bei Videoanrufen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d962e-105">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d962e-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d962e-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d962e-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d962e-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d962e-110"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-110"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="d962e-111">int</span><span class="sxs-lookup"><span data-stu-id="d962e-111">int</span></span></p></td>
<td><p><span data-ttu-id="d962e-112">Primary</span><span class="sxs-lookup"><span data-stu-id="d962e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d962e-113">Der Typ des getätigten Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d962e-113">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d962e-114"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-114"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d962e-115">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d962e-115">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d962e-116">Der Standardwert lautet 0,05.</span><span class="sxs-lookup"><span data-stu-id="d962e-116">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d962e-117"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-117"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d962e-118">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d962e-118">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d962e-119">Der Standardwert lautet 0,10.</span><span class="sxs-lookup"><span data-stu-id="d962e-119">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d962e-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d962e-121">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d962e-121">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d962e-122">Der Standardwert lautet 5,0.</span><span class="sxs-lookup"><span data-stu-id="d962e-122">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d962e-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d962e-124">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d962e-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d962e-125">Der Standardwert lautet 10,0.</span><span class="sxs-lookup"><span data-stu-id="d962e-125">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d962e-126"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-126"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d962e-127">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="d962e-127">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d962e-128">Der Standardwert lautet 12,0000.</span><span class="sxs-lookup"><span data-stu-id="d962e-128">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d962e-129"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-129"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d962e-130">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="d962e-130">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d962e-131">Der Standardwert lautet 7,0000.</span><span class="sxs-lookup"><span data-stu-id="d962e-131">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d962e-132"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-132"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d962e-133">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d962e-133">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d962e-134">Der Standardwert lautet 5,0.</span><span class="sxs-lookup"><span data-stu-id="d962e-134">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d962e-135"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-135"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d962e-136">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d962e-136">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d962e-137">Der Standardwert lautet 10,0.</span><span class="sxs-lookup"><span data-stu-id="d962e-137">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d962e-138"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-138"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d962e-139">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d962e-139">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d962e-140">Der Standardwert lautet 5,0.</span><span class="sxs-lookup"><span data-stu-id="d962e-140">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d962e-141"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-141"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d962e-142">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d962e-142">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d962e-143">Der Standardwert lautet 10,0.</span><span class="sxs-lookup"><span data-stu-id="d962e-143">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d962e-144"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-144"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d962e-145">foat</span><span class="sxs-lookup"><span data-stu-id="d962e-145">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d962e-146">Der Standardwert lautet 0,05.</span><span class="sxs-lookup"><span data-stu-id="d962e-146">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d962e-147"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-147"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d962e-148">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d962e-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d962e-149">Der Standardwert lautet 0,10.</span><span class="sxs-lookup"><span data-stu-id="d962e-149">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d962e-150"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-150"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d962e-151">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d962e-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d962e-152">Der Standardwert lautet 12.</span><span class="sxs-lookup"><span data-stu-id="d962e-152">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d962e-153"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-153"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d962e-154">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d962e-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d962e-155">Der Standardwert lautet 7.</span><span class="sxs-lookup"><span data-stu-id="d962e-155">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d962e-156"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-156"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d962e-157">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d962e-157">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d962e-158">Der Standardwert lautet 5,00.</span><span class="sxs-lookup"><span data-stu-id="d962e-158">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d962e-159"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="d962e-159"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="d962e-160">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d962e-160">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d962e-161">Der Standardwert lautet 10,00.</span><span class="sxs-lookup"><span data-stu-id="d962e-161">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

