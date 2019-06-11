---
title: 'Lync Server 2013: AppSharingMetricsThreshold-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0f8dc1dac3dc7a9ec362473221d36191dd7dd0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="76cde-102">AppSharingMetricsThreshold-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76cde-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76cde-103">_**Letztes Änderungsdatum des Themas:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="76cde-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="76cde-104">Die AppSharingMetricsThreshold-Tabelle enthält optimale und akzeptable Werte für die Qualität der Erfahrungs Metrik, die bei der Anwendungsfreigabe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="76cde-104">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span> <span data-ttu-id="76cde-105">Diese Schwellenwerte werden verwendet, um festzustellen, ob die Anwendungsfreigabe Erfahrung als "schlecht" klassifiziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="76cde-105">These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="76cde-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="76cde-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76cde-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="76cde-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="76cde-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="76cde-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76cde-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="76cde-112">int</span><span class="sxs-lookup"><span data-stu-id="76cde-112">int</span></span></p></td>
<td><p><span data-ttu-id="76cde-113">Primary</span><span class="sxs-lookup"><span data-stu-id="76cde-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="76cde-114">Der Typ des Anrufs, der getätigt wurde.</span><span class="sxs-lookup"><span data-stu-id="76cde-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76cde-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="76cde-116">int</span><span class="sxs-lookup"><span data-stu-id="76cde-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76cde-117">Optimale Bandbreitenbeschränkung bei der Anwendungsfreigabe.</span><span class="sxs-lookup"><span data-stu-id="76cde-117">Optimal bandwidth limitation for application sharing.</span></span> <span data-ttu-id="76cde-118">Der Standardwert ist 1 Million.</span><span class="sxs-lookup"><span data-stu-id="76cde-118">The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76cde-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="76cde-120">int</span><span class="sxs-lookup"><span data-stu-id="76cde-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76cde-121">Zulässige Bandbreitenbeschränkung für die Anwendungsfreigabe.</span><span class="sxs-lookup"><span data-stu-id="76cde-121">Acceptable bandwidth limitation for application sharing.</span></span> <span data-ttu-id="76cde-122">Der Standardwert ist 500000.</span><span class="sxs-lookup"><span data-stu-id="76cde-122">The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76cde-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="76cde-124">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="76cde-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76cde-125">Optimaler Prozentsatz für "verwöhnte" Kacheln für die Klassifizierung einer Anwendungsfreigabe Qualität.</span><span class="sxs-lookup"><span data-stu-id="76cde-125">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="76cde-126">Dieser Wert ist der Prozentsatz des Inhalts des mitbenutzenden, der den Betrachter nicht erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="76cde-126">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="76cde-127">Inhalte werden möglicherweise verworfen (oder verdorben), wenn der mitbenutzende die Kacheln aus der grafikquelle abwirft oder die ASMCU-Kacheln Kacheln von Sharer abwirft.</span><span class="sxs-lookup"><span data-stu-id="76cde-127">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="76cde-128">Der Standardwert ist 11 Prozent.</span><span class="sxs-lookup"><span data-stu-id="76cde-128">The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76cde-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="76cde-130">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="76cde-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76cde-131">cceptable-Prozentsatz für "verdorbene" Kacheln für die Klassifizierung einer Anwendungsfreigabe Qualität.</span><span class="sxs-lookup"><span data-stu-id="76cde-131">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="76cde-132">Dieser Wert ist der Prozentsatz des Inhalts des mitbenutzenden, der den Betrachter nicht erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="76cde-132">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="76cde-133">Inhalte werden möglicherweise verworfen (oder verdorben), wenn der mitbenutzende die Kacheln aus der grafikquelle abwirft oder die ASMCU-Kacheln Kacheln von Sharer abwirft.</span><span class="sxs-lookup"><span data-stu-id="76cde-133">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="76cde-134">Der Standardwert ist 36 Prozent.</span><span class="sxs-lookup"><span data-stu-id="76cde-134">The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76cde-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="76cde-136">int</span><span class="sxs-lookup"><span data-stu-id="76cde-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76cde-137">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="76cde-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76cde-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="76cde-139">int</span><span class="sxs-lookup"><span data-stu-id="76cde-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76cde-140">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="76cde-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76cde-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="76cde-142">float</span><span class="sxs-lookup"><span data-stu-id="76cde-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76cde-143">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="76cde-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76cde-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="76cde-145">float</span><span class="sxs-lookup"><span data-stu-id="76cde-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76cde-146">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="76cde-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76cde-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="76cde-148">float</span><span class="sxs-lookup"><span data-stu-id="76cde-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76cde-149">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="76cde-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76cde-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="76cde-151">float</span><span class="sxs-lookup"><span data-stu-id="76cde-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76cde-152">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="76cde-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76cde-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="76cde-154">float</span><span class="sxs-lookup"><span data-stu-id="76cde-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76cde-155">Optimaler Wert für die relative unidirektionale Verzögerung zwischen den beiden Medien Endpunkten, die an der Anwendungsfreigabe beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="76cde-155">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="76cde-156">Dies ist ein Single-Hop-Latenzmaß.</span><span class="sxs-lookup"><span data-stu-id="76cde-156">This is a single-hop latency measure.</span></span> <span data-ttu-id="76cde-157">Der Standardwert ist 1,0 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="76cde-157">The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="76cde-158">Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="76cde-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76cde-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="76cde-160">float</span><span class="sxs-lookup"><span data-stu-id="76cde-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76cde-161">Optimaler Wert für die relative unidirektionale Verzögerung zwischen den beiden Medien Endpunkten, die an der Anwendungsfreigabe beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="76cde-161">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="76cde-162">Dies ist ein Single-Hop-Latenzmaß.</span><span class="sxs-lookup"><span data-stu-id="76cde-162">This is a single-hop latency measure.</span></span> <span data-ttu-id="76cde-163">Der Standardwert ist 1,75 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="76cde-163">The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="76cde-164">Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="76cde-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76cde-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="76cde-166">float</span><span class="sxs-lookup"><span data-stu-id="76cde-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76cde-167">Optimaler Wert der durchschnittlichen Verarbeitungs Wartezeit für RDP-Kacheln auf dem AS-Konferenz Server über die Dauer der Anzeige Sitzung.</span><span class="sxs-lookup"><span data-stu-id="76cde-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="76cde-168">Latenz ist der Zeitunterschied zwischen dem Codieren des Start Frames auf dem Server (Sharer oder MCU, je nach Szenario) und dem gleichen Start Frame im Viewer.</span><span class="sxs-lookup"><span data-stu-id="76cde-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="76cde-169">Ein hoher Durchschnitt zeigt eine längere Verzögerung bei der Anzeige an.</span><span class="sxs-lookup"><span data-stu-id="76cde-169">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="76cde-170">Ein überlasteter Konferenzserver zeigt gegebenenfalls höhere durchschnittliche Verzögerungen an.</span><span class="sxs-lookup"><span data-stu-id="76cde-170">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="76cde-171">Der Standardwert ist 200M.</span><span class="sxs-lookup"><span data-stu-id="76cde-171">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="76cde-172">Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="76cde-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76cde-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="76cde-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="76cde-174">float</span><span class="sxs-lookup"><span data-stu-id="76cde-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76cde-175">Akzeptabler Wert der durchschnittlichen Verarbeitungs Wartezeit für RDP-Kacheln auf dem AS-Konferenz Server über die Dauer der Anzeige Sitzung.</span><span class="sxs-lookup"><span data-stu-id="76cde-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="76cde-176">Latenz ist der Zeitunterschied zwischen dem Codieren des Start Frames auf dem Server (Sharer oder MCU, je nach Szenario) und dem gleichen Start Frame im Viewer.</span><span class="sxs-lookup"><span data-stu-id="76cde-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="76cde-177">Ein hoher Durchschnitt zeigt eine längere Verzögerung bei der Anzeige an.</span><span class="sxs-lookup"><span data-stu-id="76cde-177">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="76cde-178">Ein überlasteter Konferenzserver zeigt gegebenenfalls höhere durchschnittliche Verzögerungen an.</span><span class="sxs-lookup"><span data-stu-id="76cde-178">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="76cde-179">Der Standardwert ist 200M.</span><span class="sxs-lookup"><span data-stu-id="76cde-179">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="76cde-180">Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="76cde-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

