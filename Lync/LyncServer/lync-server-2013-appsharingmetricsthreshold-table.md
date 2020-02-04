---
title: 'Lync Server 2013: AppSharingMetricsThreshold-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e247f83b00d226024f9fc671f2d744f1ee7fdf0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="c8282-102">AppSharingMetricsThreshold-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8282-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8282-103">_**Letztes Änderungsdatum des Themas:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="c8282-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="c8282-104">Die AppSharingMetricsThreshold-Tabelle enthält optimale und akzeptable Werte für die Qualität der Erfahrungs Metrik, die bei der Anwendungsfreigabe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c8282-104">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span> <span data-ttu-id="c8282-105">Diese Schwellenwerte werden verwendet, um festzustellen, ob die Anwendungsfreigabe Erfahrung als "schlecht" klassifiziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c8282-105">These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="c8282-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c8282-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8282-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c8282-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c8282-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c8282-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8282-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="c8282-112">int</span><span class="sxs-lookup"><span data-stu-id="c8282-112">int</span></span></p></td>
<td><p><span data-ttu-id="c8282-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c8282-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c8282-114">Der Typ des Anrufs, der getätigt wurde.</span><span class="sxs-lookup"><span data-stu-id="c8282-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8282-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c8282-116">int</span><span class="sxs-lookup"><span data-stu-id="c8282-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8282-117">Optimale Bandbreitenbeschränkung bei der Anwendungsfreigabe.</span><span class="sxs-lookup"><span data-stu-id="c8282-117">Optimal bandwidth limitation for application sharing.</span></span> <span data-ttu-id="c8282-118">Der Standardwert ist 1 Million.</span><span class="sxs-lookup"><span data-stu-id="c8282-118">The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8282-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c8282-120">int</span><span class="sxs-lookup"><span data-stu-id="c8282-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8282-121">Zulässige Bandbreitenbeschränkung für die Anwendungsfreigabe.</span><span class="sxs-lookup"><span data-stu-id="c8282-121">Acceptable bandwidth limitation for application sharing.</span></span> <span data-ttu-id="c8282-122">Der Standardwert ist 500000.</span><span class="sxs-lookup"><span data-stu-id="c8282-122">The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8282-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c8282-124">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="c8282-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8282-125">Optimaler Prozentsatz für "verwöhnte" Kacheln für die Klassifizierung einer Anwendungsfreigabe Qualität.</span><span class="sxs-lookup"><span data-stu-id="c8282-125">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="c8282-126">Dieser Wert ist der Prozentsatz des Inhalts des mitbenutzenden, der den Betrachter nicht erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="c8282-126">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="c8282-127">Inhalte werden möglicherweise verworfen (oder verdorben), wenn der mitbenutzende die Kacheln aus der grafikquelle abwirft oder die ASMCU-Kacheln Kacheln von Sharer abwirft.</span><span class="sxs-lookup"><span data-stu-id="c8282-127">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="c8282-128">Der Standardwert ist 11 Prozent.</span><span class="sxs-lookup"><span data-stu-id="c8282-128">The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8282-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c8282-130">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="c8282-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8282-131">cceptable-Prozentsatz für "verdorbene" Kacheln für die Klassifizierung einer Anwendungsfreigabe Qualität.</span><span class="sxs-lookup"><span data-stu-id="c8282-131">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="c8282-132">Dieser Wert ist der Prozentsatz des Inhalts des mitbenutzenden, der den Betrachter nicht erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="c8282-132">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="c8282-133">Inhalte werden möglicherweise verworfen (oder verdorben), wenn der mitbenutzende die Kacheln aus der grafikquelle abwirft oder die ASMCU-Kacheln Kacheln von Sharer abwirft.</span><span class="sxs-lookup"><span data-stu-id="c8282-133">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="c8282-134">Der Standardwert ist 36 Prozent.</span><span class="sxs-lookup"><span data-stu-id="c8282-134">The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8282-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c8282-136">int</span><span class="sxs-lookup"><span data-stu-id="c8282-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8282-137">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c8282-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8282-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c8282-139">int</span><span class="sxs-lookup"><span data-stu-id="c8282-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8282-140">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c8282-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8282-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c8282-142">float</span><span class="sxs-lookup"><span data-stu-id="c8282-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8282-143">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c8282-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8282-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c8282-145">float</span><span class="sxs-lookup"><span data-stu-id="c8282-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8282-146">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c8282-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8282-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c8282-148">float</span><span class="sxs-lookup"><span data-stu-id="c8282-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8282-149">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c8282-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8282-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c8282-151">float</span><span class="sxs-lookup"><span data-stu-id="c8282-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8282-152">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c8282-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8282-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c8282-154">float</span><span class="sxs-lookup"><span data-stu-id="c8282-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8282-155">Optimaler Wert für die relative unidirektionale Verzögerung zwischen den beiden Medien Endpunkten, die an der Anwendungsfreigabe beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="c8282-155">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="c8282-156">Dies ist ein Single-Hop-Latenzmaß.</span><span class="sxs-lookup"><span data-stu-id="c8282-156">This is a single-hop latency measure.</span></span> <span data-ttu-id="c8282-157">Der Standardwert ist 1,0 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="c8282-157">The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="c8282-158">Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c8282-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8282-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c8282-160">float</span><span class="sxs-lookup"><span data-stu-id="c8282-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8282-161">Optimaler Wert für die relative unidirektionale Verzögerung zwischen den beiden Medien Endpunkten, die an der Anwendungsfreigabe beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="c8282-161">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="c8282-162">Dies ist ein Single-Hop-Latenzmaß.</span><span class="sxs-lookup"><span data-stu-id="c8282-162">This is a single-hop latency measure.</span></span> <span data-ttu-id="c8282-163">Der Standardwert ist 1,75 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="c8282-163">The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="c8282-164">Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c8282-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8282-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c8282-166">float</span><span class="sxs-lookup"><span data-stu-id="c8282-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8282-167">Optimaler Wert der durchschnittlichen Verarbeitungs Wartezeit für RDP-Kacheln auf dem AS-Konferenz Server über die Dauer der Anzeige Sitzung.</span><span class="sxs-lookup"><span data-stu-id="c8282-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="c8282-168">Latenz ist der Zeitunterschied zwischen dem Codieren des Start Frames auf dem Server (Sharer oder MCU, je nach Szenario) und dem gleichen Start Frame im Viewer.</span><span class="sxs-lookup"><span data-stu-id="c8282-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="c8282-169">Ein hoher Durchschnitt zeigt eine längere Verzögerung bei der Anzeige an.</span><span class="sxs-lookup"><span data-stu-id="c8282-169">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="c8282-170">Ein überlasteter Konferenzserver zeigt gegebenenfalls höhere durchschnittliche Verzögerungen an.</span><span class="sxs-lookup"><span data-stu-id="c8282-170">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="c8282-171">Der Standardwert ist 200M.</span><span class="sxs-lookup"><span data-stu-id="c8282-171">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="c8282-172">Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c8282-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8282-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c8282-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c8282-174">float</span><span class="sxs-lookup"><span data-stu-id="c8282-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8282-175">Akzeptabler Wert der durchschnittlichen Verarbeitungs Wartezeit für RDP-Kacheln auf dem AS-Konferenz Server über die Dauer der Anzeige Sitzung.</span><span class="sxs-lookup"><span data-stu-id="c8282-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="c8282-176">Latenz ist der Zeitunterschied zwischen dem Codieren des Start Frames auf dem Server (Sharer oder MCU, je nach Szenario) und dem gleichen Start Frame im Viewer.</span><span class="sxs-lookup"><span data-stu-id="c8282-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="c8282-177">Ein hoher Durchschnitt zeigt eine längere Verzögerung bei der Anzeige an.</span><span class="sxs-lookup"><span data-stu-id="c8282-177">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="c8282-178">Ein überlasteter Konferenzserver zeigt gegebenenfalls höhere durchschnittliche Verzögerungen an.</span><span class="sxs-lookup"><span data-stu-id="c8282-178">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="c8282-179">Der Standardwert ist 200M.</span><span class="sxs-lookup"><span data-stu-id="c8282-179">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="c8282-180">Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c8282-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

