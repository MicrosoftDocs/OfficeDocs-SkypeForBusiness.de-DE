---
title: 'Lync Server 2013: Medienansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aebd16d8bd2efaf8deeb6752deeb199411ab125
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="84ffd-102">Medienansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84ffd-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84ffd-103">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="84ffd-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="84ffd-104">In der medialinie-Ansicht werden Informationen zu jeder medienzeile in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="84ffd-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="84ffd-105">Eine Audiositzung enthält in der Regel eine Audio-medienzeile.</span><span class="sxs-lookup"><span data-stu-id="84ffd-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="84ffd-106">Eine Audio-und Video (A/V)-Sitzung enthält in der Regel eine Audio-medienzeile und eine Video medienzeile. die Sitzung kann jedoch zwei Video Medien Linien enthalten, wenn ein Konferenzgerät verwendet wird oder wenn die Katalogansicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="84ffd-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="84ffd-107">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="84ffd-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84ffd-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="84ffd-108">Column</span></span></th>
<th><span data-ttu-id="84ffd-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="84ffd-109">Data Type</span></span></th>
<th><span data-ttu-id="84ffd-110">Details</span><span class="sxs-lookup"><span data-stu-id="84ffd-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="84ffd-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="84ffd-112">datetime</span><span class="sxs-lookup"><span data-stu-id="84ffd-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="84ffd-113">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="84ffd-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="84ffd-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="84ffd-115">int</span><span class="sxs-lookup"><span data-stu-id="84ffd-115">int</span></span></p></td>
<td><p><span data-ttu-id="84ffd-116">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="84ffd-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="84ffd-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="84ffd-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="84ffd-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="84ffd-119">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="84ffd-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="84ffd-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="84ffd-121">int</span><span class="sxs-lookup"><span data-stu-id="84ffd-121">int</span></span></p></td>
<td><p><span data-ttu-id="84ffd-122">Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der unter Bits-Flags für den Aufrufer beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="84ffd-122">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="84ffd-123">Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="84ffd-123">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="84ffd-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="84ffd-125">int</span><span class="sxs-lookup"><span data-stu-id="84ffd-125">int</span></span></p></td>
<td><p><span data-ttu-id="84ffd-126">Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der in den Bits-Flags für den aufgerufenen beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="84ffd-126">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="84ffd-127">Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="84ffd-127">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-128">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="84ffd-128">Security</span></span></p></td>
<td><p><span data-ttu-id="84ffd-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="84ffd-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="84ffd-130">Verwendetes Sicherheitsprofil</span><span class="sxs-lookup"><span data-stu-id="84ffd-130">Security profile in use.</span></span> <span data-ttu-id="84ffd-131">0 ist None, 1 ist SRTP, 2 ist v1.</span><span class="sxs-lookup"><span data-stu-id="84ffd-131">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-132">Transport</span><span class="sxs-lookup"><span data-stu-id="84ffd-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="84ffd-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="84ffd-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="84ffd-134">Transporttyp.</span><span class="sxs-lookup"><span data-stu-id="84ffd-134">Transport type.</span></span> <span data-ttu-id="84ffd-135">0 ist UDP, 1 ist TCP.</span><span class="sxs-lookup"><span data-stu-id="84ffd-135">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="84ffd-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="84ffd-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="84ffd-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-138">Die IP-Adresse des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="84ffd-138">IP address of the caller.</span></span> <span data-ttu-id="84ffd-139">Dies kann eine IPv4-oder IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="84ffd-139">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="84ffd-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="84ffd-141">int</span><span class="sxs-lookup"><span data-stu-id="84ffd-141">int</span></span></p></td>
<td><p><span data-ttu-id="84ffd-142">Der vom Aufrufer verwendete Port.</span><span class="sxs-lookup"><span data-stu-id="84ffd-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="84ffd-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="84ffd-144">bit</span><span class="sxs-lookup"><span data-stu-id="84ffd-144">bit</span></span></p></td>
<td><p><span data-ttu-id="84ffd-145">Gibt an, ob sich der Anrufer innerhalb des Organisationsnetzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="84ffd-145">Indicates whether or not the caller is inside the organization network.</span></span> <span data-ttu-id="84ffd-146">1 bedeutet, dass sich der Anrufer innerhalb des Unternehmensnetzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="84ffd-146">1 means that the caller is inside the enterprise network.</span></span> <span data-ttu-id="84ffd-147">0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="84ffd-147">0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="84ffd-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="84ffd-149">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="84ffd-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-150">Mac-Adresse der vom Anrufer verwendeten Netzwerkschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="84ffd-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="84ffd-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="84ffd-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="84ffd-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-153">Die IP-Adresse des A/V-Edgedienst, der vom Aufrufer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="84ffd-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="84ffd-154">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="84ffd-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="84ffd-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="84ffd-156">int</span><span class="sxs-lookup"><span data-stu-id="84ffd-156">int</span></span></p></td>
<td><p><span data-ttu-id="84ffd-157">Der Port des A/V-Edgedienst, der vom Aufrufer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="84ffd-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="84ffd-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="84ffd-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="84ffd-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-160">Die IP-Adresse des Anrufers, wie er vom A/V-Edgedienst gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="84ffd-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="84ffd-161">Diese Adresse kann sich von der CallerIPAddr unterscheiden, wenn sich der Client beispielsweise hinter einem NAT befindet.</span><span class="sxs-lookup"><span data-stu-id="84ffd-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="84ffd-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="84ffd-163">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="84ffd-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-164">Name des Aufnahmegeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="84ffd-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="84ffd-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="84ffd-166">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="84ffd-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-167">Name des Render-Geräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="84ffd-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="84ffd-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="84ffd-169">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="84ffd-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-170">Name des Aufnahmegeräte Treibers des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="84ffd-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="84ffd-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="84ffd-172">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="84ffd-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-173">Name des Render-Gerätetreibers des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="84ffd-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="84ffd-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="84ffd-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="84ffd-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="84ffd-176">Beschreibung des WLAN-Treibers des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="84ffd-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="84ffd-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="84ffd-178">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="84ffd-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-179">WLAN-Treiberversion des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="84ffd-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="84ffd-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="84ffd-181">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="84ffd-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-182">Details zur Netzwerkverbindung des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="84ffd-182">Details of caller’s network connection.</span></span> <span data-ttu-id="84ffd-183">Weitere Informationen finden Sie <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="84ffd-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="84ffd-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="84ffd-185">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="84ffd-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-186">Grundlegende Dienst Satzkennung, die von der WLAN-Verbindung der Anrufer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="84ffd-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="84ffd-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="84ffd-188">bit</span><span class="sxs-lookup"><span data-stu-id="84ffd-188">bit</span></span></p></td>
<td><p><span data-ttu-id="84ffd-189">Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="84ffd-189">Indicates whether the caller connected over a virtual private network.</span></span> <span data-ttu-id="84ffd-190">1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.</span><span class="sxs-lookup"><span data-stu-id="84ffd-190">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="84ffd-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="84ffd-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="84ffd-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-193">Die IP-Adresse des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="84ffd-193">IP address of the callee.</span></span> <span data-ttu-id="84ffd-194">Dies kann eine IPv4-oder IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="84ffd-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="84ffd-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="84ffd-196">int</span><span class="sxs-lookup"><span data-stu-id="84ffd-196">int</span></span></p></td>
<td><p><span data-ttu-id="84ffd-197">Port, der vom aufgerufenen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="84ffd-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="84ffd-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="84ffd-199">bit</span><span class="sxs-lookup"><span data-stu-id="84ffd-199">bit</span></span></p></td>
<td><p><span data-ttu-id="84ffd-200">Gibt an, ob sich der aufgerufene innerhalb des Unternehmensnetzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="84ffd-200">Indicates whether the callee is inside the enterprise network.</span></span> <span data-ttu-id="84ffd-201">1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass der Anrufer sich außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="84ffd-201">1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="84ffd-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="84ffd-203">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="84ffd-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-204">Mac-Adresse der vom aufgerufenen verwendeten Netzwerkschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="84ffd-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="84ffd-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="84ffd-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="84ffd-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-207">Die IP-Adresse des A/V-Edgedienst, der vom aufgerufenen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="84ffd-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="84ffd-208">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="84ffd-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="84ffd-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="84ffd-210">int</span><span class="sxs-lookup"><span data-stu-id="84ffd-210">int</span></span></p></td>
<td><p><span data-ttu-id="84ffd-211">Port, der für den A/V-Edgedienst verwendet wird, der vom aufgerufenen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="84ffd-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="84ffd-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="84ffd-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="84ffd-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-214">Die IP-Adresse des Betreibers, wie vom A/V-Edgedienst gemeldet.</span><span class="sxs-lookup"><span data-stu-id="84ffd-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="84ffd-215">Diese Adresse kann sich von der CalleeIPAddr unterscheiden, wenn sich der Client beispielsweise hinter einem NAT befindet.</span><span class="sxs-lookup"><span data-stu-id="84ffd-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="84ffd-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="84ffd-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="84ffd-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-218">Der Name des Erfassungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="84ffd-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="84ffd-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="84ffd-220">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="84ffd-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-221">Name des Render-Geräts.</span><span class="sxs-lookup"><span data-stu-id="84ffd-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="84ffd-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="84ffd-223">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="84ffd-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-224">Der Name des Capture-Gerätetreibers des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="84ffd-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="84ffd-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="84ffd-226">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="84ffd-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-227">Der Name des Render-Gerätetreibers des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="84ffd-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="84ffd-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="84ffd-229">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="84ffd-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-230">Beschreibung des WLAN-Treibers des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="84ffd-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="84ffd-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="84ffd-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="84ffd-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="84ffd-233">WLAN-Treiberversion des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="84ffd-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="84ffd-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="84ffd-235">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="84ffd-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-236">Details zur Netzwerkverbindung des berufenen.</span><span class="sxs-lookup"><span data-stu-id="84ffd-236">Details of callee’s network connection.</span></span> <span data-ttu-id="84ffd-237">Weitere Informationen finden Sie <a href="lync-server-2013-networkconnectiondetail-table.md">in der NetworkConnectionDetail-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="84ffd-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="84ffd-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="84ffd-239">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="84ffd-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-240">Grundlegende Dienst Satz-ID, die von der WLAN-Verbindung des berufenen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="84ffd-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="84ffd-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="84ffd-242">bit</span><span class="sxs-lookup"><span data-stu-id="84ffd-242">bit</span></span></p></td>
<td><p><span data-ttu-id="84ffd-243">Gibt an, ob der aufgerufene über ein virtuelles privates Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="84ffd-243">Indicates whether the callee connected over a virtual private network.</span></span> <span data-ttu-id="84ffd-244">1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.</span><span class="sxs-lookup"><span data-stu-id="84ffd-244">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="84ffd-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="84ffd-246">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="84ffd-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-247">Schmalband-Konversations-Mos der audiositzungen (basierend auf beiden Audiostreams).</span><span class="sxs-lookup"><span data-stu-id="84ffd-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="84ffd-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="84ffd-249">int</span><span class="sxs-lookup"><span data-stu-id="84ffd-249">int</span></span></p></td>
<td><p><span data-ttu-id="84ffd-250">Hierbei handelt es sich um die tatsächliche Bandbreite, die auf den angegebenen Send-Seitenstrom angewendet wird, wobei verschiedene Richtlinieneinstellungen angegeben werden (Turn, API, SDP, Richtlinien Server usw.).</span><span class="sxs-lookup"><span data-stu-id="84ffd-250">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.).</span></span> <span data-ttu-id="84ffd-251">Dies sollte nicht mit der effektiven Bandbreite verwechselt werden, da auf der Grundlage der Bandbreitenschätzung eine geringere effektive Bandbreite vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="84ffd-251">This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="84ffd-252">Dies ist im Grunde die maximale Bandbreite, die der sendedatenstrom sperren kann, wenn die Bandbreite geschätzt wird.</span><span class="sxs-lookup"><span data-stu-id="84ffd-252">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="84ffd-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="84ffd-254">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="84ffd-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="84ffd-255">Die Quelle des verhängten Bandbreitenlimits.</span><span class="sxs-lookup"><span data-stu-id="84ffd-255">Source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="84ffd-256">Es wird beschrieben, woher die Bandbreitengrenze stammt (beispielsweise "Richtlinienserver", "Server umwandeln" oder "Modalität").</span><span class="sxs-lookup"><span data-stu-id="84ffd-256">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-257">Anrufer</span><span class="sxs-lookup"><span data-stu-id="84ffd-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="84ffd-258">bit</span><span class="sxs-lookup"><span data-stu-id="84ffd-258">bit</span></span></p></td>
<td><p><span data-ttu-id="84ffd-259">Gibt an, ob Metriken des Anrufers empfangen wurden; 1 ist ja, 0 ist Nein.</span><span class="sxs-lookup"><span data-stu-id="84ffd-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-260">Callee</span><span class="sxs-lookup"><span data-stu-id="84ffd-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="84ffd-261">bit</span><span class="sxs-lookup"><span data-stu-id="84ffd-261">bit</span></span></p></td>
<td><p><span data-ttu-id="84ffd-262">Gibt an, ob Metriken vom Anrufempfänger empfangen wurden; 1 ist ja, 0 ist Nein.</span><span class="sxs-lookup"><span data-stu-id="84ffd-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="84ffd-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="84ffd-264">bit</span><span class="sxs-lookup"><span data-stu-id="84ffd-264">bit</span></span></p></td>
<td><p><span data-ttu-id="84ffd-265">Gibt an, ob es sich bei dem Bericht um einen Teil des Anrufs oder um einen vollständigen Anruf handelt.</span><span class="sxs-lookup"><span data-stu-id="84ffd-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="84ffd-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="84ffd-267">bit</span><span class="sxs-lookup"><span data-stu-id="84ffd-267">bit</span></span></p></td>
<td><p><span data-ttu-id="84ffd-268">Gibt an, ob ein Anruf als schlechter Anruf (1) oder als guter Anruf (0) klassifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="84ffd-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ffd-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="84ffd-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="84ffd-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="84ffd-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="84ffd-271">Gibt an, ob der Anrufer über das Ice-Protokoll (Internet Connectivity Establishment) mit dem Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="84ffd-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ffd-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="84ffd-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="84ffd-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="84ffd-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="84ffd-274">Gibt an, ob der Benutzer die Verbindung mit dem Netzwerk mit dem ICE-Protokoll (Internet Connectivity Establishment) aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="84ffd-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

