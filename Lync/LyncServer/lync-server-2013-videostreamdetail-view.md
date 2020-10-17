---
title: 'Lync Server 2013: VideoStreamDetail-Ansicht'
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
ms.openlocfilehash: 3d419800842fed080efe4005e7282a25c91f29df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518522"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="14602-102">VideoStreamDetail-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14602-102">VideoStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14602-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="14602-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="14602-104">In der VideoStreamDetail-Ansicht werden Informationen zu den einzelnen Videostreams in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="14602-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="14602-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="14602-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14602-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="14602-106">Column</span></span></th>
<th><span data-ttu-id="14602-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="14602-107">Data Type</span></span></th>
<th><span data-ttu-id="14602-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14602-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14602-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="14602-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="14602-110">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="14602-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="14602-111"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="14602-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="14602-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="14602-113">int</span><span class="sxs-lookup"><span data-stu-id="14602-113">int</span></span></p></td>
<td><p><span data-ttu-id="14602-114"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="14602-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="14602-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="14602-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="14602-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="14602-117"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="14602-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-118">Datenstrom-Nr</span><span class="sxs-lookup"><span data-stu-id="14602-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="14602-119">int</span><span class="sxs-lookup"><span data-stu-id="14602-119">int</span></span></p></td>
<td><p><span data-ttu-id="14602-120">Eindeutige ID innerhalb einer Medienzeile.</span><span class="sxs-lookup"><span data-stu-id="14602-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="14602-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="14602-122">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="14602-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="14602-123">Startzeitpunkt der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="14602-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="14602-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="14602-125">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="14602-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="14602-126">Endzeitpunkt der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="14602-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="14602-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="14602-128">int</span><span class="sxs-lookup"><span data-stu-id="14602-128">int</span></span></p></td>
<td><p><span data-ttu-id="14602-129">Priorität des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="14602-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="14602-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="14602-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="14602-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="14602-132">FQDN des Anruferpools.</span><span class="sxs-lookup"><span data-stu-id="14602-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="14602-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="14602-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="14602-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="14602-135">FQDN des Angerufenenpools.</span><span class="sxs-lookup"><span data-stu-id="14602-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-136">Anrufer</span><span class="sxs-lookup"><span data-stu-id="14602-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="14602-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="14602-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="14602-138">URI des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="14602-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-139">Aufgerufene</span><span class="sxs-lookup"><span data-stu-id="14602-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="14602-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="14602-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="14602-141">URI des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="14602-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="14602-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="14602-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="14602-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="14602-144">Zeichenfolge für den Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="14602-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="14602-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="14602-146">smallint</span><span class="sxs-lookup"><span data-stu-id="14602-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="14602-147">Typ des Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="14602-147">Type of caller’s user agent.</span></span> <span data-ttu-id="14602-148">Ausführliche Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="14602-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="14602-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="14602-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="14602-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="14602-151">Kategorie des Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="14602-151">Category of caller’s user agent.</span></span> <span data-ttu-id="14602-152">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="14602-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="14602-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="14602-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="14602-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="14602-155">Zeichenfolge für den Benutzer-Agent des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="14602-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="14602-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="14602-157">smallint</span><span class="sxs-lookup"><span data-stu-id="14602-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="14602-158">Typ des Benutzer-Agent des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="14602-158">Type of callee’s user agent.</span></span> <span data-ttu-id="14602-159">Weitere Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="14602-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="14602-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="14602-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="14602-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="14602-162">Kategorie des Benutzer-Agent des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="14602-162">Category of callee’s user agent.</span></span> <span data-ttu-id="14602-163">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="14602-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="14602-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="14602-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="14602-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="14602-166">Name des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="14602-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="14602-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="14602-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="14602-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="14602-169">Name des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="14602-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-170">Anrufer</span><span class="sxs-lookup"><span data-stu-id="14602-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="14602-171">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="14602-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="14602-172">Betriebssystem des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="14602-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="14602-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="14602-174">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="14602-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="14602-175">Betriebssystem des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="14602-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="14602-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="14602-177">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="14602-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="14602-178">Name der CPU des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="14602-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="14602-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="14602-180">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="14602-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="14602-181">Name der CPU des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="14602-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="14602-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="14602-183">smallint</span><span class="sxs-lookup"><span data-stu-id="14602-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="14602-184">Anzahl der CPU-Kerne des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="14602-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="14602-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="14602-186">smallint</span><span class="sxs-lookup"><span data-stu-id="14602-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="14602-187">Anzahl der CPU-Kerne des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="14602-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="14602-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="14602-189">int</span><span class="sxs-lookup"><span data-stu-id="14602-189">int</span></span></p></td>
<td><p><span data-ttu-id="14602-190">Prozessorgeschwindigkeit der CPU des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="14602-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="14602-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="14602-192">int</span><span class="sxs-lookup"><span data-stu-id="14602-192">int</span></span></p></td>
<td><p><span data-ttu-id="14602-193">Prozessorgeschwindigkeit der CPU des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="14602-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="14602-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="14602-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="14602-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="14602-196">Gibt an, ob das System des Anrufers in einer virtualisierten Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="14602-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="14602-197">Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpoint-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="14602-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="14602-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="14602-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="14602-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="14602-200">Gibt an, ob das System des Angerufenen in einer virtualisierten Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="14602-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="14602-201">Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpoint-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="14602-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="14602-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="14602-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="14602-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="14602-204">Informationen zum Medienpfad, z. B. direkt oder Relay.</span><span class="sxs-lookup"><span data-stu-id="14602-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="14602-205">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="14602-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="14602-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="14602-207">int</span><span class="sxs-lookup"><span data-stu-id="14602-207">int</span></span></p></td>
<td><p><span data-ttu-id="14602-p109">Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Anrufer, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".</span><span class="sxs-lookup"><span data-stu-id="14602-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="14602-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="14602-211">int</span><span class="sxs-lookup"><span data-stu-id="14602-211">int</span></span></p></td>
<td><p><span data-ttu-id="14602-p110">Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Angerufenen, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".</span><span class="sxs-lookup"><span data-stu-id="14602-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-214">Transport</span><span class="sxs-lookup"><span data-stu-id="14602-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="14602-215">int</span><span class="sxs-lookup"><span data-stu-id="14602-215">int</span></span></p></td>
<td><p><span data-ttu-id="14602-216">Transporttyp: 0 ist UDP, 1 ist TCP.</span><span class="sxs-lookup"><span data-stu-id="14602-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="14602-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="14602-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="14602-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="14602-219">IP-Adresse des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="14602-219">IP address of the caller.</span></span> <span data-ttu-id="14602-220">Dies kann eine IPv4- oder eine IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="14602-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="14602-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="14602-222">int</span><span class="sxs-lookup"><span data-stu-id="14602-222">int</span></span></p></td>
<td><p><span data-ttu-id="14602-223">Vom Anrufer verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="14602-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="14602-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="14602-225">Bit</span><span class="sxs-lookup"><span data-stu-id="14602-225">bit</span></span></p></td>
<td><p><span data-ttu-id="14602-p112">Gibt an, ob der Anrufer sich innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, der Anrufer befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Anrufer befindet sich außerhalb davon.</span><span class="sxs-lookup"><span data-stu-id="14602-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="14602-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="14602-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="14602-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="14602-230">IP-Adresse des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="14602-230">IP address of the callee.</span></span> <span data-ttu-id="14602-231">Dies kann eine IPv4- oder eine IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="14602-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="14602-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="14602-233">int</span><span class="sxs-lookup"><span data-stu-id="14602-233">int</span></span></p></td>
<td><p><span data-ttu-id="14602-234">Vom Angerufenen verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="14602-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="14602-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="14602-236">Bit</span><span class="sxs-lookup"><span data-stu-id="14602-236">bit</span></span></p></td>
<td><p><span data-ttu-id="14602-237">Gibt an, ob der Angerufene sich innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, der Angerufene befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Angerufene befindet sich außerhalb davon.</span><span class="sxs-lookup"><span data-stu-id="14602-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="14602-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="14602-239">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="14602-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="14602-240">Name der Website des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="14602-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="14602-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="14602-242">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="14602-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="14602-243">Name des Landes/der Region der Website des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="14602-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="14602-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="14602-245">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="14602-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="14602-246">Name der Website des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="14602-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="14602-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="14602-248">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="14602-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="14602-249">Name des Landes/der Region der Website des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="14602-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="14602-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="14602-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="14602-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="14602-252">IP-Adresse des vom Anrufer verwendeten A/V-Edgedienstes.</span><span class="sxs-lookup"><span data-stu-id="14602-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="14602-253">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="14602-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="14602-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="14602-255">int</span><span class="sxs-lookup"><span data-stu-id="14602-255">int</span></span></p></td>
<td><p><span data-ttu-id="14602-256">Port auf dem vom Anrufer verwendeten A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="14602-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="14602-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="14602-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="14602-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="14602-259">IP-Adressschlüssel des vom Anrufer verwendeten A/V-Edgedienstes.</span><span class="sxs-lookup"><span data-stu-id="14602-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="14602-260">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="14602-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="14602-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="14602-262">int</span><span class="sxs-lookup"><span data-stu-id="14602-262">int</span></span></p></td>
<td><p><span data-ttu-id="14602-263">Port auf dem vom Angerufenen verwendeten A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="14602-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="14602-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="14602-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="14602-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="14602-266">Name des Aufnahmegeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="14602-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="14602-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="14602-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="14602-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="14602-269">Name des Darstellungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="14602-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="14602-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="14602-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="14602-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="14602-272">Name des Gerätetreibers des Aufnahmegeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="14602-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="14602-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="14602-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="14602-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="14602-275">Name des Gerätetreibers des Darstellungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="14602-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="14602-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="14602-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="14602-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="14602-278">Name des Aufnahmegeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="14602-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="14602-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="14602-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="14602-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="14602-281">Name des Darstellungsgeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="14602-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="14602-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="14602-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="14602-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="14602-284">Name des Gerätetreibers des Aufnahmegeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="14602-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="14602-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="14602-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="14602-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="14602-287">Name des Gerätetreibers des Darstellungsgeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="14602-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="14602-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="14602-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="14602-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="14602-290">Typ der Netzwerkverbindung des Anrufers: 0 ist verkabelt, 1 ist kabellos.</span><span class="sxs-lookup"><span data-stu-id="14602-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="14602-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="14602-292">Bit</span><span class="sxs-lookup"><span data-stu-id="14602-292">bit</span></span></p></td>
<td><p><span data-ttu-id="14602-p116">Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk (VPN) verbunden ist. 1 ist VPN, 0 ist Nicht-VPN.</span><span class="sxs-lookup"><span data-stu-id="14602-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="14602-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="14602-296">Decimal (18,)</span><span class="sxs-lookup"><span data-stu-id="14602-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="14602-297">Netzwerkübertragungsrate für den Endpunkt des Anrufers in Bit/s.</span><span class="sxs-lookup"><span data-stu-id="14602-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="14602-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="14602-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="14602-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="14602-300">Typ der Netzwerkverbindung des Angerufenen: 0 ist verkabelt, 1 ist kabellos.</span><span class="sxs-lookup"><span data-stu-id="14602-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="14602-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="14602-302">Bit</span><span class="sxs-lookup"><span data-stu-id="14602-302">bit</span></span></p></td>
<td><p><span data-ttu-id="14602-p117">Gibt an, ob der Angerufene über ein virtuelles privates Netzwerk (VPN) verbunden ist. 1 ist VPN, 0 ist Nicht-VPN.</span><span class="sxs-lookup"><span data-stu-id="14602-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="14602-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="14602-306">Decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="14602-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="14602-307">Netzwerkübertragungsrate für den Endpunkt des Angerufenen in Bit/s.</span><span class="sxs-lookup"><span data-stu-id="14602-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="14602-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="14602-309">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="14602-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="14602-310">Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).</span><span class="sxs-lookup"><span data-stu-id="14602-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="14602-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="14602-312">int</span><span class="sxs-lookup"><span data-stu-id="14602-312">int</span></span></p></td>
<td><p><span data-ttu-id="14602-p118">Tatsächliche Bandbreite, die unter verschiedenen Richtlinieneinstellungen (TURN, API, SDP, Richtlinienserver usw.) auf den jeweiligen Stream auf der Seite des Absenders angewendet wird. Dies ist nicht zu verwechseln mit der effektiven Bandbreite, da diese u. U. basierend auf der Bandbreitenschätzung niedriger ist. Dabei handelt es sich um die maximale Bandbreite, die für den Absenderstream möglich ist, abgesehen von den Beschränkungen durch die Bandbreitenschätzung.</span><span class="sxs-lookup"><span data-stu-id="14602-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="14602-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="14602-317">int</span><span class="sxs-lookup"><span data-stu-id="14602-317">int</span></span></p></td>
<td><p><span data-ttu-id="14602-318">Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="14602-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="14602-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="14602-320">int</span><span class="sxs-lookup"><span data-stu-id="14602-320">int</span></span></p></td>
<td><p><span data-ttu-id="14602-321">Maximaler Netzwerkjitter während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="14602-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-322">Roundtrip</span><span class="sxs-lookup"><span data-stu-id="14602-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="14602-323">int</span><span class="sxs-lookup"><span data-stu-id="14602-323">int</span></span></p></td>
<td><p><span data-ttu-id="14602-324">Roundtripzeit aus RTCP-Statistik.</span><span class="sxs-lookup"><span data-stu-id="14602-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="14602-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="14602-326">int</span><span class="sxs-lookup"><span data-stu-id="14602-326">int</span></span></p></td>
<td><p><span data-ttu-id="14602-327">Maximale Roundtripzeit für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="14602-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="14602-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="14602-329">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="14602-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="14602-330">Durchschnittliche Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="14602-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="14602-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="14602-332">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="14602-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="14602-333">Maximale Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="14602-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="14602-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="14602-335">int</span><span class="sxs-lookup"><span data-stu-id="14602-335">int</span></span></p></td>
<td><p><span data-ttu-id="14602-336">Paketwert für den Videostream (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="14602-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-337">Bandbreite</span><span class="sxs-lookup"><span data-stu-id="14602-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="14602-338">int</span><span class="sxs-lookup"><span data-stu-id="14602-338">int</span></span></p></td>
<td><p><span data-ttu-id="14602-339">Bandbreitenschätzungen für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="14602-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="14602-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="14602-341">int</span><span class="sxs-lookup"><span data-stu-id="14602-341">int</span></span></p></td>
<td><p><span data-ttu-id="14602-342">Für den Anruf verwendeter Audiocodec, der <a href="lync-server-2013-payloaddescription-table.md">in lync Server 2013 in der PayloadDescription-Tabelle</a>referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="14602-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="14602-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="14602-344">char (9)</span><span class="sxs-lookup"><span data-stu-id="14602-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="14602-p119">Auflösung des Videos in Pixel Breite x Höhe. Gemeldet als Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="14602-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="14602-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="14602-348">int</span><span class="sxs-lookup"><span data-stu-id="14602-348">int</span></span></p></td>
<td><p><span data-ttu-id="14602-349">Durchschnittliche Bitrate des Videostreams.</span><span class="sxs-lookup"><span data-stu-id="14602-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="14602-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="14602-351">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="14602-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="14602-352">Empfangene Framerate des Videostreams.</span><span class="sxs-lookup"><span data-stu-id="14602-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="14602-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="14602-354">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="14602-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="14602-355">Gesendete Framerate des Videostreams.</span><span class="sxs-lookup"><span data-stu-id="14602-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="14602-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="14602-357">int</span><span class="sxs-lookup"><span data-stu-id="14602-357">int</span></span></p></td>
<td><p><span data-ttu-id="14602-358">Maximale Videobitrate während der Videositzung.</span><span class="sxs-lookup"><span data-stu-id="14602-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="14602-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="14602-360">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="14602-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="14602-361">Videpaketverlustrate.</span><span class="sxs-lookup"><span data-stu-id="14602-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="14602-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="14602-363">Decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="14602-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="14602-364">Prozentsatz der verlorenen Videoframes von der Gesamtzahl der Videoframes.</span><span class="sxs-lookup"><span data-stu-id="14602-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="14602-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="14602-366">Bit</span><span class="sxs-lookup"><span data-stu-id="14602-366">bit</span></span></p></td>
<td><p><span data-ttu-id="14602-367">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="14602-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="14602-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="14602-369">int</span><span class="sxs-lookup"><span data-stu-id="14602-369">int</span></span></p></td>
<td><p><span data-ttu-id="14602-370">Durchschnittliche für Video reservierte Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="14602-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14602-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="14602-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="14602-372">Decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="14602-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="14602-373">Durchschnittlicher Prozentsatz der gesamten Videoframes, die verloren gingen.</span><span class="sxs-lookup"><span data-stu-id="14602-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14602-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="14602-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="14602-375">Bit</span><span class="sxs-lookup"><span data-stu-id="14602-375">bit</span></span></p></td>
<td><p><span data-ttu-id="14602-p120">Streamrichtung für PAI-Informationen (P-Asserted-Identity). 1 bedeutet, die Streamrichtung verläuft vom Anrufer zum Angerufenen. 0 bedeutet, die Streamrichtung verläuft vom Angerufenen zum Anrufer.</span><span class="sxs-lookup"><span data-stu-id="14602-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

