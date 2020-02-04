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
ms.openlocfilehash: dfa754fbcc24377b07bab3b13473adb1c5e953ea
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="d7d70-102">VideoStreamDetail-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7d70-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7d70-103">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d7d70-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d7d70-104">In der VideoStreamDetail-Ansicht werden Informationen zu den einzelnen Videodatenströmen in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d7d70-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="d7d70-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d7d70-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7d70-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="d7d70-106">Column</span></span></th>
<th><span data-ttu-id="d7d70-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="d7d70-107">Data Type</span></span></th>
<th><span data-ttu-id="d7d70-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7d70-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="d7d70-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="d7d70-110">datetime</span><span class="sxs-lookup"><span data-stu-id="d7d70-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="d7d70-111">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d7d70-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="d7d70-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="d7d70-113">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-113">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-114">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d7d70-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="d7d70-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="d7d70-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7d70-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d7d70-117">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d7d70-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-118">Datenstrom-Nr</span><span class="sxs-lookup"><span data-stu-id="d7d70-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="d7d70-119">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-119">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-120">Eindeutige ID innerhalb einer medienzeile</span><span class="sxs-lookup"><span data-stu-id="d7d70-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="d7d70-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="d7d70-122">datetime</span><span class="sxs-lookup"><span data-stu-id="d7d70-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="d7d70-123">Startzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="d7d70-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="d7d70-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="d7d70-125">datetime</span><span class="sxs-lookup"><span data-stu-id="d7d70-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="d7d70-126">Endzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="d7d70-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="d7d70-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="d7d70-128">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-128">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-129">Die Priorität des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d7d70-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="d7d70-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="d7d70-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d7d70-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-132">FQDN des anrufenden Pools.</span><span class="sxs-lookup"><span data-stu-id="d7d70-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="d7d70-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="d7d70-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d7d70-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-135">FQDN des aufgerufenen Pools.</span><span class="sxs-lookup"><span data-stu-id="d7d70-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-136">Anrufer</span><span class="sxs-lookup"><span data-stu-id="d7d70-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="d7d70-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d7d70-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-138">URI des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-139">Callee</span><span class="sxs-lookup"><span data-stu-id="d7d70-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="d7d70-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d7d70-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-141">URI des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="d7d70-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="d7d70-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="d7d70-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d7d70-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-144">Benutzer-Agent-Zeichenfolge des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="d7d70-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="d7d70-146">smallint</span><span class="sxs-lookup"><span data-stu-id="d7d70-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="d7d70-147">Der Typ des Benutzer-Agents des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-147">Type of caller’s user agent.</span></span> <span data-ttu-id="d7d70-148">Weitere Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d7d70-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="d7d70-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="d7d70-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="d7d70-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-151">Kategorie des Benutzer-Agents des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-151">Category of caller’s user agent.</span></span> <span data-ttu-id="d7d70-152">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d7d70-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="d7d70-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="d7d70-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d7d70-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-155">Benutzer-Agent-Zeichenfolge des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="d7d70-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="d7d70-157">smallint</span><span class="sxs-lookup"><span data-stu-id="d7d70-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="d7d70-158">Der Typ des Benutzer-Agents des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-158">Type of callee’s user agent.</span></span> <span data-ttu-id="d7d70-159">Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d7d70-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="d7d70-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="d7d70-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="d7d70-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-162">Kategorie des Benutzer-Agents des berufenen</span><span class="sxs-lookup"><span data-stu-id="d7d70-162">Category of callee’s user agent.</span></span> <span data-ttu-id="d7d70-163">Informationen hierzu finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d7d70-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="d7d70-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="d7d70-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d7d70-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-166">Der Endpunktname des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="d7d70-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="d7d70-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d7d70-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-169">Endpunktname des angerufenen</span><span class="sxs-lookup"><span data-stu-id="d7d70-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-170">Anrufer</span><span class="sxs-lookup"><span data-stu-id="d7d70-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="d7d70-171">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="d7d70-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-172">Betriebssystem (OS) des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="d7d70-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="d7d70-174">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="d7d70-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-175">Betriebssystem (OS) des Endpunkts des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="d7d70-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="d7d70-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="d7d70-177">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="d7d70-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-178">Der CPU-Name des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="d7d70-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="d7d70-180">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="d7d70-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-181">Der CPU-Name des Endpunkts des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="d7d70-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="d7d70-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="d7d70-183">smallint</span><span class="sxs-lookup"><span data-stu-id="d7d70-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="d7d70-184">Die Anzahl der CPU-Kerne des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="d7d70-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="d7d70-186">smallint</span><span class="sxs-lookup"><span data-stu-id="d7d70-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="d7d70-187">Die Anzahl von CPU-Kernen des Endpunkts des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="d7d70-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="d7d70-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="d7d70-189">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-189">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-190">CPU-Prozessorgeschwindigkeit des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="d7d70-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="d7d70-192">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-192">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-193">CPU-Prozessorgeschwindigkeit des Endpunkts des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="d7d70-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="d7d70-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="d7d70-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7d70-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d7d70-196">Gibt an, ob das System des Anrufers in einer virtualisierten Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d7d70-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="d7d70-197">Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpunkt Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d7d70-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="d7d70-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="d7d70-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7d70-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d7d70-200">Gibt an, ob das System des aufgerufenen in einer virtualisierten Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d7d70-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="d7d70-201">Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpunkt Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d7d70-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="d7d70-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="d7d70-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7d70-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d7d70-204">Informationen zu Medien Pfaden, beispielsweise direkt oder weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="d7d70-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="d7d70-205">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d7d70-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="d7d70-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="d7d70-207">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-207">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-208">Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der unter Bits-Flags für den Aufrufer beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="d7d70-208">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="d7d70-209">Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="d7d70-209">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="d7d70-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="d7d70-211">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-211">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-212">Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der in den Bits-Flags für den aufgerufenen beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="d7d70-212">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="d7d70-213">Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="d7d70-213">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-214">Transport</span><span class="sxs-lookup"><span data-stu-id="d7d70-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="d7d70-215">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-215">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-216">Transporttyp: 0 ist UDP, 1 ist TCP.</span><span class="sxs-lookup"><span data-stu-id="d7d70-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="d7d70-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d7d70-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7d70-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-219">Die IP-Adresse des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-219">IP address of the caller.</span></span> <span data-ttu-id="d7d70-220">Hierbei kann es sich entweder um eine IPv4-oder eine IPv6-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="d7d70-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="d7d70-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="d7d70-222">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-222">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-223">Der vom Aufrufer verwendete Port.</span><span class="sxs-lookup"><span data-stu-id="d7d70-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="d7d70-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="d7d70-225">bit</span><span class="sxs-lookup"><span data-stu-id="d7d70-225">bit</span></span></p></td>
<td><p><span data-ttu-id="d7d70-226">Gibt an, ob sich der Anrufer innerhalb des Organisationsnetzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="d7d70-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="d7d70-227">1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="d7d70-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="d7d70-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d7d70-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7d70-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-230">Die IP-Adresse des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="d7d70-230">IP address of the callee.</span></span> <span data-ttu-id="d7d70-231">Hierbei kann es sich entweder um eine IPv4-oder eine IPv6-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="d7d70-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="d7d70-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="d7d70-233">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-233">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-234">Port, der vom aufgerufenen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d7d70-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="d7d70-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="d7d70-236">bit</span><span class="sxs-lookup"><span data-stu-id="d7d70-236">bit</span></span></p></td>
<td><p><span data-ttu-id="d7d70-237">Gibt an, ob sich der Aufrufer innerhalb des Organisationsnetzwerks befindet. 1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass der Anrufer sich außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="d7d70-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="d7d70-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="d7d70-239">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="d7d70-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-240">Der Name der Website des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="d7d70-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="d7d70-242">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="d7d70-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-243">Name des Landes/der Region der Website des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="d7d70-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="d7d70-245">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="d7d70-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-246">Name der Website des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="d7d70-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="d7d70-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="d7d70-248">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="d7d70-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-249">Name des Landes/der Region der Website des berufenen.</span><span class="sxs-lookup"><span data-stu-id="d7d70-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="d7d70-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d7d70-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7d70-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-252">Die IP-Adresse des A/V-Edgedienst, der vom Aufrufer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d7d70-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="d7d70-253">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d7d70-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="d7d70-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="d7d70-255">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-255">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-256">Port des A/V-Edgedienst, der vom Anrufer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d7d70-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="d7d70-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d7d70-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="d7d70-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-259">Der IP-Adressen Schlüssel des A/V-Edgedienst, der vom aufgerufenen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d7d70-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="d7d70-260">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d7d70-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="d7d70-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="d7d70-262">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-262">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-263">Port auf dem A/V-Edgedienst, der vom aufgerufenen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d7d70-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="d7d70-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="d7d70-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7d70-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-266">Name des Aufnahmegeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="d7d70-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="d7d70-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7d70-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-269">Name des Render-Geräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="d7d70-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d7d70-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7d70-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-272">Name des Aufnahmegeräte Treibers des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="d7d70-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d7d70-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7d70-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-275">Name des Render-Gerätetreibers des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="d7d70-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="d7d70-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7d70-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-278">Der Name des Erfassungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="d7d70-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="d7d70-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7d70-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-281">Name des Render-Geräts.</span><span class="sxs-lookup"><span data-stu-id="d7d70-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="d7d70-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d7d70-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7d70-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-284">Der Name des Capture-Gerätetreibers des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="d7d70-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d7d70-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d7d70-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-287">Der Name des Render-Gerätetreibers des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="d7d70-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="d7d70-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="d7d70-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7d70-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d7d70-290">Netzwerkverbindungstyp des Anrufers: 0 ist verkabelt, 1 ist drahtlos.</span><span class="sxs-lookup"><span data-stu-id="d7d70-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="d7d70-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="d7d70-292">bit</span><span class="sxs-lookup"><span data-stu-id="d7d70-292">bit</span></span></p></td>
<td><p><span data-ttu-id="d7d70-293">Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="d7d70-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="d7d70-294">1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.</span><span class="sxs-lookup"><span data-stu-id="d7d70-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="d7d70-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="d7d70-296">Decimal (18;)</span><span class="sxs-lookup"><span data-stu-id="d7d70-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-297">Netzwerkverbindungsgeschwindigkeit für den Endpunkt des Anrufers in BPS.</span><span class="sxs-lookup"><span data-stu-id="d7d70-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="d7d70-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="d7d70-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7d70-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d7d70-300">Netzwerkverbindungstyp des anrufempfängers: 0 ist verkabelt, 1 ist drahtlos.</span><span class="sxs-lookup"><span data-stu-id="d7d70-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="d7d70-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="d7d70-302">bit</span><span class="sxs-lookup"><span data-stu-id="d7d70-302">bit</span></span></p></td>
<td><p><span data-ttu-id="d7d70-303">Gibt an, ob der aufgerufene über ein virtuelles privates Netzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="d7d70-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="d7d70-304">1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.</span><span class="sxs-lookup"><span data-stu-id="d7d70-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="d7d70-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="d7d70-306">Decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="d7d70-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-307">Netzwerkverbindungsgeschwindigkeit für den Endpunkt des aufgerufenen (in BPS).</span><span class="sxs-lookup"><span data-stu-id="d7d70-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="d7d70-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="d7d70-309">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="d7d70-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-310">Schmalband-Konversations-Mos der audiositzungen (basierend auf beiden Audiostreams).</span><span class="sxs-lookup"><span data-stu-id="d7d70-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="d7d70-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="d7d70-312">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-312">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-313">Tatsächliche Bandbreite, die auf den angegebenen Send-Seitenstrom angewendet wurde, wenn verschiedene Richtlinieneinstellungen angegeben wurden (Turn, API, SDP, Richtlinien Server usw.).</span><span class="sxs-lookup"><span data-stu-id="d7d70-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="d7d70-314">Dies sollte nicht mit der effektiven Bandbreite verwechselt werden, da auf der Grundlage der Bandbreitenschätzung eine geringere effektive Bandbreite vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="d7d70-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="d7d70-315">Dies ist im Grunde die maximale Bandbreite, die der sendedatenstrom sperren kann, wenn die Bandbreite geschätzt wird.</span><span class="sxs-lookup"><span data-stu-id="d7d70-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="d7d70-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="d7d70-317">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-317">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-318">Durchschnittlicher Netzwerk-Jitter aus RTCP-Statistiken (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="d7d70-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="d7d70-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="d7d70-320">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-320">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-321">Maximaler Netzwerk Jitter während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d7d70-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-322">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="d7d70-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="d7d70-323">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-323">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-324">Roundtrip-Zeit von RTCP-Statistiken</span><span class="sxs-lookup"><span data-stu-id="d7d70-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="d7d70-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="d7d70-326">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-326">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-327">Maximale Roundtrip-Zeit für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="d7d70-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="d7d70-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="d7d70-329">Dezimal (5; 4)</span><span class="sxs-lookup"><span data-stu-id="d7d70-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-330">Durchschnittliche Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d7d70-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="d7d70-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="d7d70-332">Dezimal (5; 4)</span><span class="sxs-lookup"><span data-stu-id="d7d70-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-333">Maximaler Paketverlust während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d7d70-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="d7d70-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="d7d70-335">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-335">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-336">Paketanzahl für den Videostream (Echt Zeit Transport Protokoll, RTP).</span><span class="sxs-lookup"><span data-stu-id="d7d70-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-337">Bandbreite</span><span class="sxs-lookup"><span data-stu-id="d7d70-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="d7d70-338">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-338">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-339">Bandbreiten Schätzungen für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="d7d70-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="d7d70-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="d7d70-341">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-341">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-342">Für den Anruf verwendeter Audiocodec, auf den aus der <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription-Tabelle in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d7d70-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="d7d70-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="d7d70-344">char (9)</span><span class="sxs-lookup"><span data-stu-id="d7d70-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-345">Auflösung des Videos in Pixel Breite multipliziert mit Höhe des Pixels.</span><span class="sxs-lookup"><span data-stu-id="d7d70-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="d7d70-346">Als Zeichenfolge gemeldet.</span><span class="sxs-lookup"><span data-stu-id="d7d70-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="d7d70-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="d7d70-348">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-348">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-349">Durchschnittliche Bitrate des Videodatenstroms.</span><span class="sxs-lookup"><span data-stu-id="d7d70-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="d7d70-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="d7d70-351">Dezimal (9; 4)</span><span class="sxs-lookup"><span data-stu-id="d7d70-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-352">Bildrate des empfangenen Videos.</span><span class="sxs-lookup"><span data-stu-id="d7d70-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="d7d70-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="d7d70-354">Dezimal (9; 4)</span><span class="sxs-lookup"><span data-stu-id="d7d70-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-355">Bildrate des gesendeten Videos.</span><span class="sxs-lookup"><span data-stu-id="d7d70-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="d7d70-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="d7d70-357">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-357">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-358">Maximale Video Bitrate während der Videositzung.</span><span class="sxs-lookup"><span data-stu-id="d7d70-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="d7d70-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="d7d70-360">Dezimal (9; 4)</span><span class="sxs-lookup"><span data-stu-id="d7d70-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-361">Die Rate, mit der Videopakete verloren gegangen sind.</span><span class="sxs-lookup"><span data-stu-id="d7d70-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="d7d70-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="d7d70-363">Decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="d7d70-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-364">Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="d7d70-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="d7d70-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="d7d70-366">bit</span><span class="sxs-lookup"><span data-stu-id="d7d70-366">bit</span></span></p></td>
<td><p><span data-ttu-id="d7d70-367">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7d70-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="d7d70-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="d7d70-369">int</span><span class="sxs-lookup"><span data-stu-id="d7d70-369">int</span></span></p></td>
<td><p><span data-ttu-id="d7d70-370">Der durchschnittliche Umfang der für Video zugewiesenen Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="d7d70-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7d70-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="d7d70-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="d7d70-372">Decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="d7d70-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="d7d70-373">Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gegangen sind.</span><span class="sxs-lookup"><span data-stu-id="d7d70-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7d70-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="d7d70-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="d7d70-375">bit</span><span class="sxs-lookup"><span data-stu-id="d7d70-375">bit</span></span></p></td>
<td><p><span data-ttu-id="d7d70-376">Datenstrom Richtung für p-asserted Identity-Informationen.</span><span class="sxs-lookup"><span data-stu-id="d7d70-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="d7d70-377">1 bedeutet, dass die Datenstrom Richtung vom Anrufer an den aufgerufenen erfolgt; 0 bedeutet, dass die Datenstrom Richtung vom aufgerufenen zum Aufrufer ist.</span><span class="sxs-lookup"><span data-stu-id="d7d70-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

