---
title: 'Lync Server 2013: medialinie-Tabelle'
description: 'Lync Server 2013: medialinie-Tabelle.'
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
ms.openlocfilehash: 2acea8e14ba0608d9ebf72a48f888bfc4501fae3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572111"
---
# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="95a05-103">Medientabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95a05-103">MediaLine table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95a05-104">_**Letztes Änderungsstand des Themas:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="95a05-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="95a05-105">Jeder Datensatz stellt eine Medienleiste dar.</span><span class="sxs-lookup"><span data-stu-id="95a05-105">Each record represents one media line.</span></span> <span data-ttu-id="95a05-106">(Eine Audiositzung enthält normalerweise eine Audio-Medien-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="95a05-106">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="95a05-107">Eine Audio-und Video (A/V)-Sitzung enthält normalerweise eine Audiomedien-und eine Video medienleitung, obwohl die Sitzung zwei Video medienleitungen enthalten kann, wenn ein Konferenzgerät verwendet wird oder wenn die Galerieansicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="95a05-107">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95a05-108"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="95a05-109"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="95a05-110"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="95a05-111"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95a05-112"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-113">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="95a05-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="95a05-114">Primary</span><span class="sxs-lookup"><span data-stu-id="95a05-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="95a05-115">Referenziert aus der <a href="lync-server-2013-session-table.md">Session-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="95a05-115">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-117">int</span><span class="sxs-lookup"><span data-stu-id="95a05-117">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-118">Primary</span><span class="sxs-lookup"><span data-stu-id="95a05-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="95a05-119">Referenziert aus der <a href="lync-server-2013-session-table.md">Session-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="95a05-119">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-120"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-120"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-121">tinyint</span><span class="sxs-lookup"><span data-stu-id="95a05-121">tinyint</span></span></p></td>
<td><p><span data-ttu-id="95a05-122">Primary</span><span class="sxs-lookup"><span data-stu-id="95a05-122">Primary</span></span></p></td>
<td><p><span data-ttu-id="95a05-123">0 ist Haupt-Audio, 1 ist Hauptvideo, 2 ist Panorama Video, 3 ist Application/Desktop Sharing.</span><span class="sxs-lookup"><span data-stu-id="95a05-123">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="95a05-124">Diese Bezeichnung muss innerhalb einer einzelnen Sitzung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="95a05-124">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-125"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-125"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-126">tinyint</span><span class="sxs-lookup"><span data-stu-id="95a05-126">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="95a05-127">Diese Spalte ist vorhanden, wird aber in Microsoft lync Server 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="95a05-127">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="95a05-128">Informationen zur für eine Medien Verbindung verwendeten Konnektivität werden in den Spalten CallerConnectivityICE und CalleeConnectivityICE erfasst.</span><span class="sxs-lookup"><span data-stu-id="95a05-128">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-129"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-129"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-130">int</span><span class="sxs-lookup"><span data-stu-id="95a05-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="95a05-131">Informationen zum unter Bits Flags beschriebenen Ice-Prozess (Interactive Connectivity Establishment).</span><span class="sxs-lookup"><span data-stu-id="95a05-131">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="95a05-132">Ausführliche Informationen finden Sie unter <em>Quality of Experience Monitoring Server Protocol Specification</em>, die zum Download bereit steht.</span><span class="sxs-lookup"><span data-stu-id="95a05-132">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-133"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-133"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-134">int</span><span class="sxs-lookup"><span data-stu-id="95a05-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="95a05-135">Identisch mit CallerIceWarningFlags, jedoch auf der Seite "angerufener".</span><span class="sxs-lookup"><span data-stu-id="95a05-135">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="95a05-136">Ausführliche Informationen finden Sie unter <em>Quality of Experience Monitoring Server Protocol Specification</em>, die zum Download bereit steht.</span><span class="sxs-lookup"><span data-stu-id="95a05-136">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-137"><strong>Sicherheit</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-137"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-138">tinyint</span><span class="sxs-lookup"><span data-stu-id="95a05-138">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="95a05-139">Das verwendete Sicherheitsprofil.</span><span class="sxs-lookup"><span data-stu-id="95a05-139">The security profile in use.</span></span> <span data-ttu-id="95a05-140">0 ist KEINES, 1 ist SRTP, 2 ist V1.</span><span class="sxs-lookup"><span data-stu-id="95a05-140">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-141"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-141"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-142">tinyint</span><span class="sxs-lookup"><span data-stu-id="95a05-142">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="95a05-143">0 ist UDP, 1 ist TCP.</span><span class="sxs-lookup"><span data-stu-id="95a05-143">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-144"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-144"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-145">int</span><span class="sxs-lookup"><span data-stu-id="95a05-145">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-146">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-147">Die IP-Adresse des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="95a05-147">IP Address of the caller.</span></span> <span data-ttu-id="95a05-148">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="95a05-148">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-149"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-149"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-150">int</span><span class="sxs-lookup"><span data-stu-id="95a05-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="95a05-151">Vom Anrufer verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="95a05-151">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-152"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-152"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-153">int</span><span class="sxs-lookup"><span data-stu-id="95a05-153">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-154"> Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-154"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-155">Das Subnetz des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="95a05-155">The subnet of the caller.</span></span> <span data-ttu-id="95a05-156">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="95a05-156">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-157"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-157"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-158">Bit</span><span class="sxs-lookup"><span data-stu-id="95a05-158">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="95a05-159">1 bedeutet, der Anrufer befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Anrufer befindet sich außerhalb davon.</span><span class="sxs-lookup"><span data-stu-id="95a05-159">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-160"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-160"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-161">int</span><span class="sxs-lookup"><span data-stu-id="95a05-161">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-162">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-163">Die Mac-Adresse des Anrufers, die von der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a>referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="95a05-163">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-164"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-164"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-165">int</span><span class="sxs-lookup"><span data-stu-id="95a05-165">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-166">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-167">Die IP-Adresse des vom Anrufer verwendeten lync Server A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="95a05-167">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="95a05-168">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="95a05-168">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-169"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-169"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-170">int</span><span class="sxs-lookup"><span data-stu-id="95a05-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="95a05-171">Port, der vom Aufrufer auf dem A/V-Edgedienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="95a05-171">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-172"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-172"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-173">int</span><span class="sxs-lookup"><span data-stu-id="95a05-173">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-174">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-175">Vom Anrufer verwendete Aufnahmegerät.</span><span class="sxs-lookup"><span data-stu-id="95a05-175">Capture device used by the caller.</span></span> <span data-ttu-id="95a05-176">Wird aus der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="95a05-176">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-177"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-177"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-178">int</span><span class="sxs-lookup"><span data-stu-id="95a05-178">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-179">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-179">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-180">Vom Aufrufer verwendetes Render-Gerät.</span><span class="sxs-lookup"><span data-stu-id="95a05-180">Render device used by caller.</span></span> <span data-ttu-id="95a05-181">Wird aus der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="95a05-181">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-182"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-182"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-183">int</span><span class="sxs-lookup"><span data-stu-id="95a05-183">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-184">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-185">Treiber für das Aufnahmegerät des Anrufers, auf das von der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="95a05-185">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-186"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-186"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-187">int</span><span class="sxs-lookup"><span data-stu-id="95a05-187">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-188">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-189">Treiber für das Render-Gerät des Anrufers, auf das von der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="95a05-189">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-190"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-190"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-191">tinyint</span><span class="sxs-lookup"><span data-stu-id="95a05-191">tinyint</span></span></p></td>
<td><p><span data-ttu-id="95a05-192">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-193">Gibt an, wie der Anrufer mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="95a05-193">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="95a05-194">Werte werden <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a>abgerufen.</span><span class="sxs-lookup"><span data-stu-id="95a05-194">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="95a05-195">Typische Werte sind 0 für eine kabelgebundene Verbindung "1 für eine WLAN-Verbindung; und 3 für eine Ethernet-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="95a05-195">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-196"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-196"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-197">int</span><span class="sxs-lookup"><span data-stu-id="95a05-197">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-198">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-199">BSSID des Anrufers, wenn Wireless verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="95a05-199">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="95a05-200">Referenziert aus der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="95a05-200">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-201"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-201"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-202">Bit</span><span class="sxs-lookup"><span data-stu-id="95a05-202">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="95a05-203">Link des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="95a05-203">The caller's link.</span></span> <span data-ttu-id="95a05-204">1 ist VPN, 0 ist Nicht-VPN.</span><span class="sxs-lookup"><span data-stu-id="95a05-204">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-205"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-205"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-206">Decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="95a05-206">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="95a05-207">Die Netzwerkverbindungsgeschwindigkeit in BPS für den Endpunkt des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="95a05-207">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-208"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-208"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-209">int</span><span class="sxs-lookup"><span data-stu-id="95a05-209">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-210">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-210">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-211">IP-Adresse des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="95a05-211">IP Address of the call receiver.</span></span> <span data-ttu-id="95a05-212">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="95a05-212">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-213"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-213"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-214">Bit</span><span class="sxs-lookup"><span data-stu-id="95a05-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="95a05-215">Vom Anrufempfänger verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="95a05-215">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-216"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-216"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-217">int</span><span class="sxs-lookup"><span data-stu-id="95a05-217">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-218">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-219">Subnetz des angerufenen.</span><span class="sxs-lookup"><span data-stu-id="95a05-219">Subnet of callee.</span></span> <span data-ttu-id="95a05-220">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="95a05-220">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-221"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-221"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-222">Bit</span><span class="sxs-lookup"><span data-stu-id="95a05-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="95a05-223">1 bedeutet, dass sich der Anrufempfänger innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufempfänger außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="95a05-223">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-224"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-224"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-225">int</span><span class="sxs-lookup"><span data-stu-id="95a05-225">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-226">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-226">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-227">Mac-Adresse des angerufenen.</span><span class="sxs-lookup"><span data-stu-id="95a05-227">Callee Mac address.</span></span> <span data-ttu-id="95a05-228">Referenziert aus der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="95a05-228">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-229"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-229"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-230">int</span><span class="sxs-lookup"><span data-stu-id="95a05-230">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-231">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-231">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-232">Die IP-Adresse des vom Anrufempfänger verwendeten A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="95a05-232">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="95a05-233">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="95a05-233">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-234"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-234"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-235">int</span><span class="sxs-lookup"><span data-stu-id="95a05-235">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="95a05-236">Port, der vom Anrufempfänger im A/V-Edgedienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="95a05-236">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-237"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-237"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-238">int</span><span class="sxs-lookup"><span data-stu-id="95a05-238">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-239">fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-239">foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-240">Vom Anrufempfänger verwendetes Aufnahmegerät.</span><span class="sxs-lookup"><span data-stu-id="95a05-240">Capture device used by the call receiver.</span></span> <span data-ttu-id="95a05-241">Wird aus der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="95a05-241">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-242"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-242"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-243">int</span><span class="sxs-lookup"><span data-stu-id="95a05-243">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-244">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-244">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-245">Vom Anrufempfänger verwendetes Render-Gerät.</span><span class="sxs-lookup"><span data-stu-id="95a05-245">Render device used by the call receiver.</span></span> <span data-ttu-id="95a05-246">Wird aus der <a href="lync-server-2013-device-table.md">Gerätetabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="95a05-246">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-247"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-247"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-248">int</span><span class="sxs-lookup"><span data-stu-id="95a05-248">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-249">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-249">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-250">Treiber für das Aufnahmegerät des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="95a05-250">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="95a05-251">Referenziert aus der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="95a05-251">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-252"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-252"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-253">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="95a05-253">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95a05-254">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-254">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-255">Treiber für das Render-Gerät des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="95a05-255">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="95a05-256">Referenziert aus der <a href="lync-server-2013-devicedriver-table.md">ACPITreiber-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="95a05-256">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-257"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-257"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-258">tinyint</span><span class="sxs-lookup"><span data-stu-id="95a05-258">tinyint</span></span></p></td>
<td><p><span data-ttu-id="95a05-259">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-259">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-260">Gibt an, wie der angerufene mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="95a05-260">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="95a05-261">Werte werden <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a>abgerufen.</span><span class="sxs-lookup"><span data-stu-id="95a05-261">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="95a05-262">Typische Werte sind 0 für eine kabelgebundene Verbindung "1 für eine WLAN-Verbindung; und 3 für eine Ethernet-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="95a05-262">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-263"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-263"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-264">int</span><span class="sxs-lookup"><span data-stu-id="95a05-264">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-265">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-265">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-266">BSSID des angerufenen, wenn Wireless verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="95a05-266">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="95a05-267">Referenziert aus der <a href="lync-server-2013-macaddress-table.md">macaddress-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="95a05-267">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-268"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-268"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-269">Bit</span><span class="sxs-lookup"><span data-stu-id="95a05-269">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="95a05-270">Link des anrufempfängers; 1 ist virtuelles privates Netzwerk (VPN), 0 ist kein VPN.</span><span class="sxs-lookup"><span data-stu-id="95a05-270">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-271"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-271"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-272">Decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="95a05-272">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="95a05-273">Die Netzwerkverbindungsgeschwindigkeit in BPS für den Endpunkt des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="95a05-273">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-274"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-274"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-275">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="95a05-275">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="95a05-276">Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).</span><span class="sxs-lookup"><span data-stu-id="95a05-276">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-277"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-277"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-278">int</span><span class="sxs-lookup"><span data-stu-id="95a05-278">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="95a05-279">Hierbei handelt es sich um die tatsächliche Bandbreite, die für den angegebenen Sende seitigen Stream mit verschiedenen Richtlinieneinstellungen (Turn, API, SDP, Policy Server usw.) angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="95a05-279">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="95a05-280">Dies ist nicht mit der effektiven Bandbreite zu verwechseln, da aufgrund der Bandbreitenschätzung eine geringere effektive Bandbreite vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="95a05-280">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="95a05-281">Hierbei handelt es sich im Wesentlichen um die maximale Bandbreite, die der sendedatenstrom durch die Schätzung der Bandbreite für die Begrenzung von Beschränkungen ergreifen kann.</span><span class="sxs-lookup"><span data-stu-id="95a05-281">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-282"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-282"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-283">smallint</span><span class="sxs-lookup"><span data-stu-id="95a05-283">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="95a05-284">Dies ist die Quelle der Bandbreiten Obergrenze, die auferlegt wird.</span><span class="sxs-lookup"><span data-stu-id="95a05-284">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="95a05-285">In diesem Artikel wird beschrieben, woher die Bandbreitengrenze stammt ("Richtlinienserver", "Turn Server", "Modalität" usw.).</span><span class="sxs-lookup"><span data-stu-id="95a05-285">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="95a05-286">Referenziert aus der <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="95a05-286">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-287"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-287"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-288">Bit</span><span class="sxs-lookup"><span data-stu-id="95a05-288">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="95a05-289">Gibt an, ob Metriken vom Anrufer empfangen wurden; 1 ist ja, ein NULL-Wert ist Nein.</span><span class="sxs-lookup"><span data-stu-id="95a05-289">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-290"><strong>Aufgerufene</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-290"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-291">Bit</span><span class="sxs-lookup"><span data-stu-id="95a05-291">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="95a05-292">Gibt an, ob Metriken vom Anrufempfänger empfangen wurden; 1 ist ja, ein NULL-Wert ist Nein.</span><span class="sxs-lookup"><span data-stu-id="95a05-292">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-293"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-293"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-294">Bit</span><span class="sxs-lookup"><span data-stu-id="95a05-294">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="95a05-295">Gibt an, ob der Bericht für einen Teil der Sitzung oder für die gesamte Sitzung gilt.</span><span class="sxs-lookup"><span data-stu-id="95a05-295">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="95a05-296">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="95a05-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-297"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-297"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-298">Bit</span><span class="sxs-lookup"><span data-stu-id="95a05-298">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="95a05-299">Gibt an, ob ein Anruf als schlechter Anruf klassifiziert wurde (Wert 1) oder als guter Aufruf (0).</span><span class="sxs-lookup"><span data-stu-id="95a05-299">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="95a05-300">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="95a05-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-301"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-301"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-302">tinyInt</span><span class="sxs-lookup"><span data-stu-id="95a05-302">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="95a05-303">Gibt an, ob sich der Anrufer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.</span><span class="sxs-lookup"><span data-stu-id="95a05-303">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="95a05-304">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="95a05-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-305"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-305"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-306">tinyint</span><span class="sxs-lookup"><span data-stu-id="95a05-306">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="95a05-307">Gibt an, ob sich der Anrufer mithilfe des ICE (Internet Connectivity Establishment)-Protokolls mit dem Netzwerk verbunden hat.</span><span class="sxs-lookup"><span data-stu-id="95a05-307">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="95a05-308">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="95a05-308">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-309"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-309"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-310">int</span><span class="sxs-lookup"><span data-stu-id="95a05-310">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-311">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-311">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-312">Reflexive IP-Adresse des Benutzers, der den Anruf getätigt hat.</span><span class="sxs-lookup"><span data-stu-id="95a05-312">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="95a05-313">In Organisationen, die NAT verwenden (Netzwerkadressübersetzung), ist die reflexive IP-Adresse die IP-Adresse des Proxyservers.</span><span class="sxs-lookup"><span data-stu-id="95a05-313">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="95a05-314">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="95a05-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-315"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-315"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-316">int</span><span class="sxs-lookup"><span data-stu-id="95a05-316">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-317">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-317">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-318">Gerätebeschreibung für den von dem Benutzer, der den Anruf getätigt hat, verwendeten WLAN-Treiber.</span><span class="sxs-lookup"><span data-stu-id="95a05-318">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="95a05-319">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="95a05-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-320"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-320"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-321">int</span><span class="sxs-lookup"><span data-stu-id="95a05-321">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-322">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-322">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-323">Versionsnummer des WLAN-Treibers, der von dem Benutzer, der den Anruf getätigt hat, verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="95a05-323">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="95a05-324">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="95a05-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-325"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-325"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-326">int</span><span class="sxs-lookup"><span data-stu-id="95a05-326">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-327">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-327">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-328">Reflexive IP-Adresse des Benutzers, der den Anruf empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="95a05-328">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="95a05-329">In Organisationen, die NAT verwenden (Netzwerkadressübersetzung), ist die reflexive IP-Adresse die IP-Adresse des Proxyservers.</span><span class="sxs-lookup"><span data-stu-id="95a05-329">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="95a05-330">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="95a05-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95a05-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-332">int</span><span class="sxs-lookup"><span data-stu-id="95a05-332">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-333">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-333">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-334">Gerätebeschreibung für den von dem Benutzer, der den Anruf empfangen hat, verwendeten WLAN-Treiber.</span><span class="sxs-lookup"><span data-stu-id="95a05-334">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="95a05-335">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="95a05-335">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95a05-336"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="95a05-336"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="95a05-337">int</span><span class="sxs-lookup"><span data-stu-id="95a05-337">int</span></span></p></td>
<td><p><span data-ttu-id="95a05-338">Fremd</span><span class="sxs-lookup"><span data-stu-id="95a05-338">Foreign</span></span></p></td>
<td><p><span data-ttu-id="95a05-339">Versionsnummer des WLAN-Treibers, der von dem Benutzer, der den Anruf empfangen hat, verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="95a05-339">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="95a05-340">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="95a05-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

