---
title: 'Lync Server 2013: AppSharingMetricsThreshold-Tabelle'
description: 'Lync Server 2013: AppSharingMetricsThreshold-Tabelle.'
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
ms.openlocfilehash: 092c7d08026e6b736b81043a71b4ecaabc4d5f1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546811"
---
# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="7c8bf-103">AppSharingMetricsThreshold-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c8bf-103">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c8bf-104">_**Letztes Änderungsstand des Themas:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="7c8bf-104">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="7c8bf-p101">In der AppSharingMetricsThreshold-Tabelle sind die optimalen und zulässigen Werte für die QoE-Daten (Quality of Experience) enthalten, die für die Anwendungsfreigabe verwendet werden. Diese Schwellenwerte werden verwendet, um zu ermitteln, ob die Anwendungsfreigabemöglichkeiten als schlecht klassifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-p101">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing. These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="7c8bf-107">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c8bf-108"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7c8bf-109"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7c8bf-110"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7c8bf-111"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c8bf-112"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-112"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="7c8bf-113">int</span><span class="sxs-lookup"><span data-stu-id="7c8bf-113">int</span></span></p></td>
<td><p><span data-ttu-id="7c8bf-114">Primary</span><span class="sxs-lookup"><span data-stu-id="7c8bf-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="7c8bf-115">Anruftyp, der getätigt wurde.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-115">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c8bf-116"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-116"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7c8bf-117">int</span><span class="sxs-lookup"><span data-stu-id="7c8bf-117">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c8bf-p102">Optimale Bandbreitenbeschränkung für die Anwendungsfreigabe. Der Standardwert lautet 1000000.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-p102">Optimal bandwidth limitation for application sharing. The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c8bf-120"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-120"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7c8bf-121">int</span><span class="sxs-lookup"><span data-stu-id="7c8bf-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c8bf-p103">Zulässige Bandbreitenbeschränkung für die Anwendungsfreigabe. Der Standardwert lautet 500000.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-p103">Acceptable bandwidth limitation for application sharing. The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c8bf-124"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-124"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7c8bf-125">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7c8bf-125">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c8bf-p104">Optimaler Prozentsatzwert für „beschädigte“ Kacheln bei der Klassifizierung der Anwendungsfreigabequalität. Dieser Wert gibt den Prozentsatz des Inhalts an, der vom freigebenden Benutzer nicht an den anzeigenden Benutzer weitergegeben wurde. Inhalt kann gelöscht (oder beschädigt) werden, wenn der freigebende Benutzer Kacheln aus der Grafikquelle löscht oder wenn ASMCU-Kacheln die Kacheln des freigebenden Benutzers löschen. Der Standardwert lautet 11 Prozent</span><span class="sxs-lookup"><span data-stu-id="7c8bf-p104">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c8bf-130"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-130"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7c8bf-131">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7c8bf-131">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c8bf-p105">Optimaler Prozentsatzwert für „beschädigte“ Kacheln bei der Klassifizierung der Anwendungsfreigabequalität. Dieser Wert gibt den Prozentsatz des Inhalts an, der vom freigebenden Benutzer nicht an den anzeigenden Benutzer weitergegeben wurde. Inhalt kann gelöscht (oder beschädigt) werden, wenn der freigebende Benutzer Kacheln aus der Grafikquelle löscht, oder wenn ASMCU-Kacheln die Kacheln des freigebenden Benutzers löschen. Der Standardwert lautet 36 Prozent</span><span class="sxs-lookup"><span data-stu-id="7c8bf-p105">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c8bf-136"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-136"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7c8bf-137">int</span><span class="sxs-lookup"><span data-stu-id="7c8bf-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c8bf-138">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-138">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c8bf-139"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-139"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7c8bf-140">int</span><span class="sxs-lookup"><span data-stu-id="7c8bf-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c8bf-141">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-141">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c8bf-142"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-142"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7c8bf-143">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="7c8bf-143">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c8bf-144">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-144">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c8bf-145"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-145"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7c8bf-146">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="7c8bf-146">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c8bf-147">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-147">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c8bf-148"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-148"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7c8bf-149">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="7c8bf-149">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c8bf-150">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-150">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c8bf-151"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-151"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7c8bf-152">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="7c8bf-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c8bf-153">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-153">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c8bf-154"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-154"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7c8bf-155">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="7c8bf-155">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c8bf-p106">Optimaler Wert für die relative unidirektionale Verzögerung zwischen den beiden Medienendpunkten, die in die Anwendungsfreigabe eingebunden sind. Dieser Wert stellt den Latenzwert für einen einzelnen Hop dar. Der Standardwert beträgt 1,0 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-p106">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="7c8bf-159">Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-159">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c8bf-160"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-160"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7c8bf-161">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="7c8bf-161">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c8bf-p107">Optimaler Wert für die relative unidirektionale Verzögerung zwischen den beiden Medienendpunkten, die in die Anwendungsfreigabe eingebunden sind. Dieser Wert stellt den Latenzwert für einen einzelnen Hop dar. Der Standardwert beträgt 1,75 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-p107">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="7c8bf-165">Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-165">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c8bf-166"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-166"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7c8bf-167">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="7c8bf-167">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c8bf-168">Optimaler Wert für die durchschnittliche Verarbeitungslatenz für RDP-Kacheln im AS-Konferenzserver für die Dauer der Anzeigesitzung.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-168">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="7c8bf-169">Wartezeit ist der Zeitunterschied zwischen dem Codieren des Start Frames auf dem Server (je nach Szenario "miteinander" oder "MCU") und dem gleichen Start Frame, der im Viewer decodiert ist.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-169">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="7c8bf-p109">Ein hoher Durchschnittswert gibt eine längere Verzögerung bei der Darstellung an. Bei einem überlasteten Konferenzserver können längere durchschnittliche Verzögerungen auftreten. Der Standardwert beträgt 200 ms.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-p109">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="7c8bf-173">Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-173">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c8bf-174"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7c8bf-174"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7c8bf-175">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="7c8bf-175">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c8bf-176">Zulässiger Wert für die durchschnittliche Verarbeitungslatenz für RDP-Kacheln im AS-Konferenzserver für die Dauer der Anzeigesitzung.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-176">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="7c8bf-177">Wartezeit ist der Zeitunterschied zwischen dem Codieren des Start Frames auf dem Server (je nach Szenario "miteinander" oder "MCU") und dem gleichen Start Frame, der im Viewer decodiert ist.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-177">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="7c8bf-p111">Ein hoher Durchschnittswert gibt eine längere Verzögerung bei der Darstellung an. Bei einem überlasteten Konferenzserver können längere durchschnittliche Verzögerungen auftreten. Der Standardwert beträgt 200 ms.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-p111">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="7c8bf-181">Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7c8bf-181">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

