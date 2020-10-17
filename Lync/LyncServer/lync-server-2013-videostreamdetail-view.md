---
title: 'Lync Server 2013: VideoStreamDetail-Ansicht'
description: 'Lync Server 2013: VideoStreamDetail-Ansicht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3f420c292627d15fd0d54f2eba01c565a49a72d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567971"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="71282-103">VideoStreamDetail-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71282-103">VideoStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71282-104">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="71282-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="71282-105">In der VideoStreamDetail-Ansicht werden Informationen zu den einzelnen Videostreams in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="71282-105">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="71282-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71282-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71282-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="71282-107">Column</span></span></th>
<th><span data-ttu-id="71282-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="71282-108">Data Type</span></span></th>
<th><span data-ttu-id="71282-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71282-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71282-110">SessionTime</span><span class="sxs-lookup"><span data-stu-id="71282-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="71282-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="71282-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="71282-112"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="71282-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="71282-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="71282-114">int</span><span class="sxs-lookup"><span data-stu-id="71282-114">int</span></span></p></td>
<td><p><span data-ttu-id="71282-115"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="71282-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-116">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="71282-116">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="71282-117">tinyint</span><span class="sxs-lookup"><span data-stu-id="71282-117">tinyint</span></span></p></td>
<td><p><span data-ttu-id="71282-118"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="71282-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-119">Datenstrom-Nr</span><span class="sxs-lookup"><span data-stu-id="71282-119">StreamId</span></span></p></td>
<td><p><span data-ttu-id="71282-120">int</span><span class="sxs-lookup"><span data-stu-id="71282-120">int</span></span></p></td>
<td><p><span data-ttu-id="71282-121">Eindeutige ID innerhalb einer Medienzeile.</span><span class="sxs-lookup"><span data-stu-id="71282-121">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-122">StartTime</span><span class="sxs-lookup"><span data-stu-id="71282-122">StartTime</span></span></p></td>
<td><p><span data-ttu-id="71282-123">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="71282-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="71282-124">Startzeitpunkt der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="71282-124">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-125">EndTime</span><span class="sxs-lookup"><span data-stu-id="71282-125">EndTime</span></span></p></td>
<td><p><span data-ttu-id="71282-126">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="71282-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="71282-127">Endzeitpunkt der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="71282-127">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-128">CallPriority</span><span class="sxs-lookup"><span data-stu-id="71282-128">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="71282-129">int</span><span class="sxs-lookup"><span data-stu-id="71282-129">int</span></span></p></td>
<td><p><span data-ttu-id="71282-130">Priorität des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="71282-130">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-131">CallerPool</span><span class="sxs-lookup"><span data-stu-id="71282-131">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="71282-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="71282-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71282-133">FQDN des Anruferpools.</span><span class="sxs-lookup"><span data-stu-id="71282-133">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-134">CalleePool</span><span class="sxs-lookup"><span data-stu-id="71282-134">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="71282-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="71282-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71282-136">FQDN des Angerufenenpools.</span><span class="sxs-lookup"><span data-stu-id="71282-136">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-137">Anrufer</span><span class="sxs-lookup"><span data-stu-id="71282-137">Caller</span></span></p></td>
<td><p><span data-ttu-id="71282-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="71282-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="71282-139">URI des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="71282-139">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-140">Aufgerufene</span><span class="sxs-lookup"><span data-stu-id="71282-140">Callee</span></span></p></td>
<td><p><span data-ttu-id="71282-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="71282-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="71282-142">URI des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="71282-142">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-143">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="71282-143">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="71282-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="71282-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71282-145">Zeichenfolge für den Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="71282-145">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-146">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="71282-146">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="71282-147">smallint</span><span class="sxs-lookup"><span data-stu-id="71282-147">smallint</span></span></p></td>
<td><p><span data-ttu-id="71282-148">Typ des Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="71282-148">Type of caller’s user agent.</span></span> <span data-ttu-id="71282-149">Ausführliche Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71282-149">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-150">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="71282-150">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="71282-151">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="71282-151">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="71282-152">Kategorie des Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="71282-152">Category of caller’s user agent.</span></span> <span data-ttu-id="71282-153">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71282-153">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-154">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="71282-154">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="71282-155">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="71282-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71282-156">Zeichenfolge für den Benutzer-Agent des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="71282-156">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-157">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="71282-157">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="71282-158">smallint</span><span class="sxs-lookup"><span data-stu-id="71282-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="71282-159">Typ des Benutzer-Agent des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="71282-159">Type of callee’s user agent.</span></span> <span data-ttu-id="71282-160">Weitere Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71282-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-161">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="71282-161">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="71282-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="71282-162">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="71282-163">Kategorie des Benutzer-Agent des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="71282-163">Category of callee’s user agent.</span></span> <span data-ttu-id="71282-164">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71282-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-165">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="71282-165">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="71282-166">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="71282-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71282-167">Name des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="71282-167">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-168">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="71282-168">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="71282-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="71282-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71282-170">Name des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="71282-170">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-171">Anrufer</span><span class="sxs-lookup"><span data-stu-id="71282-171">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="71282-172">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="71282-172">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="71282-173">Betriebssystem des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="71282-173">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-174">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="71282-174">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="71282-175">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="71282-175">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="71282-176">Betriebssystem des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="71282-176">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-177">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="71282-177">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="71282-178">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="71282-178">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="71282-179">Name der CPU des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="71282-179">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-180">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="71282-180">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="71282-181">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="71282-181">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="71282-182">Name der CPU des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="71282-182">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-183">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="71282-183">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="71282-184">smallint</span><span class="sxs-lookup"><span data-stu-id="71282-184">smallint</span></span></p></td>
<td><p><span data-ttu-id="71282-185">Anzahl der CPU-Kerne des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="71282-185">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-186">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="71282-186">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="71282-187">smallint</span><span class="sxs-lookup"><span data-stu-id="71282-187">smallint</span></span></p></td>
<td><p><span data-ttu-id="71282-188">Anzahl der CPU-Kerne des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="71282-188">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-189">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="71282-189">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="71282-190">int</span><span class="sxs-lookup"><span data-stu-id="71282-190">int</span></span></p></td>
<td><p><span data-ttu-id="71282-191">Prozessorgeschwindigkeit der CPU des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="71282-191">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-192">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="71282-192">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="71282-193">int</span><span class="sxs-lookup"><span data-stu-id="71282-193">int</span></span></p></td>
<td><p><span data-ttu-id="71282-194">Prozessorgeschwindigkeit der CPU des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="71282-194">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-195">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="71282-195">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="71282-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="71282-196">tinyint</span></span></p></td>
<td><p><span data-ttu-id="71282-197">Gibt an, ob das System des Anrufers in einer virtualisierten Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="71282-197">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="71282-198">Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpoint-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71282-198">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-199">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="71282-199">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="71282-200">tinyint</span><span class="sxs-lookup"><span data-stu-id="71282-200">tinyint</span></span></p></td>
<td><p><span data-ttu-id="71282-201">Gibt an, ob das System des Angerufenen in einer virtualisierten Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="71282-201">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="71282-202">Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpoint-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71282-202">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-203">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="71282-203">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="71282-204">tinyint</span><span class="sxs-lookup"><span data-stu-id="71282-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="71282-205">Informationen zum Medienpfad, z. B. direkt oder Relay.</span><span class="sxs-lookup"><span data-stu-id="71282-205">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="71282-206">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71282-206">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-207">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="71282-207">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="71282-208">int</span><span class="sxs-lookup"><span data-stu-id="71282-208">int</span></span></p></td>
<td><p><span data-ttu-id="71282-p109">Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Anrufer, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".</span><span class="sxs-lookup"><span data-stu-id="71282-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-211">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="71282-211">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="71282-212">int</span><span class="sxs-lookup"><span data-stu-id="71282-212">int</span></span></p></td>
<td><p><span data-ttu-id="71282-p110">Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Angerufenen, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".</span><span class="sxs-lookup"><span data-stu-id="71282-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-215">Transport</span><span class="sxs-lookup"><span data-stu-id="71282-215">Transport</span></span></p></td>
<td><p><span data-ttu-id="71282-216">int</span><span class="sxs-lookup"><span data-stu-id="71282-216">int</span></span></p></td>
<td><p><span data-ttu-id="71282-217">Transporttyp: 0 ist UDP, 1 ist TCP.</span><span class="sxs-lookup"><span data-stu-id="71282-217">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-218">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="71282-218">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="71282-219">var (50)</span><span class="sxs-lookup"><span data-stu-id="71282-219">var(50)</span></span></p></td>
<td><p><span data-ttu-id="71282-220">IP-Adresse des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="71282-220">IP address of the caller.</span></span> <span data-ttu-id="71282-221">Dies kann eine IPv4- oder eine IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="71282-221">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-222">CallerPort</span><span class="sxs-lookup"><span data-stu-id="71282-222">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="71282-223">int</span><span class="sxs-lookup"><span data-stu-id="71282-223">int</span></span></p></td>
<td><p><span data-ttu-id="71282-224">Vom Anrufer verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="71282-224">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-225">CallerInside</span><span class="sxs-lookup"><span data-stu-id="71282-225">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="71282-226">Bit</span><span class="sxs-lookup"><span data-stu-id="71282-226">bit</span></span></p></td>
<td><p><span data-ttu-id="71282-p112">Gibt an, ob der Anrufer sich innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, der Anrufer befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Anrufer befindet sich außerhalb davon.</span><span class="sxs-lookup"><span data-stu-id="71282-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-229">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="71282-229">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="71282-230">var (50)</span><span class="sxs-lookup"><span data-stu-id="71282-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="71282-231">IP-Adresse des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="71282-231">IP address of the callee.</span></span> <span data-ttu-id="71282-232">Dies kann eine IPv4- oder eine IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="71282-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-233">CalleePort</span><span class="sxs-lookup"><span data-stu-id="71282-233">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="71282-234">int</span><span class="sxs-lookup"><span data-stu-id="71282-234">int</span></span></p></td>
<td><p><span data-ttu-id="71282-235">Vom Angerufenen verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="71282-235">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-236">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="71282-236">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="71282-237">Bit</span><span class="sxs-lookup"><span data-stu-id="71282-237">bit</span></span></p></td>
<td><p><span data-ttu-id="71282-238">Gibt an, ob der Angerufene sich innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, der Angerufene befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Angerufene befindet sich außerhalb davon.</span><span class="sxs-lookup"><span data-stu-id="71282-238">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-239">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="71282-239">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="71282-240">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="71282-240">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="71282-241">Name der Website des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="71282-241">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-242">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="71282-242">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="71282-243">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="71282-243">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="71282-244">Name des Landes/der Region der Website des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="71282-244">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-245">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="71282-245">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="71282-246">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="71282-246">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="71282-247">Name der Website des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="71282-247">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-248">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="71282-248">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="71282-249">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="71282-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="71282-250">Name des Landes/der Region der Website des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="71282-250">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-251">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="71282-251">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="71282-252">var (50)</span><span class="sxs-lookup"><span data-stu-id="71282-252">var(50)</span></span></p></td>
<td><p><span data-ttu-id="71282-253">IP-Adresse des vom Anrufer verwendeten A/V-Edgedienstes.</span><span class="sxs-lookup"><span data-stu-id="71282-253">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="71282-254">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71282-254">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-255">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="71282-255">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="71282-256">int</span><span class="sxs-lookup"><span data-stu-id="71282-256">int</span></span></p></td>
<td><p><span data-ttu-id="71282-257">Port auf dem vom Anrufer verwendeten A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="71282-257">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-258">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="71282-258">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="71282-259">var (50)</span><span class="sxs-lookup"><span data-stu-id="71282-259">var(50)</span></span></p></td>
<td><p><span data-ttu-id="71282-260">IP-Adressschlüssel des vom Anrufer verwendeten A/V-Edgedienstes.</span><span class="sxs-lookup"><span data-stu-id="71282-260">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="71282-261">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71282-261">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-262">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="71282-262">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="71282-263">int</span><span class="sxs-lookup"><span data-stu-id="71282-263">int</span></span></p></td>
<td><p><span data-ttu-id="71282-264">Port auf dem vom Angerufenen verwendeten A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="71282-264">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-265">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="71282-265">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="71282-266">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="71282-266">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71282-267">Name des Aufnahmegeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="71282-267">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-268">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="71282-268">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="71282-269">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="71282-269">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71282-270">Name des Darstellungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="71282-270">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-271">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="71282-271">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="71282-272">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="71282-272">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71282-273">Name des Gerätetreibers des Aufnahmegeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="71282-273">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-274">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="71282-274">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="71282-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="71282-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71282-276">Name des Gerätetreibers des Darstellungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="71282-276">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-277">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="71282-277">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="71282-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="71282-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71282-279">Name des Aufnahmegeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="71282-279">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-280">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="71282-280">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="71282-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="71282-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71282-282">Name des Darstellungsgeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="71282-282">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-283">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="71282-283">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="71282-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="71282-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71282-285">Name des Gerätetreibers des Aufnahmegeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="71282-285">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-286">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="71282-286">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="71282-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="71282-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71282-288">Name des Gerätetreibers des Darstellungsgeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="71282-288">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-289">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="71282-289">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="71282-290">tinyint</span><span class="sxs-lookup"><span data-stu-id="71282-290">tinyint</span></span></p></td>
<td><p><span data-ttu-id="71282-291">Typ der Netzwerkverbindung des Anrufers: 0 ist verkabelt, 1 ist kabellos.</span><span class="sxs-lookup"><span data-stu-id="71282-291">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-292">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="71282-292">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="71282-293">Bit</span><span class="sxs-lookup"><span data-stu-id="71282-293">bit</span></span></p></td>
<td><p><span data-ttu-id="71282-p116">Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk (VPN) verbunden ist. 1 ist VPN, 0 ist Nicht-VPN.</span><span class="sxs-lookup"><span data-stu-id="71282-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-296">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="71282-296">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="71282-297">Decimal (18,)</span><span class="sxs-lookup"><span data-stu-id="71282-297">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="71282-298">Netzwerkübertragungsrate für den Endpunkt des Anrufers in Bit/s.</span><span class="sxs-lookup"><span data-stu-id="71282-298">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-299">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="71282-299">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="71282-300">tinyint</span><span class="sxs-lookup"><span data-stu-id="71282-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="71282-301">Typ der Netzwerkverbindung des Angerufenen: 0 ist verkabelt, 1 ist kabellos.</span><span class="sxs-lookup"><span data-stu-id="71282-301">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-302">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="71282-302">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="71282-303">Bit</span><span class="sxs-lookup"><span data-stu-id="71282-303">bit</span></span></p></td>
<td><p><span data-ttu-id="71282-p117">Gibt an, ob der Angerufene über ein virtuelles privates Netzwerk (VPN) verbunden ist. 1 ist VPN, 0 ist Nicht-VPN.</span><span class="sxs-lookup"><span data-stu-id="71282-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-306">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="71282-306">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="71282-307">Decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="71282-307">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="71282-308">Netzwerkübertragungsrate für den Endpunkt des Angerufenen in Bit/s.</span><span class="sxs-lookup"><span data-stu-id="71282-308">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-309">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="71282-309">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="71282-310">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="71282-310">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="71282-311">Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).</span><span class="sxs-lookup"><span data-stu-id="71282-311">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-312">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="71282-312">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="71282-313">int</span><span class="sxs-lookup"><span data-stu-id="71282-313">int</span></span></p></td>
<td><p><span data-ttu-id="71282-p118">Tatsächliche Bandbreite, die unter verschiedenen Richtlinieneinstellungen (TURN, API, SDP, Richtlinienserver usw.) auf den jeweiligen Stream auf der Seite des Absenders angewendet wird. Dies ist nicht zu verwechseln mit der effektiven Bandbreite, da diese u. U. basierend auf der Bandbreitenschätzung niedriger ist. Dabei handelt es sich um die maximale Bandbreite, die für den Absenderstream möglich ist, abgesehen von den Beschränkungen durch die Bandbreitenschätzung.</span><span class="sxs-lookup"><span data-stu-id="71282-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-317">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="71282-317">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="71282-318">int</span><span class="sxs-lookup"><span data-stu-id="71282-318">int</span></span></p></td>
<td><p><span data-ttu-id="71282-319">Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="71282-319">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-320">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="71282-320">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="71282-321">int</span><span class="sxs-lookup"><span data-stu-id="71282-321">int</span></span></p></td>
<td><p><span data-ttu-id="71282-322">Maximaler Netzwerkjitter während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="71282-322">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-323">Roundtrip</span><span class="sxs-lookup"><span data-stu-id="71282-323">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="71282-324">int</span><span class="sxs-lookup"><span data-stu-id="71282-324">int</span></span></p></td>
<td><p><span data-ttu-id="71282-325">Roundtripzeit aus RTCP-Statistik.</span><span class="sxs-lookup"><span data-stu-id="71282-325">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-326">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="71282-326">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="71282-327">int</span><span class="sxs-lookup"><span data-stu-id="71282-327">int</span></span></p></td>
<td><p><span data-ttu-id="71282-328">Maximale Roundtripzeit für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="71282-328">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-329">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="71282-329">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="71282-330">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="71282-330">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="71282-331">Durchschnittliche Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="71282-331">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-332">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="71282-332">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="71282-333">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="71282-333">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="71282-334">Maximale Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="71282-334">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-335">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="71282-335">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="71282-336">int</span><span class="sxs-lookup"><span data-stu-id="71282-336">int</span></span></p></td>
<td><p><span data-ttu-id="71282-337">Paketwert für den Videostream (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="71282-337">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-338">Bandbreite</span><span class="sxs-lookup"><span data-stu-id="71282-338">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="71282-339">int</span><span class="sxs-lookup"><span data-stu-id="71282-339">int</span></span></p></td>
<td><p><span data-ttu-id="71282-340">Bandbreitenschätzungen für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="71282-340">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-341">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="71282-341">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="71282-342">int</span><span class="sxs-lookup"><span data-stu-id="71282-342">int</span></span></p></td>
<td><p><span data-ttu-id="71282-343">Für den Anruf verwendeter Audiocodec, der <a href="lync-server-2013-payloaddescription-table.md">in lync Server 2013 in der PayloadDescription-Tabelle</a>referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="71282-343">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-344">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="71282-344">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="71282-345">char (9)</span><span class="sxs-lookup"><span data-stu-id="71282-345">char(9)</span></span></p></td>
<td><p><span data-ttu-id="71282-p119">Auflösung des Videos in Pixel Breite x Höhe. Gemeldet als Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="71282-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-348">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="71282-348">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="71282-349">int</span><span class="sxs-lookup"><span data-stu-id="71282-349">int</span></span></p></td>
<td><p><span data-ttu-id="71282-350">Durchschnittliche Bitrate des Videostreams.</span><span class="sxs-lookup"><span data-stu-id="71282-350">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-351">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="71282-351">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="71282-352">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="71282-352">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="71282-353">Empfangene Framerate des Videostreams.</span><span class="sxs-lookup"><span data-stu-id="71282-353">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-354">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="71282-354">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="71282-355">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="71282-355">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="71282-356">Gesendete Framerate des Videostreams.</span><span class="sxs-lookup"><span data-stu-id="71282-356">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-357">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="71282-357">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="71282-358">int</span><span class="sxs-lookup"><span data-stu-id="71282-358">int</span></span></p></td>
<td><p><span data-ttu-id="71282-359">Maximale Videobitrate während der Videositzung.</span><span class="sxs-lookup"><span data-stu-id="71282-359">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-360">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="71282-360">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="71282-361">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="71282-361">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="71282-362">Videpaketverlustrate.</span><span class="sxs-lookup"><span data-stu-id="71282-362">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-363">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="71282-363">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="71282-364">Decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="71282-364">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="71282-365">Prozentsatz der verlorenen Videoframes von der Gesamtzahl der Videoframes.</span><span class="sxs-lookup"><span data-stu-id="71282-365">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-366">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="71282-366">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="71282-367">Bit</span><span class="sxs-lookup"><span data-stu-id="71282-367">bit</span></span></p></td>
<td><p><span data-ttu-id="71282-368">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="71282-368">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-369">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="71282-369">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="71282-370">int</span><span class="sxs-lookup"><span data-stu-id="71282-370">int</span></span></p></td>
<td><p><span data-ttu-id="71282-371">Durchschnittliche für Video reservierte Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="71282-371">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71282-372">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="71282-372">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="71282-373">Decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="71282-373">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="71282-374">Durchschnittlicher Prozentsatz der gesamten Videoframes, die verloren gingen.</span><span class="sxs-lookup"><span data-stu-id="71282-374">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71282-375">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="71282-375">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="71282-376">Bit</span><span class="sxs-lookup"><span data-stu-id="71282-376">bit</span></span></p></td>
<td><p><span data-ttu-id="71282-p120">Streamrichtung für PAI-Informationen (P-Asserted-Identity). 1 bedeutet, die Streamrichtung verläuft vom Anrufer zum Angerufenen. 0 bedeutet, die Streamrichtung verläuft vom Angerufenen zum Anrufer.</span><span class="sxs-lookup"><span data-stu-id="71282-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

