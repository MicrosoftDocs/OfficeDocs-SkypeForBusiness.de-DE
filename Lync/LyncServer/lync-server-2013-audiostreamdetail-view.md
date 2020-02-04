---
title: 'Lync Server 2013: AudioStreamDetail-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cebcd47d735f1779396c0272877c0ec64a6189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="83f14-102">AudioStreamDetail-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83f14-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83f14-103">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="83f14-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="83f14-104">In der AudioStreamDetail-Ansicht werden Informationen zu jedem Audiostream in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="83f14-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="83f14-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="83f14-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83f14-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="83f14-106">Column</span></span></th>
<th><span data-ttu-id="83f14-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="83f14-107">Data Type</span></span></th>
<th><span data-ttu-id="83f14-108">Details</span><span class="sxs-lookup"><span data-stu-id="83f14-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83f14-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="83f14-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="83f14-110">datetime</span><span class="sxs-lookup"><span data-stu-id="83f14-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="83f14-111">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="83f14-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="83f14-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="83f14-113">int</span><span class="sxs-lookup"><span data-stu-id="83f14-113">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-114">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="83f14-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-115">Datenstrom-Nr</span><span class="sxs-lookup"><span data-stu-id="83f14-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="83f14-116">int</span><span class="sxs-lookup"><span data-stu-id="83f14-116">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-117">Eindeutige ID innerhalb einer medienzeile</span><span class="sxs-lookup"><span data-stu-id="83f14-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="83f14-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="83f14-119">datetime</span><span class="sxs-lookup"><span data-stu-id="83f14-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="83f14-120">Startzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="83f14-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="83f14-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="83f14-122">datetime</span><span class="sxs-lookup"><span data-stu-id="83f14-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="83f14-123">Endzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="83f14-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="83f14-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="83f14-125">bit</span><span class="sxs-lookup"><span data-stu-id="83f14-125">bit</span></span></p></td>
<td><p><span data-ttu-id="83f14-126">Dialog Feld Kategorie: 0 ist der lync Server to Mediation Server Leg; 1 ist der Vermittlungs Server für das PSTN-Gateway-Bein.</span><span class="sxs-lookup"><span data-stu-id="83f14-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="83f14-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="83f14-128">bit</span><span class="sxs-lookup"><span data-stu-id="83f14-128">bit</span></span></p></td>
<td><p><span data-ttu-id="83f14-129">Flag, das angibt, ob der Anruf umgangen wurde oder nicht.</span><span class="sxs-lookup"><span data-stu-id="83f14-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="83f14-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="83f14-131">int</span><span class="sxs-lookup"><span data-stu-id="83f14-131">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-132">Wenn vorhanden, gibt an, warum ein Anruf nicht umgangen wurde, auch wenn die Bypass-IDs zugeordnet wurden.</span><span class="sxs-lookup"><span data-stu-id="83f14-132">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="83f14-133">Es wird nur ein Wert definiert:</span><span class="sxs-lookup"><span data-stu-id="83f14-133">Only one value is defined:</span></span></p>
<p><span data-ttu-id="83f14-134">0x0001 – unbekannte Bypass-ID für den standardmäßigen Netzwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="83f14-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="83f14-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="83f14-136">int</span><span class="sxs-lookup"><span data-stu-id="83f14-136">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-137">Die Priorität des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="83f14-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="83f14-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="83f14-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="83f14-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83f14-140">FQDN des anrufenden Pools.</span><span class="sxs-lookup"><span data-stu-id="83f14-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="83f14-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="83f14-142">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="83f14-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83f14-143">FQDN des aufgerufenen Pools.</span><span class="sxs-lookup"><span data-stu-id="83f14-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-144">Anrufer</span><span class="sxs-lookup"><span data-stu-id="83f14-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="83f14-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="83f14-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="83f14-146">URI des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-147">Callee</span><span class="sxs-lookup"><span data-stu-id="83f14-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="83f14-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="83f14-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="83f14-149">URI des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="83f14-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="83f14-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="83f14-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="83f14-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83f14-152">Benutzer-Agent-Zeichenfolge des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="83f14-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="83f14-154">smallint</span><span class="sxs-lookup"><span data-stu-id="83f14-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="83f14-155">Der Typ des Benutzer-Agents des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="83f14-156">Weitere Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="83f14-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="83f14-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="83f14-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="83f14-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="83f14-159">Kategorie des Benutzer-Agents des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="83f14-160">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="83f14-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="83f14-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="83f14-162">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="83f14-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83f14-163">Benutzer-Agent-Zeichenfolge des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="83f14-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="83f14-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="83f14-165">smallint</span><span class="sxs-lookup"><span data-stu-id="83f14-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="83f14-166">Der Typ des Benutzer-Agents des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="83f14-166">Type of callee’s user agent.</span></span> <span data-ttu-id="83f14-167">Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="83f14-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="83f14-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="83f14-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="83f14-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="83f14-170">Kategorie des Benutzer-Agents des berufenen</span><span class="sxs-lookup"><span data-stu-id="83f14-170">Category of callee’s user agent.</span></span> <span data-ttu-id="83f14-171">Informationen hierzu finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="83f14-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="83f14-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="83f14-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="83f14-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83f14-174">Der Endpunktname des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="83f14-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="83f14-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="83f14-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83f14-177">Endpunktname des angerufenen</span><span class="sxs-lookup"><span data-stu-id="83f14-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-178">Anrufer</span><span class="sxs-lookup"><span data-stu-id="83f14-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="83f14-179">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="83f14-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="83f14-180">Betriebssystem (OS) des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="83f14-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="83f14-182">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="83f14-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="83f14-183">Betriebssystem (OS) des Endpunkts des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="83f14-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="83f14-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="83f14-185">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="83f14-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="83f14-186">Der CPU-Name des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="83f14-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="83f14-188">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="83f14-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="83f14-189">Der CPU-Name des Endpunkts des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="83f14-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="83f14-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="83f14-191">smallint</span><span class="sxs-lookup"><span data-stu-id="83f14-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="83f14-192">Die Anzahl der CPU-Kerne im Endpunkt des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="83f14-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="83f14-194">smallint</span><span class="sxs-lookup"><span data-stu-id="83f14-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="83f14-195">Die Anzahl der CPU-Kerne im Endpunkt des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="83f14-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="83f14-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="83f14-197">int</span><span class="sxs-lookup"><span data-stu-id="83f14-197">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-198">CPU-Prozessorgeschwindigkeit des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="83f14-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="83f14-200">int</span><span class="sxs-lookup"><span data-stu-id="83f14-200">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-201">CPU-Prozessorgeschwindigkeit des Endpunkts des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="83f14-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="83f14-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="83f14-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="83f14-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="83f14-204">Gibt an, ob das System des Anrufers in einer virtualisierten Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="83f14-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="83f14-205">Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpunkt Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="83f14-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="83f14-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="83f14-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="83f14-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="83f14-208">Gibt an, ob das System des aufgerufenen in einer virtualisierten Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="83f14-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="83f14-209">Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpunkt Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="83f14-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="83f14-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="83f14-211">Korrelationsschlüssel</span><span class="sxs-lookup"><span data-stu-id="83f14-211">Correlation key.</span></span> <span data-ttu-id="83f14-212">Wird in der <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation-Tabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="83f14-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="83f14-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="83f14-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="83f14-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="83f14-215">Informationen zum Medienpfad, beispielsweise direkt oder weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="83f14-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="83f14-216">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="83f14-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="83f14-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="83f14-218">int</span><span class="sxs-lookup"><span data-stu-id="83f14-218">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-219">Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der unter Bits-Flags für den Aufrufer beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="83f14-219">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="83f14-220">Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="83f14-220">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="83f14-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="83f14-222">int</span><span class="sxs-lookup"><span data-stu-id="83f14-222">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-223">Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der in den Bits-Flags für den aufgerufenen beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="83f14-223">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="83f14-224">Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="83f14-224">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-225">Transport</span><span class="sxs-lookup"><span data-stu-id="83f14-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="83f14-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="83f14-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="83f14-227">Transporttyp: 0 ist UDP, 1 ist TCP.</span><span class="sxs-lookup"><span data-stu-id="83f14-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="83f14-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="83f14-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="83f14-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="83f14-230">Die IP-Adresse des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-230">IP address of the caller.</span></span> <span data-ttu-id="83f14-231">Hierbei kann es sich entweder um eine IPv4-oder eine IPv6-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="83f14-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="83f14-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="83f14-233">int</span><span class="sxs-lookup"><span data-stu-id="83f14-233">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-234">Der vom Aufrufer verwendete Port.</span><span class="sxs-lookup"><span data-stu-id="83f14-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="83f14-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="83f14-236">bit</span><span class="sxs-lookup"><span data-stu-id="83f14-236">bit</span></span></p></td>
<td><p><span data-ttu-id="83f14-237">Gibt an, ob sich der Aufrufer innerhalb des Intervall Netzwerks befindet: 1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="83f14-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="83f14-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="83f14-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="83f14-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="83f14-240">Die IP-Adresse des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="83f14-240">IP address of the callee.</span></span> <span data-ttu-id="83f14-241">Hierbei kann es sich entweder um eine IPv4-oder eine IPv6-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="83f14-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="83f14-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="83f14-243">int</span><span class="sxs-lookup"><span data-stu-id="83f14-243">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-244">Port, der vom aufgerufenen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="83f14-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="83f14-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="83f14-246">bit</span><span class="sxs-lookup"><span data-stu-id="83f14-246">bit</span></span></p></td>
<td><p><span data-ttu-id="83f14-247">Gibt an, ob sich der aufgerufene innerhalb des Intervall Netzwerks befindet: 1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass der Anrufer sich außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="83f14-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="83f14-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="83f14-249">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="83f14-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="83f14-250">Der Name der Website des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="83f14-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="83f14-252">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="83f14-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="83f14-253">Name des Landes/der Region der Website des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="83f14-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="83f14-255">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="83f14-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="83f14-256">Name der Website des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="83f14-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="83f14-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="83f14-258">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="83f14-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="83f14-259">Name des Landes/der Region der Website des berufenen.</span><span class="sxs-lookup"><span data-stu-id="83f14-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="83f14-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="83f14-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="83f14-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="83f14-262">Die IP-Adresse des A/V-Edgedienst, der vom Aufrufer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="83f14-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="83f14-263">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="83f14-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="83f14-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="83f14-265">int</span><span class="sxs-lookup"><span data-stu-id="83f14-265">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-266">Der Port des A/V-Edgedienst, der vom Aufrufer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="83f14-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="83f14-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="83f14-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="83f14-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="83f14-269">Der IP-Adressen Schlüssel des A/V-Edgedienst, der vom aufgerufenen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="83f14-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="83f14-270">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="83f14-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="83f14-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="83f14-272">int</span><span class="sxs-lookup"><span data-stu-id="83f14-272">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-273">Port, der für den A/V-Edgedienst verwendet wird, der vom aufgerufenen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="83f14-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="83f14-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="83f14-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83f14-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83f14-276">Name des Aufnahmegeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="83f14-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="83f14-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83f14-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83f14-279">Name des Render-Geräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="83f14-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="83f14-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83f14-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83f14-282">Name des Aufnahmegeräte Treibers des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="83f14-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="83f14-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83f14-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83f14-285">Name des Render-Gerätetreibers des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="83f14-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="83f14-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83f14-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83f14-288">Der Name des Erfassungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="83f14-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="83f14-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83f14-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83f14-291">Name des Render-Geräts.</span><span class="sxs-lookup"><span data-stu-id="83f14-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="83f14-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="83f14-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83f14-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83f14-294">Der Name des Capture-Gerätetreibers des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="83f14-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="83f14-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="83f14-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="83f14-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="83f14-297">Der Name des Render-Gerätetreibers des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="83f14-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="83f14-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="83f14-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="83f14-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="83f14-300">Netzwerkverbindungstyp des Anrufers: 0 ist verkabelt, 1 ist drahtlos.</span><span class="sxs-lookup"><span data-stu-id="83f14-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="83f14-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="83f14-302">bit</span><span class="sxs-lookup"><span data-stu-id="83f14-302">bit</span></span></p></td>
<td><p><span data-ttu-id="83f14-303">Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist: 1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.</span><span class="sxs-lookup"><span data-stu-id="83f14-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="83f14-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="83f14-305">Decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="83f14-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="83f14-306">Netzwerkverbindungsgeschwindigkeit für den Endpunkt des Anrufers in BPS.</span><span class="sxs-lookup"><span data-stu-id="83f14-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="83f14-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="83f14-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="83f14-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="83f14-309">Netzwerkverbindungstyp des anrufempfängers: 0 ist verkabelt, 1 ist drahtlos.</span><span class="sxs-lookup"><span data-stu-id="83f14-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="83f14-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="83f14-311">bit</span><span class="sxs-lookup"><span data-stu-id="83f14-311">bit</span></span></p></td>
<td><p><span data-ttu-id="83f14-312">Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist: 1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.</span><span class="sxs-lookup"><span data-stu-id="83f14-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="83f14-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="83f14-314">Decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="83f14-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="83f14-315">Netzwerkverbindungsgeschwindigkeit für den Endpunkt des aufgerufenen in BPS.</span><span class="sxs-lookup"><span data-stu-id="83f14-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="83f14-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="83f14-317">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-318">Schmalband-Konversations-Mos der audiositzungen (basierend auf beiden Audiostreams).</span><span class="sxs-lookup"><span data-stu-id="83f14-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="83f14-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="83f14-320">int</span><span class="sxs-lookup"><span data-stu-id="83f14-320">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-321">Tatsächliche Bandbreite, die auf den angegebenen Send-Seitenstrom angewendet wurde, wenn verschiedene Richtlinieneinstellungen angegeben wurden (Turn, API, SDP, Richtlinien Server usw.).</span><span class="sxs-lookup"><span data-stu-id="83f14-321">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="83f14-322">Dies sollte nicht mit der effektiven Bandbreite verwechselt werden, da auf der Grundlage der Bandbreitenschätzung eine geringere effektive Bandbreite vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="83f14-322">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="83f14-323">Dies ist im Grunde die maximale Bandbreite, die der sendedatenstrom sperren kann, wenn die Bandbreite geschätzt wird.</span><span class="sxs-lookup"><span data-stu-id="83f14-323">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="83f14-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="83f14-325">int</span><span class="sxs-lookup"><span data-stu-id="83f14-325">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-326">Durchschnittlicher Netzwerk-Jitter aus RTCP-Statistiken (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="83f14-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="83f14-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="83f14-328">int</span><span class="sxs-lookup"><span data-stu-id="83f14-328">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-329">Maximaler Netzwerk Jitter während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="83f14-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="83f14-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="83f14-331">Dezimal (5; 4)</span><span class="sxs-lookup"><span data-stu-id="83f14-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="83f14-332">Durchschnittliche Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="83f14-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="83f14-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="83f14-334">Dezimal (5; 4)</span><span class="sxs-lookup"><span data-stu-id="83f14-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="83f14-335">Maximaler Paketverlust während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="83f14-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="83f14-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="83f14-337">Dezimal (9; 4)</span><span class="sxs-lookup"><span data-stu-id="83f14-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="83f14-338">Durchschnittliche Dichte des Paketverlusts während des Ausbruchs von Verlusten während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="83f14-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="83f14-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="83f14-340">int</span><span class="sxs-lookup"><span data-stu-id="83f14-340">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-341">Durchschnittliche Dauer des Paketverlusts während des Ausbruchs von Verlusten während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="83f14-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="83f14-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="83f14-343">Dezimal (9; 4)</span><span class="sxs-lookup"><span data-stu-id="83f14-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="83f14-344">Durchschnittliche Dichte des Paketverlusts bei Lücken zwischen Bursts des Paketverlusts.</span><span class="sxs-lookup"><span data-stu-id="83f14-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="83f14-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="83f14-346">int</span><span class="sxs-lookup"><span data-stu-id="83f14-346">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-347">Durchschnittliche Dauer von Lücken zwischen Bursts des Paketverlusts.</span><span class="sxs-lookup"><span data-stu-id="83f14-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="83f14-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="83f14-349">int</span><span class="sxs-lookup"><span data-stu-id="83f14-349">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-350">Die Anzahl der Pakete für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="83f14-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-351">Bandbreite</span><span class="sxs-lookup"><span data-stu-id="83f14-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="83f14-352">int</span><span class="sxs-lookup"><span data-stu-id="83f14-352">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-353">Bandbreiten Schätzungen für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="83f14-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="83f14-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="83f14-355">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-356">Netzwerk-Mos-Verschlechterung für den gesamten Anruf.</span><span class="sxs-lookup"><span data-stu-id="83f14-356">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="83f14-357">Der Bereich ist 0,0 bis 5,0.</span><span class="sxs-lookup"><span data-stu-id="83f14-357">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="83f14-358">Diese Metrik zeigt die Menge, die das Netzwerk Mos aufgrund von Jitter und Paketverlust reduziert wurde.</span><span class="sxs-lookup"><span data-stu-id="83f14-358">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="83f14-359">Für akzeptable Qualität sollte es weniger als 0,5.</span><span class="sxs-lookup"><span data-stu-id="83f14-359">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="83f14-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="83f14-361">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-362">Maximaler Netzwerk-Mos-Abbau während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="83f14-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="83f14-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="83f14-364">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-365">Netzwerk-Mos-Beeinträchtigung durch Jitter.</span><span class="sxs-lookup"><span data-stu-id="83f14-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="83f14-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="83f14-367">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-368">Netzwerk-Mos-Beeinträchtigung durch Paketverlust.</span><span class="sxs-lookup"><span data-stu-id="83f14-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="83f14-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="83f14-370">int</span><span class="sxs-lookup"><span data-stu-id="83f14-370">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-371">Der für den Anruf verwendete Audiocodec, auf den von der <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription-Tabelle in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="83f14-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="83f14-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="83f14-373">int</span><span class="sxs-lookup"><span data-stu-id="83f14-373">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-374">Abtastrate für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="83f14-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="83f14-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="83f14-376">int</span><span class="sxs-lookup"><span data-stu-id="83f14-376">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-377">Analoger Gain-Regler für Audio-Signalpegel für das Audiosignal, das der Anrufer gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="83f14-377">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="83f14-378">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="83f14-378">The unit for this metric is dBmo.</span></span> <span data-ttu-id="83f14-379">Für akzeptable Qualität sollte es mindestens 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="83f14-379">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="83f14-380">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="83f14-380">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="83f14-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="83f14-382">int</span><span class="sxs-lookup"><span data-stu-id="83f14-382">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-383">Audio-Signalpegel für das Audiosignal, das der Anrufer empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="83f14-383">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="83f14-384">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="83f14-384">The unit for this metric is dBmo.</span></span> <span data-ttu-id="83f14-385">Für akzeptable Qualität sollte es mindestens 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="83f14-385">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="83f14-386">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="83f14-386">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="83f14-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="83f14-388">int</span><span class="sxs-lookup"><span data-stu-id="83f14-388">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-389">Nach analoger Gain-Regler Audio-Rauschpegel für das Audiosignal, das der Anrufer gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="83f14-389">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="83f14-390">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="83f14-390">The unit for this metric is dBmo.</span></span> <span data-ttu-id="83f14-391">Für akzeptable Qualität sollte es weniger als 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="83f14-391">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="83f14-392">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="83f14-392">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="83f14-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="83f14-394">int</span><span class="sxs-lookup"><span data-stu-id="83f14-394">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-395">Nach analoger Gain-Regler Audio-Rauschpegel für das Audiosignal, das der Anrufer empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="83f14-395">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="83f14-396">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="83f14-396">The unit for this metric is dBmo.</span></span> <span data-ttu-id="83f14-397">Für akzeptable Qualität sollte es weniger als 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="83f14-397">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="83f14-398">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="83f14-398">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="83f14-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="83f14-400">int</span><span class="sxs-lookup"><span data-stu-id="83f14-400">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-401">Verbesserung der Echo-Rückerstattung für den Anrufer.</span><span class="sxs-lookup"><span data-stu-id="83f14-401">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="83f14-402">Die Einheit für diese Metrik ist DB.</span><span class="sxs-lookup"><span data-stu-id="83f14-402">The unit for this metric is dB.</span></span> <span data-ttu-id="83f14-403">Niedrigere Werte stellen weniger Echo dar.</span><span class="sxs-lookup"><span data-stu-id="83f14-403">Lower values represent less echo.</span></span> <span data-ttu-id="83f14-404">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="83f14-404">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="83f14-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="83f14-406">int</span><span class="sxs-lookup"><span data-stu-id="83f14-406">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-407">Durchschnittliche Störimpulse pro fünf Minuten für die Lautsprecher-Wiedergabe des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-407">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="83f14-408">Für eine gute Qualität sollte dies weniger als eins pro fünf Minuten sein.</span><span class="sxs-lookup"><span data-stu-id="83f14-408">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="83f14-409">Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="83f14-409">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="83f14-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="83f14-411">int</span><span class="sxs-lookup"><span data-stu-id="83f14-411">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-412">Durchschnittliche Störimpulse pro fünf Minuten für die Mikrofonaufnahme des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-412">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="83f14-413">Für eine gute Qualität sollte dies weniger als eine pro fünf Minuten sein.</span><span class="sxs-lookup"><span data-stu-id="83f14-413">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="83f14-414">Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="83f14-414">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="83f14-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="83f14-416">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-417">Clock-Drift Rate des Anrufers im Verhältnis zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="83f14-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="83f14-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="83f14-419">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-420">Clock-Drift Rate des Anrufers für das Lautsprecher Gerät relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="83f14-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="83f14-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="83f14-422">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-423">Durchschnittlicher Zeitstempel des Mikrofon-Datenstroms in Millisekunden in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="83f14-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="83f14-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="83f14-425">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-426">Der Durchschnitt des Sprechers des Sprechers Render-Datenstrom Zeitstempel-Fehler in Millisekunden in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="83f14-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="83f14-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="83f14-428">smallint</span><span class="sxs-lookup"><span data-stu-id="83f14-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="83f14-429">Voice-Switch ist ein Halbduplex-Modus mit verminderter Unterbrechungs Fähigkeit.</span><span class="sxs-lookup"><span data-stu-id="83f14-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="83f14-430">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="83f14-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="83f14-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="83f14-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="83f14-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="83f14-433">Ursachen für ein Echo Ereignis für den Aufrufer.</span><span class="sxs-lookup"><span data-stu-id="83f14-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="83f14-434">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="83f14-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="83f14-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="83f14-436">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-437">Prozentsatz der Zeit, zu der ECHO im Mikrofonaufnahme Datenstrom des Anrufers erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="83f14-437">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="83f14-438">Wenn Headset verwendet wird, sollte der Wert gering sein.</span><span class="sxs-lookup"><span data-stu-id="83f14-438">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="83f14-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="83f14-440">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-441">Prozentsatz der Zeit, zu der ECHO im gesendeten Datenstrom des Anrufers erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="83f14-441">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="83f14-442">Ein großer Prozentsatz des Echos in Send-Streams zeigt einen Hinweis auf Echo Verluste.</span><span class="sxs-lookup"><span data-stu-id="83f14-442">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="83f14-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="83f14-444">int</span><span class="sxs-lookup"><span data-stu-id="83f14-444">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-445">Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway für das Audiosignal des Anrufers; Dies gilt nur für den Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="83f14-445">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="83f14-446">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="83f14-446">The unit of this metric is dBoV.</span></span> <span data-ttu-id="83f14-447">Für eine gute Qualität sollte der zulässige Bereich-30 bis-18 dBoV sein.</span><span class="sxs-lookup"><span data-stu-id="83f14-447">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="83f14-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="83f14-449">int</span><span class="sxs-lookup"><span data-stu-id="83f14-449">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-450">Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway für das Audiosignal des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-450">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="83f14-451">Dies gilt nur für den Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="83f14-451">This applies only to the Mediation Server.</span></span> <span data-ttu-id="83f14-452">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="83f14-452">The unit of this metric is dBoV.</span></span> <span data-ttu-id="83f14-453">Für eine gute Qualität sollte der zulässige Bereich kleiner als-50 dBoV sein.</span><span class="sxs-lookup"><span data-stu-id="83f14-453">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="83f14-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="83f14-455">int</span><span class="sxs-lookup"><span data-stu-id="83f14-455">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-456">Automatische Gain-Steuerung (AGC) auf der Mediation Server-Seite, die auf das Audiosignal des Anrufers angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="83f14-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="83f14-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="83f14-458">float</span><span class="sxs-lookup"><span data-stu-id="83f14-458">float</span></span></p></td>
<td><p><span data-ttu-id="83f14-459">Root Mean Square (RMS) des eingehenden Signals an den Anrufer für bis zu den ersten 30 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="83f14-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="83f14-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="83f14-461">int</span><span class="sxs-lookup"><span data-stu-id="83f14-461">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-462">Stellt die analogen Gain-Regler-Audiosignale für das Audiosignal dar, das der Anrufer gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="83f14-462">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="83f14-463">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="83f14-463">The unit for this metric is dBmo.</span></span> <span data-ttu-id="83f14-464">Für akzeptable Qualität sollte es mindestens 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="83f14-464">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="83f14-465">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="83f14-465">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="83f14-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="83f14-467">int</span><span class="sxs-lookup"><span data-stu-id="83f14-467">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-468">Audiosignal Pegel für das Audiosignal, das der Anrufer empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="83f14-468">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="83f14-469">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="83f14-469">The unit for this metric is dBmo.</span></span> <span data-ttu-id="83f14-470">Für akzeptable Qualität sollte es mindestens 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="83f14-470">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="83f14-471">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="83f14-471">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="83f14-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="83f14-473">int</span><span class="sxs-lookup"><span data-stu-id="83f14-473">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-474">Post-Analog-Gain-Regler Audio-Rauschpegel für das Audiosignal, das der Anrufer gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="83f14-474">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="83f14-475">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="83f14-475">The unit for this metric is dBmo.</span></span> <span data-ttu-id="83f14-476">Für akzeptable Qualität sollte es weniger als 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="83f14-476">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="83f14-477">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="83f14-477">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="83f14-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="83f14-479">int</span><span class="sxs-lookup"><span data-stu-id="83f14-479">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-480">Analoger Gain-Regler Audio-Rauschpegel für das Audiosignal, das der Anrufer empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="83f14-480">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="83f14-481">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="83f14-481">The unit for this metric is dBmo.</span></span> <span data-ttu-id="83f14-482">Für akzeptable Qualität sollte es weniger als 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="83f14-482">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="83f14-483">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="83f14-483">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="83f14-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="83f14-485">int</span><span class="sxs-lookup"><span data-stu-id="83f14-485">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-486">Verbesserung der Echo-Rückerstattung für den aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="83f14-486">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="83f14-487">Die Einheit für diese Metrik ist DB.</span><span class="sxs-lookup"><span data-stu-id="83f14-487">The unit for this metric is dB.</span></span> <span data-ttu-id="83f14-488">Niedrigere Werte stellen weniger Echo dar.</span><span class="sxs-lookup"><span data-stu-id="83f14-488">Lower values represent less echo.</span></span> <span data-ttu-id="83f14-489">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="83f14-489">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="83f14-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="83f14-491">int</span><span class="sxs-lookup"><span data-stu-id="83f14-491">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-492">Durchschnittliche Störgeräusche pro fünf Minuten für die Lautsprecher-Darstellung des anrufenden.</span><span class="sxs-lookup"><span data-stu-id="83f14-492">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="83f14-493">Für eine gute Qualität sollte dies weniger als eins pro fünf Minuten sein.</span><span class="sxs-lookup"><span data-stu-id="83f14-493">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="83f14-494">Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="83f14-494">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="83f14-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="83f14-496">int</span><span class="sxs-lookup"><span data-stu-id="83f14-496">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-497">Durchschnittliche Störimpulse pro fünf Minuten für die Mikrofonaufnahme des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="83f14-497">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="83f14-498">Für eine gute Qualität sollte dies weniger als eine pro fünf Minuten sein.</span><span class="sxs-lookup"><span data-stu-id="83f14-498">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="83f14-499">Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="83f14-499">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="83f14-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="83f14-501">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-502">Abdriftrate des Mikrofon Geräts des Anrufers, relativ zu CPU-Takt.</span><span class="sxs-lookup"><span data-stu-id="83f14-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="83f14-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="83f14-504">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-505">Clock-Drift Rate des Anrufers für das Lautsprecher Gerät relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="83f14-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="83f14-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="83f14-507">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-508">Durchschnittlicher Zeitstempel des Mikrofon-Datenstroms in Millisekunden in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="83f14-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="83f14-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="83f14-510">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-511">Der Durchschnitt des Sprechers des Speaker-Render-Datenstrom Zeitstempels in Millisekunden in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="83f14-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="83f14-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="83f14-513">smallint</span><span class="sxs-lookup"><span data-stu-id="83f14-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="83f14-514">Voice-Switch ist ein Halbduplex-Modus mit verminderter Unterbrechungs Fähigkeit.</span><span class="sxs-lookup"><span data-stu-id="83f14-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="83f14-515">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="83f14-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="83f14-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="83f14-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="83f14-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="83f14-518">Ursachen für ein Echo Ereignis für den aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="83f14-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="83f14-519">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="83f14-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="83f14-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="83f14-521">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-522">Prozentsatz der Zeit, zu der ECHO im Mikrofonaufnahme Datenstrom des berufenen erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="83f14-522">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="83f14-523">Wenn Headset verwendet wird, sollte der Wert gering sein.</span><span class="sxs-lookup"><span data-stu-id="83f14-523">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="83f14-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="83f14-525">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-526">Der Prozentsatz der Zeit, zu der ECHO im gesendeten Datenstrom des aufgerufenen erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="83f14-526">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="83f14-527">Ein großer Prozentsatz des Echos in Send-Streams zeigt einen Hinweis auf Echo Verluste.</span><span class="sxs-lookup"><span data-stu-id="83f14-527">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="83f14-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="83f14-529">int</span><span class="sxs-lookup"><span data-stu-id="83f14-529">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-530">Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway für das Audio des berufenen; Dies gilt nur für den Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="83f14-530">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="83f14-531">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="83f14-531">The unit of this metric is dBoV.</span></span> <span data-ttu-id="83f14-532">Für eine gute Qualität sollte der zulässige Bereich [-30 bis-18] dBoV sein.</span><span class="sxs-lookup"><span data-stu-id="83f14-532">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="83f14-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="83f14-534">int</span><span class="sxs-lookup"><span data-stu-id="83f14-534">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-535">Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway für das Audio des berufenen.</span><span class="sxs-lookup"><span data-stu-id="83f14-535">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="83f14-536">Dies gilt nur für den Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="83f14-536">This applies only to the Mediation Server.</span></span> <span data-ttu-id="83f14-537">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="83f14-537">The unit of this metric is dBoV.</span></span> <span data-ttu-id="83f14-538">Für eine gute Qualität sollte der zulässige Bereich kleiner als-50 dBoV sein.</span><span class="sxs-lookup"><span data-stu-id="83f14-538">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="83f14-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="83f14-540">int</span><span class="sxs-lookup"><span data-stu-id="83f14-540">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-541">Automatische Gain-Steuerung (AGC) auf der Mediation Server-Seite, die auf die Audiofunktion des berufenen angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="83f14-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="83f14-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="83f14-543">float</span><span class="sxs-lookup"><span data-stu-id="83f14-543">float</span></span></p></td>
<td><p><span data-ttu-id="83f14-544">Root Mean Square (RMS) des eingehenden Signals an den Anrufer für bis zu den ersten 30 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="83f14-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="83f14-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="83f14-546">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-547">Durchschnittliches Verhältnis der verborgenen Samples, die von der audioheilung an typische Samples generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="83f14-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="83f14-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="83f14-549">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-550">Durchschnittliches Verhältnis von gedehnten Samples, die von der audioheilung zu typischen Samples generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="83f14-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="83f14-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="83f14-552">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-553">Durchschnittliches Verhältnis von komprimierten Samples, die von der audioheilung zu typischen Samples generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="83f14-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-554">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="83f14-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="83f14-555">int</span><span class="sxs-lookup"><span data-stu-id="83f14-555">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-556">Roundtrip-Zeit von RTCP-Statistiken</span><span class="sxs-lookup"><span data-stu-id="83f14-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="83f14-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="83f14-558">int</span><span class="sxs-lookup"><span data-stu-id="83f14-558">int</span></span></p></td>
<td><p><span data-ttu-id="83f14-559">Maximale Roundtrip-Zeit für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="83f14-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="83f14-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="83f14-561">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-562">Durchschnittliche Breitband-Netzwerk-Mos für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="83f14-562">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="83f14-563">Diese Metrik hängt vom verwendeten Paketverlust, Jitter und Codec ab.</span><span class="sxs-lookup"><span data-stu-id="83f14-563">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="83f14-564">Der Bereich ist 1,0 bis 5,0.</span><span class="sxs-lookup"><span data-stu-id="83f14-564">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="83f14-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="83f14-566">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-567">Minimale Breitband-Netzwerk-Mos für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="83f14-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="83f14-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="83f14-569">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-570">Durchschnittliche vorhergesagte Breitband-Abhör-Mos-Bewertung für gesendete Audiodaten, einschließlich Sprachniveau, Geräuschpegel und Aufnahmegeräte Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="83f14-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="83f14-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="83f14-572">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-573">Minimale SendListenMOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="83f14-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="83f14-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="83f14-575">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-576">Durchschnittlicher prognostizierter breitbandiger Abhör-Mos-Score für vom Netzwerk empfangene Audiosignale, einschließlich Sprachpegel, Geräuschpegel, Codec, Netzwerkbedingungen und Merkmale des Aufnahmegeräts.</span><span class="sxs-lookup"><span data-stu-id="83f14-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="83f14-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="83f14-578">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="83f14-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="83f14-579">Minimale RecvListenMOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="83f14-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f14-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="83f14-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="83f14-581">bit</span><span class="sxs-lookup"><span data-stu-id="83f14-581">bit</span></span></p></td>
<td><p><span data-ttu-id="83f14-582">Gibt an, ob Audio FEC für den Anruf verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="83f14-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f14-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="83f14-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="83f14-584">bit</span><span class="sxs-lookup"><span data-stu-id="83f14-584">bit</span></span></p></td>
<td><p><span data-ttu-id="83f14-585">Gibt die Richtung der p-Assert-identifizier Informationen an; 1 bedeutet, dass die Datenstrom Richtung vom Anrufer an den aufgerufenen erfolgt; 0 bedeutet, dass die Datenstrom Richtung vom aufgerufenen zum Aufrufer ist.</span><span class="sxs-lookup"><span data-stu-id="83f14-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

