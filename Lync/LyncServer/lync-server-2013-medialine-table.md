---
title: 'Lync Server 2013: medialinie-Tabelle'
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
ms.openlocfilehash: edf0e216d90af0d32a0e700661a653a13028e01a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="408d2-102">Medientabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="408d2-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="408d2-103">_**Letztes Änderungsstand des Themas:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="408d2-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="408d2-104">Jeder Datensatz stellt eine Medienleiste dar.</span><span class="sxs-lookup"><span data-stu-id="408d2-104">Each record represents one media line.</span></span> <span data-ttu-id="408d2-105">(Eine Audiositzung enthält normalerweise eine Audio-Medien-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="408d2-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="408d2-106">Eine Audio-und Video (A/V)-Sitzung enthält normalerweise eine Audiomedien-und eine Video medienleitung, obwohl die Sitzung zwei Video medienleitungen enthalten kann, wenn ein Konferenzgerät verwendet wird oder wenn die Galerieansicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="408d2-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="408d2-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="408d2-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="408d2-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="408d2-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="408d2-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="408d2-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="408d2-113">Primary</span><span class="sxs-lookup"><span data-stu-id="408d2-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="408d2-114">Referenziert aus der <a href="lync-server-2013-session-table.md">Session-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="408d2-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-116">int</span><span class="sxs-lookup"><span data-stu-id="408d2-116">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-117">Primary</span><span class="sxs-lookup"><span data-stu-id="408d2-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="408d2-118">Referenziert aus der <a href="lync-server-2013-session-table.md">Session-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="408d2-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="408d2-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="408d2-121">Primary</span><span class="sxs-lookup"><span data-stu-id="408d2-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="408d2-122">0 ist Haupt-Audio, 1 ist Hauptvideo, 2 ist Panorama Video, 3 ist Application/Desktop Sharing.</span><span class="sxs-lookup"><span data-stu-id="408d2-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="408d2-123">Diese Bezeichnung muss innerhalb einer einzelnen Sitzung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="408d2-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="408d2-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="408d2-126">Diese Spalte ist vorhanden, wird aber in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="408d2-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="408d2-127">Informationen zur für eine Medien Verbindung verwendeten Konnektivität werden in den Spalten CallerConnectivityICE und CalleeConnectivityICE erfasst.</span><span class="sxs-lookup"><span data-stu-id="408d2-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-129">int</span><span class="sxs-lookup"><span data-stu-id="408d2-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="408d2-130">Informationen zum unter Bits Flags beschriebenen Ice-Prozess (Interactive Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="408d2-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="408d2-131">Ausführliche Informationen finden Sie unter <em>Quality of Experience Monitoring Server Protocol Specification</em>, die zum Download bereit steht.</span><span class="sxs-lookup"><span data-stu-id="408d2-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-133">int</span><span class="sxs-lookup"><span data-stu-id="408d2-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="408d2-134">Identisch mit CallerIceWarningFlags, jedoch auf der Seite "angerufener".</span><span class="sxs-lookup"><span data-stu-id="408d2-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="408d2-135">Ausführliche Informationen finden Sie unter <em>Quality of Experience Monitoring Server Protocol Specification</em>, die zum Download bereit steht.</span><span class="sxs-lookup"><span data-stu-id="408d2-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-136"><strong>Sicherheit</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="408d2-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="408d2-138">Das verwendete Sicherheitsprofil.</span><span class="sxs-lookup"><span data-stu-id="408d2-138">The security profile in use.</span></span> <span data-ttu-id="408d2-139">0 ist KEINES, 1 ist SRTP, 2 ist V1.</span><span class="sxs-lookup"><span data-stu-id="408d2-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="408d2-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="408d2-142">0 ist UDP, 1 ist TCP.</span><span class="sxs-lookup"><span data-stu-id="408d2-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-144">int</span><span class="sxs-lookup"><span data-stu-id="408d2-144">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-145">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-146">Die IP-Adresse des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="408d2-146">IP Address of the caller.</span></span> <span data-ttu-id="408d2-147">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="408d2-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-149">int</span><span class="sxs-lookup"><span data-stu-id="408d2-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="408d2-150">Vom Anrufer verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="408d2-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-152">int</span><span class="sxs-lookup"><span data-stu-id="408d2-152">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-153"> Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-154">Das Subnetz des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="408d2-154">The subnet of the caller.</span></span> <span data-ttu-id="408d2-155">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="408d2-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-157">Bit</span><span class="sxs-lookup"><span data-stu-id="408d2-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="408d2-158">1 bedeutet, der Anrufer befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Anrufer befindet sich außerhalb davon.</span><span class="sxs-lookup"><span data-stu-id="408d2-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-160">int</span><span class="sxs-lookup"><span data-stu-id="408d2-160">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-161">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-162">Die Mac-Adresse des Anrufers, die von der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a>referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="408d2-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-164">int</span><span class="sxs-lookup"><span data-stu-id="408d2-164">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-165">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-166">Die IP-Adresse des vom Anrufer verwendeten lync Server A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="408d2-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="408d2-167">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="408d2-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-169">int</span><span class="sxs-lookup"><span data-stu-id="408d2-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="408d2-170">Port, der vom Aufrufer auf dem A/V-Edgedienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="408d2-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-172">int</span><span class="sxs-lookup"><span data-stu-id="408d2-172">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-173">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-174">Vom Anrufer verwendete Aufnahmegerät.</span><span class="sxs-lookup"><span data-stu-id="408d2-174">Capture device used by the caller.</span></span> <span data-ttu-id="408d2-175">Wird aus der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="408d2-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-177">int</span><span class="sxs-lookup"><span data-stu-id="408d2-177">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-178">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-179">Vom Aufrufer verwendetes Render-Gerät.</span><span class="sxs-lookup"><span data-stu-id="408d2-179">Render device used by caller.</span></span> <span data-ttu-id="408d2-180">Wird aus der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="408d2-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-182">int</span><span class="sxs-lookup"><span data-stu-id="408d2-182">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-183">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-184">Treiber für das Aufnahmegerät des Anrufers, auf das von der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="408d2-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-186">int</span><span class="sxs-lookup"><span data-stu-id="408d2-186">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-187">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-188">Treiber für das Render-Gerät des Anrufers, auf das von der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="408d2-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="408d2-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="408d2-191">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-192">Gibt an, wie der Anrufer mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="408d2-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="408d2-193">Werte werden <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a>abgerufen.</span><span class="sxs-lookup"><span data-stu-id="408d2-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="408d2-194">Typische Werte sind 0 für eine kabelgebundene Verbindung "1 für eine WLAN-Verbindung; und 3 für eine Ethernet-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="408d2-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-196">int</span><span class="sxs-lookup"><span data-stu-id="408d2-196">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-197">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-198">BSSID des Anrufers, wenn Wireless verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="408d2-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="408d2-199">Referenziert aus der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="408d2-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-201">Bit</span><span class="sxs-lookup"><span data-stu-id="408d2-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="408d2-202">Link des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="408d2-202">The caller's link.</span></span> <span data-ttu-id="408d2-203">1 ist VPN, 0 ist Nicht-VPN.</span><span class="sxs-lookup"><span data-stu-id="408d2-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-205">Decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="408d2-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="408d2-206">Die Netzwerkverbindungsgeschwindigkeit in BPS für den Endpunkt des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="408d2-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-208">int</span><span class="sxs-lookup"><span data-stu-id="408d2-208">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-209">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-210">IP-Adresse des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="408d2-210">IP Address of the call receiver.</span></span> <span data-ttu-id="408d2-211">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="408d2-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-213">Bit</span><span class="sxs-lookup"><span data-stu-id="408d2-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="408d2-214">Vom Anrufempfänger verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="408d2-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-216">int</span><span class="sxs-lookup"><span data-stu-id="408d2-216">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-217">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-218">Subnetz des angerufenen.</span><span class="sxs-lookup"><span data-stu-id="408d2-218">Subnet of callee.</span></span> <span data-ttu-id="408d2-219">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="408d2-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-221">Bit</span><span class="sxs-lookup"><span data-stu-id="408d2-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="408d2-222">1 bedeutet, dass sich der Anrufempfänger innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufempfänger außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="408d2-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-224">int</span><span class="sxs-lookup"><span data-stu-id="408d2-224">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-225">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-226">Mac-Adresse des angerufenen.</span><span class="sxs-lookup"><span data-stu-id="408d2-226">Callee Mac address.</span></span> <span data-ttu-id="408d2-227">Referenziert aus der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="408d2-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-229">int</span><span class="sxs-lookup"><span data-stu-id="408d2-229">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-230">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-231">Die IP-Adresse des vom Anrufempfänger verwendeten A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="408d2-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="408d2-232">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="408d2-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-234">int</span><span class="sxs-lookup"><span data-stu-id="408d2-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="408d2-235">Port, der vom Anrufempfänger im A/V-Edgedienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="408d2-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-237">int</span><span class="sxs-lookup"><span data-stu-id="408d2-237">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-238">fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-239">Vom Anrufempfänger verwendetes Aufnahmegerät.</span><span class="sxs-lookup"><span data-stu-id="408d2-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="408d2-240">Wird aus der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="408d2-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-242">int</span><span class="sxs-lookup"><span data-stu-id="408d2-242">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-243">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-244">Vom Anrufempfänger verwendetes Render-Gerät.</span><span class="sxs-lookup"><span data-stu-id="408d2-244">Render device used by the call receiver.</span></span> <span data-ttu-id="408d2-245">Wird aus der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="408d2-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-247">int</span><span class="sxs-lookup"><span data-stu-id="408d2-247">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-248">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-249">Treiber für das Aufnahmegerät des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="408d2-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="408d2-250">Referenziert aus der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="408d2-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="408d2-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="408d2-253">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-254">Treiber für das Render-Gerät des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="408d2-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="408d2-255">Referenziert aus der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="408d2-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="408d2-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="408d2-258">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-259">Gibt an, wie der angerufene mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="408d2-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="408d2-260">Werte werden <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a>abgerufen.</span><span class="sxs-lookup"><span data-stu-id="408d2-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="408d2-261">Typische Werte sind 0 für eine kabelgebundene Verbindung "1 für eine WLAN-Verbindung; und 3 für eine Ethernet-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="408d2-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-263">int</span><span class="sxs-lookup"><span data-stu-id="408d2-263">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-264">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-265">BSSID des angerufenen, wenn Wireless verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="408d2-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="408d2-266">Referenziert aus der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="408d2-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-268">Bit</span><span class="sxs-lookup"><span data-stu-id="408d2-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="408d2-269">Link des anrufempfängers; 1 ist virtuelles privates Netzwerk (VPN), 0 ist kein VPN.</span><span class="sxs-lookup"><span data-stu-id="408d2-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-271">Decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="408d2-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="408d2-272">Die Netzwerkverbindungsgeschwindigkeit in BPS für den Endpunkt des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="408d2-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-274">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="408d2-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="408d2-275">Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).</span><span class="sxs-lookup"><span data-stu-id="408d2-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-277">int</span><span class="sxs-lookup"><span data-stu-id="408d2-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="408d2-278">Hierbei handelt es sich um die tatsächliche Bandbreite, die für den angegebenen Sende seitigen Stream mit verschiedenen Richtlinieneinstellungen (Turn, API, SDP, Policy Server usw.) angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="408d2-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="408d2-279">Dies ist nicht mit der effektiven Bandbreite zu verwechseln, da aufgrund der Bandbreitenschätzung eine geringere effektive Bandbreite vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="408d2-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="408d2-280">Hierbei handelt es sich im Wesentlichen um die maximale Bandbreite, die der sendedatenstrom durch die Schätzung der Bandbreite für die Begrenzung von Beschränkungen ergreifen kann.</span><span class="sxs-lookup"><span data-stu-id="408d2-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-282">smallint</span><span class="sxs-lookup"><span data-stu-id="408d2-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="408d2-283">Dies ist die Quelle der Bandbreiten Obergrenze, die auferlegt wird.</span><span class="sxs-lookup"><span data-stu-id="408d2-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="408d2-284">In diesem Artikel wird beschrieben, woher die Bandbreitengrenze stammt ("Richtlinienserver", "Turn Server", "Modalität" usw.).</span><span class="sxs-lookup"><span data-stu-id="408d2-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="408d2-285">Referenziert aus der <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="408d2-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-286"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-287">Bit</span><span class="sxs-lookup"><span data-stu-id="408d2-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="408d2-288">Gibt an, ob Metriken vom Anrufer empfangen wurden; 1 ist ja, ein NULL-Wert ist Nein.</span><span class="sxs-lookup"><span data-stu-id="408d2-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-289"><strong>Aufgerufene</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-290">Bit</span><span class="sxs-lookup"><span data-stu-id="408d2-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="408d2-291">Gibt an, ob Metriken vom Anrufempfänger empfangen wurden; 1 ist ja, ein NULL-Wert ist Nein.</span><span class="sxs-lookup"><span data-stu-id="408d2-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-293">Bit</span><span class="sxs-lookup"><span data-stu-id="408d2-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="408d2-294">Gibt an, ob der Bericht für einen Teil der Sitzung oder für die gesamte Sitzung gilt.</span><span class="sxs-lookup"><span data-stu-id="408d2-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="408d2-295">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="408d2-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-297">Bit</span><span class="sxs-lookup"><span data-stu-id="408d2-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="408d2-298">Gibt an, ob ein Anruf als schlechter Anruf klassifiziert wurde (Wert 1) oder als guter Aufruf (0).</span><span class="sxs-lookup"><span data-stu-id="408d2-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="408d2-299">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="408d2-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="408d2-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="408d2-302">Gibt an, ob sich der Anrufer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.</span><span class="sxs-lookup"><span data-stu-id="408d2-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="408d2-303">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="408d2-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="408d2-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="408d2-306">Gibt an, ob sich der Anrufer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.</span><span class="sxs-lookup"><span data-stu-id="408d2-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="408d2-307">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="408d2-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-309">int</span><span class="sxs-lookup"><span data-stu-id="408d2-309">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-310">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-311">Reflexive IP-Adresse des Benutzers, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="408d2-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="408d2-312">In Organisationen, die NAT verwenden (Netzwerkadressübersetzung), ist die reflexive IP-Adresse die IP-Adresse des Proxyservers.</span><span class="sxs-lookup"><span data-stu-id="408d2-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="408d2-313">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="408d2-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-315">int</span><span class="sxs-lookup"><span data-stu-id="408d2-315">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-316">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-317">Gerätebeschreibung für den von dem Benutzer, der den Anruf getätigt hat, verwendeten WLAN-Treiber.</span><span class="sxs-lookup"><span data-stu-id="408d2-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="408d2-318">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="408d2-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-320">int</span><span class="sxs-lookup"><span data-stu-id="408d2-320">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-321">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-322">Versionsnummer des WLAN-Treibers, der von dem Benutzer, der den Anruf getätigt hat, verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="408d2-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="408d2-323">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="408d2-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-325">int</span><span class="sxs-lookup"><span data-stu-id="408d2-325">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-326">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-327">Reflexive IP-Adresse des Benutzers, der den Anruf empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="408d2-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="408d2-328">In Organisationen, die NAT verwenden (Netzwerkadressübersetzung), ist die reflexive IP-Adresse die IP-Adresse des Proxyservers.</span><span class="sxs-lookup"><span data-stu-id="408d2-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="408d2-329">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="408d2-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="408d2-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-331">int</span><span class="sxs-lookup"><span data-stu-id="408d2-331">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-332">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-333">Gerätebeschreibung für den von dem Benutzer, der den Anruf empfangen hat, verwendeten WLAN-Treiber.</span><span class="sxs-lookup"><span data-stu-id="408d2-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="408d2-334">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="408d2-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="408d2-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="408d2-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="408d2-336">int</span><span class="sxs-lookup"><span data-stu-id="408d2-336">int</span></span></p></td>
<td><p><span data-ttu-id="408d2-337">Fremd</span><span class="sxs-lookup"><span data-stu-id="408d2-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="408d2-338">Versionsnummer des WLAN-Treibers, der von dem Benutzer, der den Anruf empfangen hat, verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="408d2-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="408d2-339">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="408d2-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

