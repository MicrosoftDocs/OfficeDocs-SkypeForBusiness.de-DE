---
title: 'Lync Server 2013: MediaLine-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4828f67614115eb4d6f46ab0a0a7c315e02d1924
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="236e5-102">MediaLine-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="236e5-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="236e5-103">_**Letztes Änderungsdatum des Themas:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="236e5-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="236e5-104">Jeder Datensatz stellt eine medienzeile dar.</span><span class="sxs-lookup"><span data-stu-id="236e5-104">Each record represents one media line.</span></span> <span data-ttu-id="236e5-105">(Eine Audiositzung enthält in der Regel eine Audio-medienzeile.</span><span class="sxs-lookup"><span data-stu-id="236e5-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="236e5-106">Eine Audio-und Video (A/V)-Sitzung enthält in der Regel eine Audio-Medien Linie und eine Video Medien Linie, obwohl die Sitzung zwei Video Medien Linien enthalten kann, wenn ein Konferenzgerät verwendet wird oder wenn die Katalogansicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="236e5-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="236e5-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="236e5-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="236e5-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="236e5-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="236e5-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-112">datetime</span><span class="sxs-lookup"><span data-stu-id="236e5-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="236e5-113">Primary</span><span class="sxs-lookup"><span data-stu-id="236e5-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="236e5-114">Wird in der <a href="lync-server-2013-session-table.md">Session-Tabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="236e5-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-116">int</span><span class="sxs-lookup"><span data-stu-id="236e5-116">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-117">Primary</span><span class="sxs-lookup"><span data-stu-id="236e5-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="236e5-118">Wird in der <a href="lync-server-2013-session-table.md">Session-Tabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="236e5-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="236e5-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="236e5-121">Primary</span><span class="sxs-lookup"><span data-stu-id="236e5-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="236e5-122">0 ist Haupt-Audio, 1 ist das Hauptvideo, und 2 ist ein Panorama Video, 3 ist die Anwendung/Desktop-Freigabe.</span><span class="sxs-lookup"><span data-stu-id="236e5-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="236e5-123">Diese Bezeichnung muss innerhalb einer einzelnen Sitzung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="236e5-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="236e5-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="236e5-126">Diese Spalte ist vorhanden, wird aber in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="236e5-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="236e5-127">Informationen zur für eine medienzeile verwendeten Konnektivität werden in den Spalten CallerConnectivityICE und CalleeConnectivityICE erfasst.</span><span class="sxs-lookup"><span data-stu-id="236e5-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-129">int</span><span class="sxs-lookup"><span data-stu-id="236e5-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="236e5-130">Informationen über das in Bits-Flags beschriebene Verfahren zum interaktiven Verbindungsaufbau (ICE).</span><span class="sxs-lookup"><span data-stu-id="236e5-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="236e5-131">Ausführliche Informationen finden Sie in der <em>Spezifikation für Quality of Experience Monitoring Server Protocol</em>, die zum Download zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="236e5-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-133">int</span><span class="sxs-lookup"><span data-stu-id="236e5-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="236e5-134">Identisch mit CallerIceWarningFlags, aber auf der aufgerufenen Seite.</span><span class="sxs-lookup"><span data-stu-id="236e5-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="236e5-135">Ausführliche Informationen finden Sie in der <em>Spezifikation für Quality of Experience Monitoring Server Protocol</em>, die zum Download zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="236e5-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-136"><strong>Sicherheit</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="236e5-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="236e5-138">Das verwendete Sicherheitsprofil.</span><span class="sxs-lookup"><span data-stu-id="236e5-138">The security profile in use.</span></span> <span data-ttu-id="236e5-139">0 ist None, 1 ist SRTP, 2 ist v1.</span><span class="sxs-lookup"><span data-stu-id="236e5-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="236e5-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="236e5-142">0 ist UDP, 1 ist TCP.</span><span class="sxs-lookup"><span data-stu-id="236e5-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-144">int</span><span class="sxs-lookup"><span data-stu-id="236e5-144">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-145">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-146">Die IP-Adresse des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="236e5-146">IP Address of the caller.</span></span> <span data-ttu-id="236e5-147">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="236e5-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-149">int</span><span class="sxs-lookup"><span data-stu-id="236e5-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="236e5-150">Der vom Aufrufer verwendete Port.</span><span class="sxs-lookup"><span data-stu-id="236e5-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-152">int</span><span class="sxs-lookup"><span data-stu-id="236e5-152">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-153"> Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-154">Das Subnetz des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="236e5-154">The subnet of the caller.</span></span> <span data-ttu-id="236e5-155">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="236e5-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-157">bit</span><span class="sxs-lookup"><span data-stu-id="236e5-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="236e5-158">1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="236e5-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-160">int</span><span class="sxs-lookup"><span data-stu-id="236e5-160">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-161">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-162">Die Mac-Adresse des Anrufers, auf die von der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="236e5-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-164">int</span><span class="sxs-lookup"><span data-stu-id="236e5-164">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-165">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-166">Die IP-Adresse des vom Aufrufer verwendeten lync Server A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="236e5-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="236e5-167">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="236e5-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-169">int</span><span class="sxs-lookup"><span data-stu-id="236e5-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="236e5-170">Port, der vom Anrufer für den A/V-Edgedienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="236e5-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-172">int</span><span class="sxs-lookup"><span data-stu-id="236e5-172">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-173">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-174">Das vom Anrufer verwendete Aufnahmegerät.</span><span class="sxs-lookup"><span data-stu-id="236e5-174">Capture device used by the caller.</span></span> <span data-ttu-id="236e5-175">Wird in der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="236e5-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-177">int</span><span class="sxs-lookup"><span data-stu-id="236e5-177">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-178">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-179">Vom Aufrufer verwendetes Render-Gerät.</span><span class="sxs-lookup"><span data-stu-id="236e5-179">Render device used by caller.</span></span> <span data-ttu-id="236e5-180">Wird in der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="236e5-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-182">int</span><span class="sxs-lookup"><span data-stu-id="236e5-182">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-183">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-184">Treiber für das Aufnahmegerät des Anrufers, auf das von der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="236e5-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-186">int</span><span class="sxs-lookup"><span data-stu-id="236e5-186">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-187">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-188">Treiber für das Render-Gerät des Anrufers, auf das von der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="236e5-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="236e5-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="236e5-191">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-192">Gibt an, wie der Anrufer mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="236e5-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="236e5-193">Werte werden <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a>abgerufen.</span><span class="sxs-lookup"><span data-stu-id="236e5-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="236e5-194">Typische Werte sind 0 für eine kabelgebundene Verbindung "1 für eine WLAN-Verbindung; und 3 für eine Ethernet-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="236e5-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-196">int</span><span class="sxs-lookup"><span data-stu-id="236e5-196">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-197">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-198">BSSID des Anrufers, wenn Wireless verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="236e5-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="236e5-199">Referenziert aus der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="236e5-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-201">bit</span><span class="sxs-lookup"><span data-stu-id="236e5-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="236e5-202">Der Link des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="236e5-202">The caller's link.</span></span> <span data-ttu-id="236e5-203">1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.</span><span class="sxs-lookup"><span data-stu-id="236e5-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-205">Decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="236e5-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="236e5-206">Die Netzwerkverbindungsgeschwindigkeit in BPS für den Endpunkt des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="236e5-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-208">int</span><span class="sxs-lookup"><span data-stu-id="236e5-208">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-209">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-210">Die IP-Adresse des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="236e5-210">IP Address of the call receiver.</span></span> <span data-ttu-id="236e5-211">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="236e5-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-213">bit</span><span class="sxs-lookup"><span data-stu-id="236e5-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="236e5-214">Der vom Anrufempfänger verwendete Port.</span><span class="sxs-lookup"><span data-stu-id="236e5-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-216">int</span><span class="sxs-lookup"><span data-stu-id="236e5-216">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-217">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-218">Subnetz der aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="236e5-218">Subnet of callee.</span></span> <span data-ttu-id="236e5-219">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="236e5-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-221">bit</span><span class="sxs-lookup"><span data-stu-id="236e5-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="236e5-222">1 bedeutet, dass der Anrufempfänger sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass der Anrufempfänger sich außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="236e5-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-224">int</span><span class="sxs-lookup"><span data-stu-id="236e5-224">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-225">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-226">Mac-Adresse des angerufenen</span><span class="sxs-lookup"><span data-stu-id="236e5-226">Callee Mac address.</span></span> <span data-ttu-id="236e5-227">Wird in der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="236e5-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-229">int</span><span class="sxs-lookup"><span data-stu-id="236e5-229">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-230">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-231">Die IP-Adresse des A/V-Edgedienst, der vom Empfänger des Anrufs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="236e5-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="236e5-232">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="236e5-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-234">int</span><span class="sxs-lookup"><span data-stu-id="236e5-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="236e5-235">Port, der vom Anrufempfänger für den A/V-Edgedienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="236e5-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-237">int</span><span class="sxs-lookup"><span data-stu-id="236e5-237">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-238">fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-239">Das vom Anrufempfänger verwendete Aufnahmegerät.</span><span class="sxs-lookup"><span data-stu-id="236e5-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="236e5-240">Wird in der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="236e5-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-242">int</span><span class="sxs-lookup"><span data-stu-id="236e5-242">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-243">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-244">Render-Gerät, das vom Empfänger des Anrufs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="236e5-244">Render device used by the call receiver.</span></span> <span data-ttu-id="236e5-245">Wird in der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="236e5-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-247">int</span><span class="sxs-lookup"><span data-stu-id="236e5-247">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-248">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-249">Treiber für das Aufnahmegerät des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="236e5-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="236e5-250">Referenziert aus der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="236e5-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="236e5-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="236e5-253">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-254">Treiber für das Render-Gerät des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="236e5-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="236e5-255">Referenziert aus der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="236e5-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="236e5-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="236e5-258">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-259">Gibt an, wie der aufgerufene mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="236e5-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="236e5-260">Werte werden <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a>abgerufen.</span><span class="sxs-lookup"><span data-stu-id="236e5-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="236e5-261">Typische Werte sind 0 für eine kabelgebundene Verbindung "1 für eine WLAN-Verbindung; und 3 für eine Ethernet-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="236e5-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-263">int</span><span class="sxs-lookup"><span data-stu-id="236e5-263">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-264">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-265">BSSID des anrufempfängers, wenn Wireless verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="236e5-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="236e5-266">Referenziert aus der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="236e5-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-268">bit</span><span class="sxs-lookup"><span data-stu-id="236e5-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="236e5-269">Link des anrufempfängers; 1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.</span><span class="sxs-lookup"><span data-stu-id="236e5-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-271">Decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="236e5-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="236e5-272">Die Netzwerkverbindungsgeschwindigkeit in BPS für den Endpunkt des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="236e5-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-274">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="236e5-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="236e5-275">Schmalband-Konversations-Mos der audiositzungen (basierend auf beiden Audiostreams).</span><span class="sxs-lookup"><span data-stu-id="236e5-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-277">int</span><span class="sxs-lookup"><span data-stu-id="236e5-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="236e5-278">Hierbei handelt es sich um die tatsächliche Bandbreite, die auf den angegebenen Send-Seitenstrom angewendet wird, wobei verschiedene Richtlinieneinstellungen angegeben werden (Turn, API, SDP, Richtlinien Server usw.).</span><span class="sxs-lookup"><span data-stu-id="236e5-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="236e5-279">Dies sollte nicht mit der effektiven Bandbreite verwechselt werden, da auf der Grundlage der Bandbreitenschätzung eine geringere effektive Bandbreite vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="236e5-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="236e5-280">Dies ist im Grunde die maximale Bandbreite, die der sendedatenstrom sperren kann, wenn die Bandbreite geschätzt wird.</span><span class="sxs-lookup"><span data-stu-id="236e5-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-282">smallint</span><span class="sxs-lookup"><span data-stu-id="236e5-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="236e5-283">Hierbei handelt es sich um die Quelle des verhängten Bandbreitenlimits.</span><span class="sxs-lookup"><span data-stu-id="236e5-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="236e5-284">Es wird beschrieben, woher die Bandbreitengrenze stammt ("Richtlinienserver", "Server umwandeln", "Modalität" usw.).</span><span class="sxs-lookup"><span data-stu-id="236e5-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="236e5-285">Wird in der <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource-Tabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="236e5-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-286"><strong>Anrufer</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-287">bit</span><span class="sxs-lookup"><span data-stu-id="236e5-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="236e5-288">Gibt an, ob Metriken des Anrufers empfangen wurden; 1 ist ja, ein NULL-Wert ist "Nein".</span><span class="sxs-lookup"><span data-stu-id="236e5-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-289"><strong>Callee</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-290">bit</span><span class="sxs-lookup"><span data-stu-id="236e5-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="236e5-291">Gibt an, ob Metriken vom Anrufempfänger empfangen wurden; 1 ist ja, ein NULL-Wert ist "Nein".</span><span class="sxs-lookup"><span data-stu-id="236e5-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-293">bit</span><span class="sxs-lookup"><span data-stu-id="236e5-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="236e5-294">Gibt an, ob der Bericht für einen Teil der Sitzung oder für die vollständige Sitzung gilt.</span><span class="sxs-lookup"><span data-stu-id="236e5-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="236e5-295">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="236e5-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-297">bit</span><span class="sxs-lookup"><span data-stu-id="236e5-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="236e5-298">Gibt an, ob ein Anruf als schlechter Anruf (Wert 1) oder als guter Anruf (0) klassifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="236e5-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="236e5-299">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="236e5-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="236e5-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="236e5-302">Gibt an, ob der Anrufer über das Ice-Protokoll (Internet Connectivity Establishment) mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="236e5-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="236e5-303">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="236e5-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="236e5-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="236e5-306">Gibt an, ob der Anrufer über das Ice-Protokoll (Internet Connectivity Establishment) mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="236e5-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="236e5-307">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="236e5-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-309">int</span><span class="sxs-lookup"><span data-stu-id="236e5-309">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-310">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-311">Reflexive IP-Adresse des Benutzers, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="236e5-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="236e5-312">In Organisationen, die NAT verwenden (Netzwerkadressübersetzung), ist die reflexive IP-Adresse die IP-Adresse des Proxyservers.</span><span class="sxs-lookup"><span data-stu-id="236e5-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="236e5-313">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="236e5-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-315">int</span><span class="sxs-lookup"><span data-stu-id="236e5-315">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-316">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-317">Gerätebeschreibung für den WiFi-Treiber des Benutzers, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="236e5-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="236e5-318">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="236e5-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-320">int</span><span class="sxs-lookup"><span data-stu-id="236e5-320">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-321">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-322">Die Versionsnummer des WLAN-Treibers, der vom Nutzer, der den Anruf getätigt hat, verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="236e5-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="236e5-323">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="236e5-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-325">int</span><span class="sxs-lookup"><span data-stu-id="236e5-325">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-326">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-327">Reflexive IP-Adresse des Benutzers, der den Anruf erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="236e5-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="236e5-328">In Organisationen, die NAT verwenden (Netzwerkadressübersetzung), ist die reflexive IP-Adresse die IP-Adresse des Proxyservers.</span><span class="sxs-lookup"><span data-stu-id="236e5-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="236e5-329">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="236e5-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="236e5-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-331">int</span><span class="sxs-lookup"><span data-stu-id="236e5-331">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-332">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-333">Gerätebeschreibung für den WiFi-Treiber des Benutzers, der den Anruf erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="236e5-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="236e5-334">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="236e5-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="236e5-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="236e5-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="236e5-336">int</span><span class="sxs-lookup"><span data-stu-id="236e5-336">int</span></span></p></td>
<td><p><span data-ttu-id="236e5-337">Fremd</span><span class="sxs-lookup"><span data-stu-id="236e5-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="236e5-338">Die Versionsnummer des WLAN-Treibers, der vom Nutzer, der den Anruf erhalten hat, verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="236e5-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="236e5-339">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="236e5-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

