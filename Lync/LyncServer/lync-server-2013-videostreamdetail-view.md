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
ms.openlocfilehash: 8163915a7af190ad91da50f84bfdb4f57eb023b2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="d300b-102">VideoStreamDetail-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d300b-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d300b-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d300b-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d300b-104">In der VideoStreamDetail-Ansicht werden Informationen zu den einzelnen Videostreams in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d300b-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="d300b-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d300b-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d300b-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="d300b-106">Column</span></span></th>
<th><span data-ttu-id="d300b-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="d300b-107">Data Type</span></span></th>
<th><span data-ttu-id="d300b-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d300b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d300b-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="d300b-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="d300b-110">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d300b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="d300b-111"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="d300b-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="d300b-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="d300b-113">int</span><span class="sxs-lookup"><span data-stu-id="d300b-113">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-114"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="d300b-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="d300b-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="d300b-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="d300b-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d300b-117"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="d300b-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-118">Datenstrom-Nr</span><span class="sxs-lookup"><span data-stu-id="d300b-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="d300b-119">int</span><span class="sxs-lookup"><span data-stu-id="d300b-119">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-120">Eindeutige ID innerhalb einer Medienzeile.</span><span class="sxs-lookup"><span data-stu-id="d300b-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="d300b-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="d300b-122">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d300b-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="d300b-123">Startzeitpunkt der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="d300b-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="d300b-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="d300b-125">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d300b-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="d300b-126">Endzeitpunkt der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="d300b-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="d300b-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="d300b-128">int</span><span class="sxs-lookup"><span data-stu-id="d300b-128">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-129">Priorität des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d300b-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="d300b-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="d300b-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d300b-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d300b-132">FQDN des Anruferpools.</span><span class="sxs-lookup"><span data-stu-id="d300b-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="d300b-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="d300b-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d300b-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d300b-135">FQDN des Angerufenenpools.</span><span class="sxs-lookup"><span data-stu-id="d300b-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-136">Anrufer</span><span class="sxs-lookup"><span data-stu-id="d300b-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="d300b-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d300b-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d300b-138">URI des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d300b-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-139">Aufgerufene</span><span class="sxs-lookup"><span data-stu-id="d300b-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="d300b-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d300b-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d300b-141">URI des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d300b-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="d300b-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="d300b-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d300b-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d300b-144">Zeichenfolge für den Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d300b-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="d300b-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="d300b-146">smallint</span><span class="sxs-lookup"><span data-stu-id="d300b-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="d300b-147">Typ des Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d300b-147">Type of caller’s user agent.</span></span> <span data-ttu-id="d300b-148">Ausführliche Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d300b-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="d300b-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="d300b-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="d300b-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="d300b-151">Kategorie des Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d300b-151">Category of caller’s user agent.</span></span> <span data-ttu-id="d300b-152">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d300b-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="d300b-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="d300b-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d300b-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d300b-155">Zeichenfolge für den Benutzer-Agent des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d300b-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="d300b-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="d300b-157">smallint</span><span class="sxs-lookup"><span data-stu-id="d300b-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="d300b-158">Typ des Benutzer-Agent des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d300b-158">Type of callee’s user agent.</span></span> <span data-ttu-id="d300b-159">Weitere Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d300b-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="d300b-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="d300b-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="d300b-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="d300b-162">Kategorie des Benutzer-Agent des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d300b-162">Category of callee’s user agent.</span></span> <span data-ttu-id="d300b-163">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d300b-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="d300b-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="d300b-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d300b-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d300b-166">Name des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d300b-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="d300b-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="d300b-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d300b-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d300b-169">Name des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d300b-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-170">Anrufer</span><span class="sxs-lookup"><span data-stu-id="d300b-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="d300b-171">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="d300b-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d300b-172">Betriebssystem des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d300b-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="d300b-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="d300b-174">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="d300b-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d300b-175">Betriebssystem des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d300b-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="d300b-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="d300b-177">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="d300b-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d300b-178">Name der CPU des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d300b-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="d300b-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="d300b-180">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="d300b-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d300b-181">Name der CPU des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d300b-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="d300b-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="d300b-183">smallint</span><span class="sxs-lookup"><span data-stu-id="d300b-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="d300b-184">Anzahl der CPU-Kerne des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d300b-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="d300b-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="d300b-186">smallint</span><span class="sxs-lookup"><span data-stu-id="d300b-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="d300b-187">Anzahl der CPU-Kerne des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d300b-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="d300b-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="d300b-189">int</span><span class="sxs-lookup"><span data-stu-id="d300b-189">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-190">Prozessorgeschwindigkeit der CPU des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d300b-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="d300b-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="d300b-192">int</span><span class="sxs-lookup"><span data-stu-id="d300b-192">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-193">Prozessorgeschwindigkeit der CPU des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d300b-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="d300b-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="d300b-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="d300b-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d300b-196">Gibt an, ob das System des Anrufers in einer virtualisierten Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d300b-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="d300b-197">Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpoint-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d300b-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="d300b-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="d300b-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="d300b-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d300b-200">Gibt an, ob das System des Angerufenen in einer virtualisierten Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d300b-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="d300b-201">Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpoint-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d300b-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="d300b-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="d300b-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="d300b-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d300b-204">Informationen zum Medienpfad, z. B. direkt oder Relay.</span><span class="sxs-lookup"><span data-stu-id="d300b-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="d300b-205">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d300b-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="d300b-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="d300b-207">int</span><span class="sxs-lookup"><span data-stu-id="d300b-207">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-p109">Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Anrufer, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".</span><span class="sxs-lookup"><span data-stu-id="d300b-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="d300b-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="d300b-211">int</span><span class="sxs-lookup"><span data-stu-id="d300b-211">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-p110">Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Angerufenen, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".</span><span class="sxs-lookup"><span data-stu-id="d300b-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-214">Transport</span><span class="sxs-lookup"><span data-stu-id="d300b-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="d300b-215">int</span><span class="sxs-lookup"><span data-stu-id="d300b-215">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-216">Transporttyp: 0 ist UDP, 1 ist TCP.</span><span class="sxs-lookup"><span data-stu-id="d300b-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="d300b-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d300b-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="d300b-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d300b-219">IP-Adresse des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d300b-219">IP address of the caller.</span></span> <span data-ttu-id="d300b-220">Dies kann eine IPv4- oder eine IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="d300b-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="d300b-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="d300b-222">int</span><span class="sxs-lookup"><span data-stu-id="d300b-222">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-223">Vom Anrufer verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="d300b-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="d300b-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="d300b-225">Bit</span><span class="sxs-lookup"><span data-stu-id="d300b-225">bit</span></span></p></td>
<td><p><span data-ttu-id="d300b-p112">Gibt an, ob der Anrufer sich innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, der Anrufer befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Anrufer befindet sich außerhalb davon.</span><span class="sxs-lookup"><span data-stu-id="d300b-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="d300b-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d300b-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="d300b-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d300b-230">IP-Adresse des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d300b-230">IP address of the callee.</span></span> <span data-ttu-id="d300b-231">Dies kann eine IPv4- oder eine IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="d300b-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="d300b-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="d300b-233">int</span><span class="sxs-lookup"><span data-stu-id="d300b-233">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-234">Vom Angerufenen verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="d300b-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="d300b-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="d300b-236">Bit</span><span class="sxs-lookup"><span data-stu-id="d300b-236">bit</span></span></p></td>
<td><p><span data-ttu-id="d300b-237">Gibt an, ob der Angerufene sich innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, der Angerufene befindet sich im Unternehmensnetzwerk, 0 bedeutet, der Angerufene befindet sich außerhalb davon.</span><span class="sxs-lookup"><span data-stu-id="d300b-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="d300b-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="d300b-239">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="d300b-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d300b-240">Name der Website des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d300b-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="d300b-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="d300b-242">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="d300b-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d300b-243">Name des Landes/der Region der Website des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d300b-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="d300b-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="d300b-245">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="d300b-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d300b-246">Name der Website des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d300b-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="d300b-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="d300b-248">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="d300b-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d300b-249">Name des Landes/der Region der Website des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d300b-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="d300b-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d300b-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="d300b-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d300b-252">IP-Adresse des vom Anrufer verwendeten A/V-Edgedienstes.</span><span class="sxs-lookup"><span data-stu-id="d300b-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="d300b-253">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d300b-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="d300b-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="d300b-255">int</span><span class="sxs-lookup"><span data-stu-id="d300b-255">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-256">Port auf dem vom Anrufer verwendeten A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="d300b-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="d300b-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d300b-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="d300b-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d300b-259">IP-Adressschlüssel des vom Anrufer verwendeten A/V-Edgedienstes.</span><span class="sxs-lookup"><span data-stu-id="d300b-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="d300b-260">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d300b-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="d300b-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="d300b-262">int</span><span class="sxs-lookup"><span data-stu-id="d300b-262">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-263">Port auf dem vom Angerufenen verwendeten A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="d300b-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="d300b-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="d300b-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d300b-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d300b-266">Name des Aufnahmegeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d300b-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="d300b-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="d300b-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d300b-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d300b-269">Name des Darstellungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d300b-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="d300b-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d300b-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d300b-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d300b-272">Name des Gerätetreibers des Aufnahmegeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d300b-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="d300b-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d300b-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d300b-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d300b-275">Name des Gerätetreibers des Darstellungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d300b-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="d300b-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="d300b-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d300b-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d300b-278">Name des Aufnahmegeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d300b-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="d300b-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="d300b-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d300b-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d300b-281">Name des Darstellungsgeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d300b-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="d300b-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d300b-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d300b-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d300b-284">Name des Gerätetreibers des Aufnahmegeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d300b-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="d300b-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d300b-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d300b-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d300b-287">Name des Gerätetreibers des Darstellungsgeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d300b-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="d300b-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="d300b-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="d300b-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d300b-290">Typ der Netzwerkverbindung des Anrufers: 0 ist verkabelt, 1 ist kabellos.</span><span class="sxs-lookup"><span data-stu-id="d300b-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="d300b-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="d300b-292">Bit</span><span class="sxs-lookup"><span data-stu-id="d300b-292">bit</span></span></p></td>
<td><p><span data-ttu-id="d300b-p116">Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk (VPN) verbunden ist. 1 ist VPN, 0 ist Nicht-VPN.</span><span class="sxs-lookup"><span data-stu-id="d300b-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="d300b-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="d300b-296">Decimal (18,)</span><span class="sxs-lookup"><span data-stu-id="d300b-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="d300b-297">Netzwerkübertragungsrate für den Endpunkt des Anrufers in Bit/s.</span><span class="sxs-lookup"><span data-stu-id="d300b-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="d300b-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="d300b-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="d300b-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d300b-300">Typ der Netzwerkverbindung des Angerufenen: 0 ist verkabelt, 1 ist kabellos.</span><span class="sxs-lookup"><span data-stu-id="d300b-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="d300b-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="d300b-302">Bit</span><span class="sxs-lookup"><span data-stu-id="d300b-302">bit</span></span></p></td>
<td><p><span data-ttu-id="d300b-p117">Gibt an, ob der Angerufene über ein virtuelles privates Netzwerk (VPN) verbunden ist. 1 ist VPN, 0 ist Nicht-VPN.</span><span class="sxs-lookup"><span data-stu-id="d300b-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="d300b-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="d300b-306">Decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="d300b-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="d300b-307">Netzwerkübertragungsrate für den Endpunkt des Angerufenen in Bit/s.</span><span class="sxs-lookup"><span data-stu-id="d300b-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="d300b-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="d300b-309">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d300b-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="d300b-310">Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).</span><span class="sxs-lookup"><span data-stu-id="d300b-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="d300b-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="d300b-312">int</span><span class="sxs-lookup"><span data-stu-id="d300b-312">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-p118">Tatsächliche Bandbreite, die unter verschiedenen Richtlinieneinstellungen (TURN, API, SDP, Richtlinienserver usw.) auf den jeweiligen Stream auf der Seite des Absenders angewendet wird. Dies ist nicht zu verwechseln mit der effektiven Bandbreite, da diese u. U. basierend auf der Bandbreitenschätzung niedriger ist. Dabei handelt es sich um die maximale Bandbreite, die für den Absenderstream möglich ist, abgesehen von den Beschränkungen durch die Bandbreitenschätzung.</span><span class="sxs-lookup"><span data-stu-id="d300b-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="d300b-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="d300b-317">int</span><span class="sxs-lookup"><span data-stu-id="d300b-317">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-318">Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="d300b-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="d300b-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="d300b-320">int</span><span class="sxs-lookup"><span data-stu-id="d300b-320">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-321">Maximaler Netzwerkjitter während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d300b-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-322">Roundtrip</span><span class="sxs-lookup"><span data-stu-id="d300b-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="d300b-323">int</span><span class="sxs-lookup"><span data-stu-id="d300b-323">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-324">Roundtripzeit aus RTCP-Statistik.</span><span class="sxs-lookup"><span data-stu-id="d300b-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="d300b-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="d300b-326">int</span><span class="sxs-lookup"><span data-stu-id="d300b-326">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-327">Maximale Roundtripzeit für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="d300b-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="d300b-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="d300b-329">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="d300b-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="d300b-330">Durchschnittliche Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d300b-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="d300b-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="d300b-332">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="d300b-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="d300b-333">Maximale Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d300b-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="d300b-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="d300b-335">int</span><span class="sxs-lookup"><span data-stu-id="d300b-335">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-336">Paketwert für den Videostream (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="d300b-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-337">Bandbreite</span><span class="sxs-lookup"><span data-stu-id="d300b-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="d300b-338">int</span><span class="sxs-lookup"><span data-stu-id="d300b-338">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-339">Bandbreitenschätzungen für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="d300b-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="d300b-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="d300b-341">int</span><span class="sxs-lookup"><span data-stu-id="d300b-341">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-342">Für den Anruf verwendeter Audiocodec, der <a href="lync-server-2013-payloaddescription-table.md">in lync Server 2013 in der PayloadDescription-Tabelle</a>referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="d300b-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="d300b-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="d300b-344">char (9)</span><span class="sxs-lookup"><span data-stu-id="d300b-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="d300b-p119">Auflösung des Videos in Pixel Breite x Höhe. Gemeldet als Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d300b-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="d300b-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="d300b-348">int</span><span class="sxs-lookup"><span data-stu-id="d300b-348">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-349">Durchschnittliche Bitrate des Videostreams.</span><span class="sxs-lookup"><span data-stu-id="d300b-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="d300b-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="d300b-351">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="d300b-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="d300b-352">Empfangene Framerate des Videostreams.</span><span class="sxs-lookup"><span data-stu-id="d300b-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="d300b-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="d300b-354">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="d300b-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="d300b-355">Gesendete Framerate des Videostreams.</span><span class="sxs-lookup"><span data-stu-id="d300b-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="d300b-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="d300b-357">int</span><span class="sxs-lookup"><span data-stu-id="d300b-357">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-358">Maximale Videobitrate während der Videositzung.</span><span class="sxs-lookup"><span data-stu-id="d300b-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="d300b-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="d300b-360">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="d300b-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="d300b-361">Videpaketverlustrate.</span><span class="sxs-lookup"><span data-stu-id="d300b-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="d300b-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="d300b-363">Decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="d300b-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="d300b-364">Prozentsatz der verlorenen Videoframes von der Gesamtzahl der Videoframes.</span><span class="sxs-lookup"><span data-stu-id="d300b-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="d300b-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="d300b-366">Bit</span><span class="sxs-lookup"><span data-stu-id="d300b-366">bit</span></span></p></td>
<td><p><span data-ttu-id="d300b-367">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d300b-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="d300b-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="d300b-369">int</span><span class="sxs-lookup"><span data-stu-id="d300b-369">int</span></span></p></td>
<td><p><span data-ttu-id="d300b-370">Durchschnittliche für Video reservierte Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="d300b-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d300b-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="d300b-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="d300b-372">Decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="d300b-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="d300b-373">Durchschnittlicher Prozentsatz der gesamten Videoframes, die verloren gingen.</span><span class="sxs-lookup"><span data-stu-id="d300b-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d300b-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="d300b-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="d300b-375">Bit</span><span class="sxs-lookup"><span data-stu-id="d300b-375">bit</span></span></p></td>
<td><p><span data-ttu-id="d300b-p120">Streamrichtung für PAI-Informationen (P-Asserted-Identity). 1 bedeutet, die Streamrichtung verläuft vom Anrufer zum Angerufenen. 0 bedeutet, die Streamrichtung verläuft vom Angerufenen zum Anrufer.</span><span class="sxs-lookup"><span data-stu-id="d300b-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

