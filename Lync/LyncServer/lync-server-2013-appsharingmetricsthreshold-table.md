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
ms.openlocfilehash: e8c1acad5682e5c74c825f32de3fa6a37105234a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="5467b-102">AppSharingMetricsThreshold-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5467b-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5467b-103">_**Letztes Änderungsstand des Themas:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="5467b-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="5467b-p101">In der AppSharingMetricsThreshold-Tabelle sind die optimalen und zulässigen Werte für die QoE-Daten (Quality of Experience) enthalten, die für die Anwendungsfreigabe verwendet werden. Diese Schwellenwerte werden verwendet, um zu ermitteln, ob die Anwendungsfreigabemöglichkeiten als schlecht klassifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="5467b-p101">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing. These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="5467b-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5467b-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5467b-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5467b-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5467b-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5467b-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5467b-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="5467b-112">int</span><span class="sxs-lookup"><span data-stu-id="5467b-112">int</span></span></p></td>
<td><p><span data-ttu-id="5467b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5467b-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="5467b-114">Anruftyp, der getätigt wurde.</span><span class="sxs-lookup"><span data-stu-id="5467b-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5467b-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5467b-116">int</span><span class="sxs-lookup"><span data-stu-id="5467b-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5467b-p102">Optimale Bandbreitenbeschränkung für die Anwendungsfreigabe. Der Standardwert lautet 1000000.</span><span class="sxs-lookup"><span data-stu-id="5467b-p102">Optimal bandwidth limitation for application sharing. The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5467b-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5467b-120">int</span><span class="sxs-lookup"><span data-stu-id="5467b-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5467b-p103">Zulässige Bandbreitenbeschränkung für die Anwendungsfreigabe. Der Standardwert lautet 500000.</span><span class="sxs-lookup"><span data-stu-id="5467b-p103">Acceptable bandwidth limitation for application sharing. The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5467b-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5467b-124">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="5467b-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5467b-p104">Optimaler Prozentsatzwert für „beschädigte“ Kacheln bei der Klassifizierung der Anwendungsfreigabequalität. Dieser Wert gibt den Prozentsatz des Inhalts an, der vom freigebenden Benutzer nicht an den anzeigenden Benutzer weitergegeben wurde. Inhalt kann gelöscht (oder beschädigt) werden, wenn der freigebende Benutzer Kacheln aus der Grafikquelle löscht oder wenn ASMCU-Kacheln die Kacheln des freigebenden Benutzers löschen. Der Standardwert lautet 11 Prozent</span><span class="sxs-lookup"><span data-stu-id="5467b-p104">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5467b-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5467b-130">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="5467b-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5467b-p105">Optimaler Prozentsatzwert für „beschädigte“ Kacheln bei der Klassifizierung der Anwendungsfreigabequalität. Dieser Wert gibt den Prozentsatz des Inhalts an, der vom freigebenden Benutzer nicht an den anzeigenden Benutzer weitergegeben wurde. Inhalt kann gelöscht (oder beschädigt) werden, wenn der freigebende Benutzer Kacheln aus der Grafikquelle löscht, oder wenn ASMCU-Kacheln die Kacheln des freigebenden Benutzers löschen. Der Standardwert lautet 36 Prozent</span><span class="sxs-lookup"><span data-stu-id="5467b-p105">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5467b-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5467b-136">int</span><span class="sxs-lookup"><span data-stu-id="5467b-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5467b-137">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5467b-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5467b-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5467b-139">int</span><span class="sxs-lookup"><span data-stu-id="5467b-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5467b-140">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5467b-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5467b-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5467b-142">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="5467b-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5467b-143">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5467b-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5467b-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5467b-145">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="5467b-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5467b-146">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5467b-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5467b-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5467b-148">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="5467b-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5467b-149">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5467b-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5467b-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5467b-151">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="5467b-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5467b-152">Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5467b-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5467b-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5467b-154">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="5467b-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5467b-p106">Optimaler Wert für die relative unidirektionale Verzögerung zwischen den beiden Medienendpunkten, die in die Anwendungsfreigabe eingebunden sind. Dieser Wert stellt den Latenzwert für einen einzelnen Hop dar. Der Standardwert beträgt 1,0 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="5467b-p106">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="5467b-158">Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5467b-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5467b-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5467b-160">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="5467b-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5467b-p107">Optimaler Wert für die relative unidirektionale Verzögerung zwischen den beiden Medienendpunkten, die in die Anwendungsfreigabe eingebunden sind. Dieser Wert stellt den Latenzwert für einen einzelnen Hop dar. Der Standardwert beträgt 1,75 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="5467b-p107">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="5467b-164">Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5467b-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5467b-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5467b-166">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="5467b-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5467b-167">Optimaler Wert für die durchschnittliche Verarbeitungslatenz für RDP-Kacheln im AS-Konferenzserver für die Dauer der Anzeigesitzung.</span><span class="sxs-lookup"><span data-stu-id="5467b-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="5467b-168">Wartezeit ist der Zeitunterschied zwischen dem Codieren des Start Frames auf dem Server (je nach Szenario "miteinander" oder "MCU") und dem gleichen Start Frame, der im Viewer decodiert ist.</span><span class="sxs-lookup"><span data-stu-id="5467b-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="5467b-p109">Ein hoher Durchschnittswert gibt eine längere Verzögerung bei der Darstellung an. Bei einem überlasteten Konferenzserver können längere durchschnittliche Verzögerungen auftreten. Der Standardwert beträgt 200 ms.</span><span class="sxs-lookup"><span data-stu-id="5467b-p109">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="5467b-172">Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5467b-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5467b-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5467b-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5467b-174">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="5467b-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5467b-175">Zulässiger Wert für die durchschnittliche Verarbeitungslatenz für RDP-Kacheln im AS-Konferenzserver für die Dauer der Anzeigesitzung.</span><span class="sxs-lookup"><span data-stu-id="5467b-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="5467b-176">Wartezeit ist der Zeitunterschied zwischen dem Codieren des Start Frames auf dem Server (je nach Szenario "miteinander" oder "MCU") und dem gleichen Start Frame, der im Viewer decodiert ist.</span><span class="sxs-lookup"><span data-stu-id="5467b-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="5467b-p111">Ein hoher Durchschnittswert gibt eine längere Verzögerung bei der Darstellung an. Bei einem überlasteten Konferenzserver können längere durchschnittliche Verzögerungen auftreten. Der Standardwert beträgt 200 ms.</span><span class="sxs-lookup"><span data-stu-id="5467b-p111">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="5467b-180">Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5467b-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

