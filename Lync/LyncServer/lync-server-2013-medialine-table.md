---
title: 'Lync Server 2013: MediaLine-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7488aa258fd30c2f9b519806dc84f9d897a08656
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="9ae23-102">MediaLine-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ae23-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ae23-103">_**Letztes Änderungsdatum des Themas:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="9ae23-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="9ae23-104">Jeder Datensatz stellt eine medienzeile dar.</span><span class="sxs-lookup"><span data-stu-id="9ae23-104">Each record represents one media line.</span></span> <span data-ttu-id="9ae23-105">(Eine Audiositzung enthält in der Regel eine Audio-medienzeile.</span><span class="sxs-lookup"><span data-stu-id="9ae23-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="9ae23-106">Eine Audio-und Video (A/V)-Sitzung enthält in der Regel eine Audio-Medien Linie und eine Video Medien Linie, obwohl die Sitzung zwei Video Medien Linien enthalten kann, wenn ein Konferenzgerät verwendet wird oder wenn die Katalogansicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9ae23-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ae23-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9ae23-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9ae23-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9ae23-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-112">datetime</span><span class="sxs-lookup"><span data-stu-id="9ae23-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="9ae23-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9ae23-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="9ae23-114">Wird in der <a href="lync-server-2013-session-table.md">Session-Tabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="9ae23-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-116">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-116">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-117">Primary</span><span class="sxs-lookup"><span data-stu-id="9ae23-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="9ae23-118">Wird in der <a href="lync-server-2013-session-table.md">Session-Tabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="9ae23-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="9ae23-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9ae23-121">Primary</span><span class="sxs-lookup"><span data-stu-id="9ae23-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="9ae23-122">0 ist Haupt-Audio, 1 ist das Hauptvideo, und 2 ist ein Panorama Video, 3 ist die Anwendung/Desktop-Freigabe.</span><span class="sxs-lookup"><span data-stu-id="9ae23-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="9ae23-123">Diese Bezeichnung muss innerhalb einer einzelnen Sitzung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="9ae23-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="9ae23-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ae23-126">Diese Spalte ist vorhanden, wird aber in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="9ae23-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="9ae23-127">Informationen zur für eine medienzeile verwendeten Konnektivität werden in den Spalten CallerConnectivityICE und CalleeConnectivityICE erfasst.</span><span class="sxs-lookup"><span data-stu-id="9ae23-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-129">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ae23-130">Informationen über das in Bits-Flags beschriebene Verfahren zum interaktiven Verbindungsaufbau (ICE).</span><span class="sxs-lookup"><span data-stu-id="9ae23-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="9ae23-131">Ausführliche Informationen finden Sie in der <em>Spezifikation für Quality of Experience Monitoring Server Protocol</em>, die zum Download zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="9ae23-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-133">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ae23-134">Identisch mit CallerIceWarningFlags, aber auf der aufgerufenen Seite.</span><span class="sxs-lookup"><span data-stu-id="9ae23-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="9ae23-135">Ausführliche Informationen finden Sie in der <em>Spezifikation für Quality of Experience Monitoring Server Protocol</em>, die zum Download zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="9ae23-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-136"><strong>Sicherheit</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="9ae23-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ae23-138">Das verwendete Sicherheitsprofil.</span><span class="sxs-lookup"><span data-stu-id="9ae23-138">The security profile in use.</span></span> <span data-ttu-id="9ae23-139">0 ist None, 1 ist SRTP, 2 ist v1.</span><span class="sxs-lookup"><span data-stu-id="9ae23-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="9ae23-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ae23-142">0 ist UDP, 1 ist TCP.</span><span class="sxs-lookup"><span data-stu-id="9ae23-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-144">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-144">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-145">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-146">Die IP-Adresse des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="9ae23-146">IP Address of the caller.</span></span> <span data-ttu-id="9ae23-147">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9ae23-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-149">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ae23-150">Der vom Aufrufer verwendete Port.</span><span class="sxs-lookup"><span data-stu-id="9ae23-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-152">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-152">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-153"> Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-154">Das Subnetz des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="9ae23-154">The subnet of the caller.</span></span> <span data-ttu-id="9ae23-155">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9ae23-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-157">bit</span><span class="sxs-lookup"><span data-stu-id="9ae23-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ae23-158">1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="9ae23-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-160">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-160">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-161">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-162">Die Mac-Adresse des Anrufers, auf die von der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9ae23-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-164">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-164">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-165">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-166">Die IP-Adresse des vom Aufrufer verwendeten lync Server A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="9ae23-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="9ae23-167">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9ae23-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-169">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ae23-170">Port, der vom Anrufer für den A/V-Edgedienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9ae23-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-172">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-172">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-173">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-174">Das vom Anrufer verwendete Aufnahmegerät.</span><span class="sxs-lookup"><span data-stu-id="9ae23-174">Capture device used by the caller.</span></span> <span data-ttu-id="9ae23-175">Wird in der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="9ae23-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-177">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-177">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-178">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-179">Vom Aufrufer verwendetes Render-Gerät.</span><span class="sxs-lookup"><span data-stu-id="9ae23-179">Render device used by caller.</span></span> <span data-ttu-id="9ae23-180">Wird in der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="9ae23-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-182">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-182">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-183">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-184">Treiber für das Aufnahmegerät des Anrufers, auf das von der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9ae23-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-186">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-186">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-187">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-188">Treiber für das Render-Gerät des Anrufers, auf das von der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9ae23-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="9ae23-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9ae23-191">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-192">Gibt an, wie der Anrufer mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="9ae23-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="9ae23-193">Werte werden <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a>abgerufen.</span><span class="sxs-lookup"><span data-stu-id="9ae23-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="9ae23-194">Typische Werte sind 0 für eine kabelgebundene Verbindung "1 für eine WLAN-Verbindung; und 3 für eine Ethernet-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="9ae23-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-196">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-196">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-197">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-198">BSSID des Anrufers, wenn Wireless verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9ae23-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="9ae23-199">Referenziert aus der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ae23-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-201">bit</span><span class="sxs-lookup"><span data-stu-id="9ae23-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9ae23-202">Der Link des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="9ae23-202">The caller's link.</span></span> <span data-ttu-id="9ae23-203">1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.</span><span class="sxs-lookup"><span data-stu-id="9ae23-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-205">Decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="9ae23-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9ae23-206">Die Netzwerkverbindungsgeschwindigkeit in BPS für den Endpunkt des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="9ae23-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-208">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-208">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-209">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-210">Die IP-Adresse des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="9ae23-210">IP Address of the call receiver.</span></span> <span data-ttu-id="9ae23-211">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9ae23-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-213">bit</span><span class="sxs-lookup"><span data-stu-id="9ae23-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9ae23-214">Der vom Anrufempfänger verwendete Port.</span><span class="sxs-lookup"><span data-stu-id="9ae23-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-216">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-216">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-217">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-218">Subnetz der aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="9ae23-218">Subnet of callee.</span></span> <span data-ttu-id="9ae23-219">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9ae23-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-221">bit</span><span class="sxs-lookup"><span data-stu-id="9ae23-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ae23-222">1 bedeutet, dass der Anrufempfänger sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass der Anrufempfänger sich außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="9ae23-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-224">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-224">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-225">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-226">Mac-Adresse des angerufenen</span><span class="sxs-lookup"><span data-stu-id="9ae23-226">Callee Mac address.</span></span> <span data-ttu-id="9ae23-227">Wird in der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="9ae23-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-229">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-229">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-230">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-231">Die IP-Adresse des A/V-Edgedienst, der vom Empfänger des Anrufs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9ae23-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="9ae23-232">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9ae23-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-234">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ae23-235">Port, der vom Anrufempfänger für den A/V-Edgedienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9ae23-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-237">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-237">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-238">fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-239">Das vom Anrufempfänger verwendete Aufnahmegerät.</span><span class="sxs-lookup"><span data-stu-id="9ae23-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="9ae23-240">Wird in der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="9ae23-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-242">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-242">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-243">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-244">Render-Gerät, das vom Empfänger des Anrufs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9ae23-244">Render device used by the call receiver.</span></span> <span data-ttu-id="9ae23-245">Wird in der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="9ae23-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-247">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-247">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-248">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-249">Treiber für das Aufnahmegerät des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="9ae23-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="9ae23-250">Referenziert aus der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ae23-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9ae23-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9ae23-253">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-254">Treiber für das Render-Gerät des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="9ae23-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="9ae23-255">Referenziert aus der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ae23-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="9ae23-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9ae23-258">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-259">Gibt an, wie der aufgerufene mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="9ae23-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="9ae23-260">Werte werden <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a>abgerufen.</span><span class="sxs-lookup"><span data-stu-id="9ae23-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="9ae23-261">Typische Werte sind 0 für eine kabelgebundene Verbindung "1 für eine WLAN-Verbindung; und 3 für eine Ethernet-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="9ae23-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-263">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-263">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-264">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-265">BSSID des anrufempfängers, wenn Wireless verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9ae23-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="9ae23-266">Referenziert aus der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9ae23-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-268">bit</span><span class="sxs-lookup"><span data-stu-id="9ae23-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ae23-269">Link des anrufempfängers; 1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.</span><span class="sxs-lookup"><span data-stu-id="9ae23-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-271">Decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="9ae23-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ae23-272">Die Netzwerkverbindungsgeschwindigkeit in BPS für den Endpunkt des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="9ae23-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-274">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9ae23-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ae23-275">Schmalband-Konversations-Mos der audiositzungen (basierend auf beiden Audiostreams).</span><span class="sxs-lookup"><span data-stu-id="9ae23-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-277">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9ae23-278">Hierbei handelt es sich um die tatsächliche Bandbreite, die auf den angegebenen Send-Seitenstrom angewendet wird, wobei verschiedene Richtlinieneinstellungen angegeben werden (Turn, API, SDP, Richtlinien Server usw.).</span><span class="sxs-lookup"><span data-stu-id="9ae23-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="9ae23-279">Dies sollte nicht mit der effektiven Bandbreite verwechselt werden, da auf der Grundlage der Bandbreitenschätzung eine geringere effektive Bandbreite vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="9ae23-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="9ae23-280">Dies ist im Grunde die maximale Bandbreite, die der sendedatenstrom sperren kann, wenn die Bandbreite geschätzt wird.</span><span class="sxs-lookup"><span data-stu-id="9ae23-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-282">smallint</span><span class="sxs-lookup"><span data-stu-id="9ae23-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9ae23-283">Hierbei handelt es sich um die Quelle des verhängten Bandbreitenlimits.</span><span class="sxs-lookup"><span data-stu-id="9ae23-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="9ae23-284">Es wird beschrieben, woher die Bandbreitengrenze stammt ("Richtlinienserver", "Server umwandeln", "Modalität" usw.).</span><span class="sxs-lookup"><span data-stu-id="9ae23-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="9ae23-285">Wird in der <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource-Tabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="9ae23-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-286"><strong>Anrufer</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-287">bit</span><span class="sxs-lookup"><span data-stu-id="9ae23-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ae23-288">Gibt an, ob Metriken des Anrufers empfangen wurden; 1 ist ja, ein NULL-Wert ist "Nein".</span><span class="sxs-lookup"><span data-stu-id="9ae23-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-289"><strong>Callee</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-290">bit</span><span class="sxs-lookup"><span data-stu-id="9ae23-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ae23-291">Gibt an, ob Metriken vom Anrufempfänger empfangen wurden; 1 ist ja, ein NULL-Wert ist "Nein".</span><span class="sxs-lookup"><span data-stu-id="9ae23-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-293">bit</span><span class="sxs-lookup"><span data-stu-id="9ae23-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9ae23-294">Gibt an, ob der Bericht für einen Teil der Sitzung oder für die vollständige Sitzung gilt.</span><span class="sxs-lookup"><span data-stu-id="9ae23-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="9ae23-295">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9ae23-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-297">bit</span><span class="sxs-lookup"><span data-stu-id="9ae23-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9ae23-298">Gibt an, ob ein Anruf als schlechter Anruf (Wert 1) oder als guter Anruf (0) klassifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="9ae23-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="9ae23-299">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9ae23-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="9ae23-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9ae23-302">Gibt an, ob der Anrufer über das Ice-Protokoll (Internet Connectivity Establishment) mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="9ae23-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="9ae23-303">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9ae23-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="9ae23-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9ae23-306">Gibt an, ob der Anrufer über das Ice-Protokoll (Internet Connectivity Establishment) mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="9ae23-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="9ae23-307">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9ae23-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-309">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-309">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-310">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-311">Reflexive IP-Adresse des Benutzers, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="9ae23-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="9ae23-312">In Organisationen, die NAT verwenden (Netzwerkadressübersetzung), ist die reflexive IP-Adresse die IP-Adresse des Proxyservers.</span><span class="sxs-lookup"><span data-stu-id="9ae23-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="9ae23-313">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9ae23-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-315">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-315">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-316">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-317">Gerätebeschreibung für den WiFi-Treiber des Benutzers, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="9ae23-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="9ae23-318">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9ae23-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-320">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-320">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-321">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-322">Die Versionsnummer des WLAN-Treibers, der vom Nutzer, der den Anruf getätigt hat, verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="9ae23-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="9ae23-323">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9ae23-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-325">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-325">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-326">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-327">Reflexive IP-Adresse des Benutzers, der den Anruf erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="9ae23-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="9ae23-328">In Organisationen, die NAT verwenden (Netzwerkadressübersetzung), ist die reflexive IP-Adresse die IP-Adresse des Proxyservers.</span><span class="sxs-lookup"><span data-stu-id="9ae23-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="9ae23-329">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9ae23-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae23-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-331">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-331">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-332">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-333">Gerätebeschreibung für den WiFi-Treiber des Benutzers, der den Anruf erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="9ae23-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="9ae23-334">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9ae23-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae23-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9ae23-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9ae23-336">int</span><span class="sxs-lookup"><span data-stu-id="9ae23-336">int</span></span></p></td>
<td><p><span data-ttu-id="9ae23-337">Fremd</span><span class="sxs-lookup"><span data-stu-id="9ae23-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9ae23-338">Die Versionsnummer des WLAN-Treibers, der vom Nutzer, der den Anruf erhalten hat, verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="9ae23-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="9ae23-339">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9ae23-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

