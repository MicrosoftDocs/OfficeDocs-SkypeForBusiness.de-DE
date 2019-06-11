---
title: 'Lync Server 2013: Medienansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d930f3beeeddb5c5582f41c44f1c68ff7f21f18d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="96246-102">Medienansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96246-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96246-103">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="96246-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="96246-104">In der medialinie-Ansicht werden Informationen zu jeder medienzeile in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="96246-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="96246-105">Eine Audiositzung enthält in der Regel eine Audio-medienzeile.</span><span class="sxs-lookup"><span data-stu-id="96246-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="96246-106">Eine Audio-und Video (A/V)-Sitzung enthält in der Regel eine Audio-medienzeile und eine Video medienzeile. die Sitzung kann jedoch zwei Video Medien Linien enthalten, wenn ein Konferenzgerät verwendet wird oder wenn die Katalogansicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="96246-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="96246-107">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="96246-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96246-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="96246-108">Column</span></span></th>
<th><span data-ttu-id="96246-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="96246-109">Data Type</span></span></th>
<th><span data-ttu-id="96246-110">Details</span><span class="sxs-lookup"><span data-stu-id="96246-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96246-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="96246-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="96246-112">datetime</span><span class="sxs-lookup"><span data-stu-id="96246-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="96246-113">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="96246-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="96246-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="96246-115">int</span><span class="sxs-lookup"><span data-stu-id="96246-115">int</span></span></p></td>
<td><p><span data-ttu-id="96246-116">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="96246-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="96246-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="96246-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="96246-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="96246-119">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="96246-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="96246-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="96246-121">int</span><span class="sxs-lookup"><span data-stu-id="96246-121">int</span></span></p></td>
<td><p><span data-ttu-id="96246-122">Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der unter Bits-Flags für den Aufrufer beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="96246-122">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="96246-123">Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="96246-123">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="96246-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="96246-125">int</span><span class="sxs-lookup"><span data-stu-id="96246-125">int</span></span></p></td>
<td><p><span data-ttu-id="96246-126">Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der in den Bits-Flags für den aufgerufenen beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="96246-126">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="96246-127">Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="96246-127">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-128">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="96246-128">Security</span></span></p></td>
<td><p><span data-ttu-id="96246-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="96246-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="96246-130">Verwendetes Sicherheitsprofil</span><span class="sxs-lookup"><span data-stu-id="96246-130">Security profile in use.</span></span> <span data-ttu-id="96246-131">0 ist None, 1 ist SRTP, 2 ist v1.</span><span class="sxs-lookup"><span data-stu-id="96246-131">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-132">Transport</span><span class="sxs-lookup"><span data-stu-id="96246-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="96246-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="96246-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="96246-134">Transporttyp.</span><span class="sxs-lookup"><span data-stu-id="96246-134">Transport type.</span></span> <span data-ttu-id="96246-135">0 ist UDP, 1 ist TCP.</span><span class="sxs-lookup"><span data-stu-id="96246-135">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="96246-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="96246-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="96246-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="96246-138">Die IP-Adresse des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="96246-138">IP address of the caller.</span></span> <span data-ttu-id="96246-139">Dies kann eine IPv4-oder IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="96246-139">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="96246-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="96246-141">int</span><span class="sxs-lookup"><span data-stu-id="96246-141">int</span></span></p></td>
<td><p><span data-ttu-id="96246-142">Der vom Aufrufer verwendete Port.</span><span class="sxs-lookup"><span data-stu-id="96246-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="96246-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="96246-144">bit</span><span class="sxs-lookup"><span data-stu-id="96246-144">bit</span></span></p></td>
<td><p><span data-ttu-id="96246-145">Gibt an, ob sich der Anrufer innerhalb des Organisationsnetzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="96246-145">Indicates whether or not the caller is inside the organization network.</span></span> <span data-ttu-id="96246-146">1 bedeutet, dass sich der Anrufer innerhalb des Unternehmensnetzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="96246-146">1 means that the caller is inside the enterprise network.</span></span> <span data-ttu-id="96246-147">0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="96246-147">0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="96246-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="96246-149">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="96246-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="96246-150">Mac-Adresse der vom Anrufer verwendeten Netzwerkschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="96246-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="96246-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="96246-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="96246-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="96246-153">Die IP-Adresse des A/V-Edgedienst, der vom Aufrufer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="96246-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="96246-154">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="96246-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="96246-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="96246-156">int</span><span class="sxs-lookup"><span data-stu-id="96246-156">int</span></span></p></td>
<td><p><span data-ttu-id="96246-157">Der Port des A/V-Edgedienst, der vom Aufrufer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="96246-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="96246-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="96246-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="96246-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="96246-160">Die IP-Adresse des Anrufers, wie er vom A/V-Edgedienst gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="96246-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="96246-161">Diese Adresse kann sich von der CallerIPAddr unterscheiden, wenn sich der Client beispielsweise hinter einem NAT befindet.</span><span class="sxs-lookup"><span data-stu-id="96246-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="96246-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="96246-163">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="96246-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="96246-164">Name des Aufnahmegeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="96246-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="96246-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="96246-166">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="96246-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="96246-167">Name des Render-Geräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="96246-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="96246-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="96246-169">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="96246-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="96246-170">Name des Aufnahmegeräte Treibers des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="96246-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="96246-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="96246-172">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="96246-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="96246-173">Name des Render-Gerätetreibers des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="96246-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="96246-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="96246-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="96246-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="96246-176">Beschreibung des WLAN-Treibers des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="96246-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="96246-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="96246-178">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="96246-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="96246-179">WLAN-Treiberversion des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="96246-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="96246-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="96246-181">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="96246-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="96246-182">Details zur Netzwerkverbindung des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="96246-182">Details of caller’s network connection.</span></span> <span data-ttu-id="96246-183">Weitere Informationen finden Sie <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="96246-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="96246-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="96246-185">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="96246-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="96246-186">Grundlegende Dienst Satzkennung, die von der WLAN-Verbindung der Anrufer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="96246-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="96246-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="96246-188">bit</span><span class="sxs-lookup"><span data-stu-id="96246-188">bit</span></span></p></td>
<td><p><span data-ttu-id="96246-189">Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="96246-189">Indicates whether the caller connected over a virtual private network.</span></span> <span data-ttu-id="96246-190">1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.</span><span class="sxs-lookup"><span data-stu-id="96246-190">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="96246-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="96246-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="96246-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="96246-193">Die IP-Adresse des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="96246-193">IP address of the callee.</span></span> <span data-ttu-id="96246-194">Dies kann eine IPv4-oder IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="96246-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="96246-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="96246-196">int</span><span class="sxs-lookup"><span data-stu-id="96246-196">int</span></span></p></td>
<td><p><span data-ttu-id="96246-197">Port, der vom aufgerufenen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="96246-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="96246-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="96246-199">bit</span><span class="sxs-lookup"><span data-stu-id="96246-199">bit</span></span></p></td>
<td><p><span data-ttu-id="96246-200">Gibt an, ob sich der aufgerufene innerhalb des Unternehmensnetzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="96246-200">Indicates whether the callee is inside the enterprise network.</span></span> <span data-ttu-id="96246-201">1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass der Anrufer sich außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="96246-201">1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="96246-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="96246-203">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="96246-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="96246-204">Mac-Adresse der vom aufgerufenen verwendeten Netzwerkschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="96246-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="96246-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="96246-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="96246-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="96246-207">Die IP-Adresse des A/V-Edgedienst, der vom aufgerufenen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="96246-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="96246-208">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="96246-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="96246-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="96246-210">int</span><span class="sxs-lookup"><span data-stu-id="96246-210">int</span></span></p></td>
<td><p><span data-ttu-id="96246-211">Port, der für den A/V-Edgedienst verwendet wird, der vom aufgerufenen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="96246-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="96246-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="96246-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="96246-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="96246-214">Die IP-Adresse des Betreibers, wie vom A/V-Edgedienst gemeldet.</span><span class="sxs-lookup"><span data-stu-id="96246-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="96246-215">Diese Adresse kann sich von der CalleeIPAddr unterscheiden, wenn sich der Client beispielsweise hinter einem NAT befindet.</span><span class="sxs-lookup"><span data-stu-id="96246-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="96246-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="96246-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="96246-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="96246-218">Der Name des Erfassungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="96246-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="96246-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="96246-220">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="96246-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="96246-221">Name des Render-Geräts.</span><span class="sxs-lookup"><span data-stu-id="96246-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="96246-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="96246-223">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="96246-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="96246-224">Der Name des Capture-Gerätetreibers des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="96246-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="96246-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="96246-226">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="96246-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="96246-227">Der Name des Render-Gerätetreibers des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="96246-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="96246-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="96246-229">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="96246-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="96246-230">Beschreibung des WLAN-Treibers des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="96246-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="96246-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="96246-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="96246-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="96246-233">WLAN-Treiberversion des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="96246-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="96246-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="96246-235">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="96246-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="96246-236">Details zur Netzwerkverbindung des berufenen.</span><span class="sxs-lookup"><span data-stu-id="96246-236">Details of callee’s network connection.</span></span> <span data-ttu-id="96246-237">Weitere Informationen finden Sie <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="96246-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="96246-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="96246-239">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="96246-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="96246-240">Grundlegende Dienst Satz-ID, die von der WLAN-Verbindung des berufenen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="96246-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="96246-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="96246-242">bit</span><span class="sxs-lookup"><span data-stu-id="96246-242">bit</span></span></p></td>
<td><p><span data-ttu-id="96246-243">Gibt an, ob der aufgerufene über ein virtuelles privates Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="96246-243">Indicates whether the callee connected over a virtual private network.</span></span> <span data-ttu-id="96246-244">1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.</span><span class="sxs-lookup"><span data-stu-id="96246-244">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="96246-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="96246-246">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="96246-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="96246-247">Schmalband-Konversations-Mos der audiositzungen (basierend auf beiden Audiostreams).</span><span class="sxs-lookup"><span data-stu-id="96246-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="96246-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="96246-249">int</span><span class="sxs-lookup"><span data-stu-id="96246-249">int</span></span></p></td>
<td><p><span data-ttu-id="96246-250">Hierbei handelt es sich um die tatsächliche Bandbreite, die auf den angegebenen Send-Seitenstrom angewendet wird, wobei verschiedene Richtlinieneinstellungen angegeben werden (Turn, API, SDP, Richtlinien Server usw.).</span><span class="sxs-lookup"><span data-stu-id="96246-250">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.).</span></span> <span data-ttu-id="96246-251">Dies sollte nicht mit der effektiven Bandbreite verwechselt werden, da auf der Grundlage der Bandbreitenschätzung eine geringere effektive Bandbreite vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="96246-251">This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="96246-252">Dies ist im Grunde die maximale Bandbreite, die der sendedatenstrom sperren kann, wenn die Bandbreite geschätzt wird.</span><span class="sxs-lookup"><span data-stu-id="96246-252">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="96246-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="96246-254">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="96246-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="96246-255">Die Quelle des verhängten Bandbreitenlimits.</span><span class="sxs-lookup"><span data-stu-id="96246-255">Source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="96246-256">Es wird beschrieben, woher die Bandbreitengrenze stammt (beispielsweise "Richtlinienserver", "Server umwandeln" oder "Modalität").</span><span class="sxs-lookup"><span data-stu-id="96246-256">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-257">Anrufer</span><span class="sxs-lookup"><span data-stu-id="96246-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="96246-258">bit</span><span class="sxs-lookup"><span data-stu-id="96246-258">bit</span></span></p></td>
<td><p><span data-ttu-id="96246-259">Gibt an, ob Metriken des Anrufers empfangen wurden; 1 ist ja, 0 ist Nein.</span><span class="sxs-lookup"><span data-stu-id="96246-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-260">Callee</span><span class="sxs-lookup"><span data-stu-id="96246-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="96246-261">bit</span><span class="sxs-lookup"><span data-stu-id="96246-261">bit</span></span></p></td>
<td><p><span data-ttu-id="96246-262">Gibt an, ob Metriken vom Anrufempfänger empfangen wurden; 1 ist ja, 0 ist Nein.</span><span class="sxs-lookup"><span data-stu-id="96246-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="96246-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="96246-264">bit</span><span class="sxs-lookup"><span data-stu-id="96246-264">bit</span></span></p></td>
<td><p><span data-ttu-id="96246-265">Gibt an, ob es sich bei dem Bericht um einen Teil des Anrufs oder um einen vollständigen Anruf handelt.</span><span class="sxs-lookup"><span data-stu-id="96246-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="96246-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="96246-267">bit</span><span class="sxs-lookup"><span data-stu-id="96246-267">bit</span></span></p></td>
<td><p><span data-ttu-id="96246-268">Gibt an, ob ein Anruf als schlechter Anruf (1) oder als guter Anruf (0) klassifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="96246-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96246-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="96246-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="96246-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="96246-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="96246-271">Gibt an, ob der Anrufer über das Ice-Protokoll (Internet Connectivity Establishment) mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="96246-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96246-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="96246-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="96246-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="96246-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="96246-274">Gibt an, ob der Benutzer die Verbindung mit dem Netzwerk mit dem ICE-Protokoll (Internet Connectivity Establishment) aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="96246-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

