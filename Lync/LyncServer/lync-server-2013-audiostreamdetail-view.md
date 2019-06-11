---
title: 'Lync Server 2013: AudioStreamDetail-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10992007c76321f8ed3b436b9786cbef840173ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="bfcd8-102">AudioStreamDetail-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfcd8-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfcd8-103">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="bfcd8-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="bfcd8-104">In der AudioStreamDetail-Ansicht werden Informationen zu jedem Audiostream in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="bfcd8-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bfcd8-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="bfcd8-106">Column</span></span></th>
<th><span data-ttu-id="bfcd8-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="bfcd8-107">Data Type</span></span></th>
<th><span data-ttu-id="bfcd8-108">Details</span><span class="sxs-lookup"><span data-stu-id="bfcd8-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="bfcd8-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-110">datetime</span><span class="sxs-lookup"><span data-stu-id="bfcd8-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-111">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="bfcd8-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-113">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-113">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-114">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-115">Datenstrom-Nr</span><span class="sxs-lookup"><span data-stu-id="bfcd8-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-116">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-116">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-117">Eindeutige ID innerhalb einer medienzeile</span><span class="sxs-lookup"><span data-stu-id="bfcd8-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="bfcd8-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-119">datetime</span><span class="sxs-lookup"><span data-stu-id="bfcd8-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-120">Startzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="bfcd8-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-122">datetime</span><span class="sxs-lookup"><span data-stu-id="bfcd8-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-123">Endzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="bfcd8-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-125">bit</span><span class="sxs-lookup"><span data-stu-id="bfcd8-125">bit</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-126">Dialog Feld Kategorie: 0 ist der lync Server to Mediation Server Leg; 1 ist der Vermittlungs Server für das PSTN-Gateway-Bein.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="bfcd8-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-128">bit</span><span class="sxs-lookup"><span data-stu-id="bfcd8-128">bit</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-129">Flag, das angibt, ob der Anruf umgangen wurde oder nicht.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="bfcd8-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-131">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-131">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-132">Wenn vorhanden, gibt an, warum ein Anruf nicht umgangen wurde, auch wenn die Bypass-IDs zugeordnet wurden.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-132">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="bfcd8-133">Es wird nur ein Wert definiert:</span><span class="sxs-lookup"><span data-stu-id="bfcd8-133">Only one value is defined:</span></span></p>
<p><span data-ttu-id="bfcd8-134">0x0001 – unbekannte Bypass-ID für den standardmäßigen Netzwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="bfcd8-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-136">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-136">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-137">Die Priorität des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="bfcd8-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-140">FQDN des anrufenden Pools.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="bfcd8-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-142">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-143">FQDN des aufgerufenen Pools.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-144">Anrufer</span><span class="sxs-lookup"><span data-stu-id="bfcd8-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-146">URI des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-147">Callee</span><span class="sxs-lookup"><span data-stu-id="bfcd8-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-149">URI des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="bfcd8-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-152">Benutzer-Agent-Zeichenfolge des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="bfcd8-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-154">smallint</span><span class="sxs-lookup"><span data-stu-id="bfcd8-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-155">Der Typ des Benutzer-Agents des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="bfcd8-156">Weitere Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bfcd8-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="bfcd8-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-159">Kategorie des Benutzer-Agents des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="bfcd8-160">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bfcd8-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="bfcd8-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-162">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-163">Benutzer-Agent-Zeichenfolge des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="bfcd8-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-165">smallint</span><span class="sxs-lookup"><span data-stu-id="bfcd8-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-166">Der Typ des Benutzer-Agents des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-166">Type of callee’s user agent.</span></span> <span data-ttu-id="bfcd8-167">Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bfcd8-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="bfcd8-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-170">Kategorie des Benutzer-Agents des berufenen</span><span class="sxs-lookup"><span data-stu-id="bfcd8-170">Category of callee’s user agent.</span></span> <span data-ttu-id="bfcd8-171">Informationen hierzu finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bfcd8-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="bfcd8-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-174">Der Endpunktname des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="bfcd8-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-177">Endpunktname des angerufenen</span><span class="sxs-lookup"><span data-stu-id="bfcd8-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-178">Anrufer</span><span class="sxs-lookup"><span data-stu-id="bfcd8-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-179">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-180">Betriebssystem (OS) des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="bfcd8-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-182">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-183">Betriebssystem (OS) des Endpunkts des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="bfcd8-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-185">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-186">Der CPU-Name des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="bfcd8-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-188">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-189">Der CPU-Name des Endpunkts des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="bfcd8-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-191">smallint</span><span class="sxs-lookup"><span data-stu-id="bfcd8-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-192">Die Anzahl der CPU-Kerne im Endpunkt des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="bfcd8-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-194">smallint</span><span class="sxs-lookup"><span data-stu-id="bfcd8-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-195">Die Anzahl der CPU-Kerne im Endpunkt des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="bfcd8-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-197">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-197">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-198">CPU-Prozessorgeschwindigkeit des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="bfcd8-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-200">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-200">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-201">CPU-Prozessorgeschwindigkeit des Endpunkts des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="bfcd8-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="bfcd8-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-204">Gibt an, ob das System des Anrufers in einer virtualisierten Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="bfcd8-205">Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpunkt Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bfcd8-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="bfcd8-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="bfcd8-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-208">Gibt an, ob das System des aufgerufenen in einer virtualisierten Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="bfcd8-209">Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpunkt Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bfcd8-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="bfcd8-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bfcd8-211">Korrelationsschlüssel</span><span class="sxs-lookup"><span data-stu-id="bfcd8-211">Correlation key.</span></span> <span data-ttu-id="bfcd8-212">Wird in der <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation-Tabelle in lync Server 2013</a>referenziert.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="bfcd8-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="bfcd8-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-215">Informationen zum Medienpfad, beispielsweise direkt oder weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="bfcd8-216">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bfcd8-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="bfcd8-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-218">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-218">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-219">Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der unter Bits-Flags für den Aufrufer beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-219">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="bfcd8-220">Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-220">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="bfcd8-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-222">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-222">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-223">Informationen zum Prozess der interaktiven Verbindungseinrichtung (ICE), der in den Bits-Flags für den aufgerufenen beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-223">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="bfcd8-224">Ausführliche Informationen finden Sie in der Quality of Experience Monitoring Server Protocol-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-224">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-225">Transport</span><span class="sxs-lookup"><span data-stu-id="bfcd8-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="bfcd8-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-227">Transporttyp: 0 ist UDP, 1 ist TCP.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="bfcd8-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-230">Die IP-Adresse des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-230">IP address of the caller.</span></span> <span data-ttu-id="bfcd8-231">Hierbei kann es sich entweder um eine IPv4-oder eine IPv6-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="bfcd8-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-233">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-233">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-234">Der vom Aufrufer verwendete Port.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="bfcd8-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-236">bit</span><span class="sxs-lookup"><span data-stu-id="bfcd8-236">bit</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-237">Gibt an, ob sich der Aufrufer innerhalb des Intervall Netzwerks befindet: 1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="bfcd8-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-240">Die IP-Adresse des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-240">IP address of the callee.</span></span> <span data-ttu-id="bfcd8-241">Hierbei kann es sich entweder um eine IPv4-oder eine IPv6-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="bfcd8-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-243">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-243">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-244">Port, der vom aufgerufenen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="bfcd8-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-246">bit</span><span class="sxs-lookup"><span data-stu-id="bfcd8-246">bit</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-247">Gibt an, ob sich der aufgerufene innerhalb des Intervall Netzwerks befindet: 1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass der Anrufer sich außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="bfcd8-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-249">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-250">Der Name der Website des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="bfcd8-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-252">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-253">Name des Landes/der Region der Website des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="bfcd8-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-255">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-256">Name der Website des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="bfcd8-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-258">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-259">Name des Landes/der Region der Website des berufenen.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="bfcd8-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-262">Die IP-Adresse des A/V-Edgedienst, der vom Aufrufer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="bfcd8-263">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bfcd8-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="bfcd8-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-265">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-265">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-266">Der Port des A/V-Edgedienst, der vom Aufrufer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="bfcd8-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-269">Der IP-Adressen Schlüssel des A/V-Edgedienst, der vom aufgerufenen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="bfcd8-270">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der Tabelle IPAddress in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bfcd8-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="bfcd8-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-272">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-272">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-273">Port, der für den A/V-Edgedienst verwendet wird, der vom aufgerufenen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="bfcd8-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-276">Name des Aufnahmegeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="bfcd8-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-279">Name des Render-Geräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="bfcd8-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-282">Name des Aufnahmegeräte Treibers des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="bfcd8-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-285">Name des Render-Gerätetreibers des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="bfcd8-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-288">Der Name des Erfassungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="bfcd8-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-291">Name des Render-Geräts.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="bfcd8-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-294">Der Name des Capture-Gerätetreibers des anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="bfcd8-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-297">Der Name des Render-Gerätetreibers des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="bfcd8-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="bfcd8-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-300">Netzwerkverbindungstyp des Anrufers: 0 ist verkabelt, 1 ist drahtlos.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="bfcd8-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-302">bit</span><span class="sxs-lookup"><span data-stu-id="bfcd8-302">bit</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-303">Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist: 1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="bfcd8-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-305">Decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-306">Netzwerkverbindungsgeschwindigkeit für den Endpunkt des Anrufers in BPS.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="bfcd8-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="bfcd8-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-309">Netzwerkverbindungstyp des anrufempfängers: 0 ist verkabelt, 1 ist drahtlos.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="bfcd8-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-311">bit</span><span class="sxs-lookup"><span data-stu-id="bfcd8-311">bit</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-312">Gibt an, ob der Anrufer über ein virtuelles privates Netzwerk verbunden ist: 1 ist ein VPN (virtuelles privates Netzwerk), 0 ist kein VPN.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="bfcd8-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-314">Decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-315">Netzwerkverbindungsgeschwindigkeit für den Endpunkt des aufgerufenen in BPS.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="bfcd8-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-317">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-318">Schmalband-Konversations-Mos der audiositzungen (basierend auf beiden Audiostreams).</span><span class="sxs-lookup"><span data-stu-id="bfcd8-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="bfcd8-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-320">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-320">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-321">Tatsächliche Bandbreite, die auf den angegebenen Send-Seitenstrom angewendet wurde, wenn verschiedene Richtlinieneinstellungen angegeben wurden (Turn, API, SDP, Richtlinien Server usw.).</span><span class="sxs-lookup"><span data-stu-id="bfcd8-321">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="bfcd8-322">Dies sollte nicht mit der effektiven Bandbreite verwechselt werden, da auf der Grundlage der Bandbreitenschätzung eine geringere effektive Bandbreite vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-322">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="bfcd8-323">Dies ist im Grunde die maximale Bandbreite, die der sendedatenstrom sperren kann, wenn die Bandbreite geschätzt wird.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-323">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="bfcd8-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-325">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-325">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-326">Durchschnittlicher Netzwerk-Jitter aus RTCP-Statistiken (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="bfcd8-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="bfcd8-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-328">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-328">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-329">Maximaler Netzwerk Jitter während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="bfcd8-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-331">Dezimal (5; 4)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-332">Durchschnittliche Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="bfcd8-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-334">Dezimal (5; 4)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-335">Maximaler Paketverlust während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="bfcd8-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-337">Dezimal (9; 4)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-338">Durchschnittliche Dichte des Paketverlusts während des Ausbruchs von Verlusten während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="bfcd8-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-340">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-340">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-341">Durchschnittliche Dauer des Paketverlusts während des Ausbruchs von Verlusten während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="bfcd8-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-343">Dezimal (9; 4)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-344">Durchschnittliche Dichte des Paketverlusts bei Lücken zwischen Bursts des Paketverlusts.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="bfcd8-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-346">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-346">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-347">Durchschnittliche Dauer von Lücken zwischen Bursts des Paketverlusts.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="bfcd8-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-349">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-349">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-350">Die Anzahl der Pakete für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-351">Bandbreite</span><span class="sxs-lookup"><span data-stu-id="bfcd8-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-352">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-352">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-353">Bandbreiten Schätzungen für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="bfcd8-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-355">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-356">Netzwerk-Mos-Verschlechterung für den gesamten Anruf.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-356">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="bfcd8-357">Der Bereich ist 0,0 bis 5,0.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-357">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="bfcd8-358">Diese Metrik zeigt die Menge, die das Netzwerk Mos aufgrund von Jitter und Paketverlust reduziert wurde.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-358">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="bfcd8-359">Für akzeptable Qualität sollte es weniger als 0,5.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-359">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="bfcd8-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-361">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-362">Maximaler Netzwerk-Mos-Abbau während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="bfcd8-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-364">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-365">Netzwerk-Mos-Beeinträchtigung durch Jitter.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="bfcd8-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-367">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-368">Netzwerk-Mos-Beeinträchtigung durch Paketverlust.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="bfcd8-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-370">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-370">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-371">Der für den Anruf verwendete Audiocodec, auf den von der <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription-Tabelle in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="bfcd8-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-373">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-373">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-374">Abtastrate für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="bfcd8-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-376">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-376">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-377">Analoger Gain-Regler für Audio-Signalpegel für das Audiosignal, das der Anrufer gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-377">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="bfcd8-378">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-378">The unit for this metric is dBmo.</span></span> <span data-ttu-id="bfcd8-379">Für akzeptable Qualität sollte es mindestens 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-379">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="bfcd8-380">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-380">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="bfcd8-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-382">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-382">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-383">Audio-Signalpegel für das Audiosignal, das der Anrufer empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-383">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="bfcd8-384">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-384">The unit for this metric is dBmo.</span></span> <span data-ttu-id="bfcd8-385">Für akzeptable Qualität sollte es mindestens 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-385">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="bfcd8-386">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-386">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="bfcd8-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-388">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-388">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-389">Nach analoger Gain-Regler Audio-Rauschpegel für das Audiosignal, das der Anrufer gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-389">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="bfcd8-390">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-390">The unit for this metric is dBmo.</span></span> <span data-ttu-id="bfcd8-391">Für akzeptable Qualität sollte es weniger als 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-391">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="bfcd8-392">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-392">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="bfcd8-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-394">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-394">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-395">Nach analoger Gain-Regler Audio-Rauschpegel für das Audiosignal, das der Anrufer empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-395">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="bfcd8-396">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-396">The unit for this metric is dBmo.</span></span> <span data-ttu-id="bfcd8-397">Für akzeptable Qualität sollte es weniger als 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-397">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="bfcd8-398">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-398">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="bfcd8-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-400">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-400">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-401">Verbesserung der Echo-Rückerstattung für den Anrufer.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-401">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="bfcd8-402">Die Einheit für diese Metrik ist DB.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-402">The unit for this metric is dB.</span></span> <span data-ttu-id="bfcd8-403">Niedrigere Werte stellen weniger Echo dar.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-403">Lower values represent less echo.</span></span> <span data-ttu-id="bfcd8-404">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-404">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="bfcd8-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-406">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-406">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-407">Durchschnittliche Störimpulse pro fünf Minuten für die Lautsprecher-Wiedergabe des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-407">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="bfcd8-408">Für eine gute Qualität sollte dies weniger als eins pro fünf Minuten sein.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-408">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="bfcd8-409">Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-409">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="bfcd8-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-411">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-411">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-412">Durchschnittliche Störimpulse pro fünf Minuten für die Mikrofonaufnahme des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-412">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="bfcd8-413">Für eine gute Qualität sollte dies weniger als eine pro fünf Minuten sein.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-413">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="bfcd8-414">Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-414">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="bfcd8-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-416">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-417">Clock-Drift Rate des Anrufers im Verhältnis zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="bfcd8-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-419">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-420">Clock-Drift Rate des Anrufers für das Lautsprecher Gerät relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="bfcd8-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-422">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-423">Durchschnittlicher Zeitstempel des Mikrofon-Datenstroms in Millisekunden in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="bfcd8-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-425">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-426">Der Durchschnitt des Sprechers des Sprechers Render-Datenstrom Zeitstempel-Fehler in Millisekunden in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="bfcd8-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-428">smallint</span><span class="sxs-lookup"><span data-stu-id="bfcd8-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-429">Voice-Switch ist ein Halbduplex-Modus mit verminderter Unterbrechungs Fähigkeit.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="bfcd8-430">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bfcd8-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="bfcd8-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="bfcd8-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-433">Ursachen für ein Echo Ereignis für den Aufrufer.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="bfcd8-434">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bfcd8-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="bfcd8-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-436">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-437">Prozentsatz der Zeit, zu der ECHO im Mikrofonaufnahme Datenstrom des Anrufers erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-437">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="bfcd8-438">Wenn Headset verwendet wird, sollte der Wert gering sein.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-438">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="bfcd8-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-440">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-441">Prozentsatz der Zeit, zu der ECHO im gesendeten Datenstrom des Anrufers erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-441">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="bfcd8-442">Ein großer Prozentsatz des Echos in Send-Streams zeigt einen Hinweis auf Echo Verluste.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-442">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="bfcd8-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-444">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-444">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-445">Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway für das Audiosignal des Anrufers; Dies gilt nur für den Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-445">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="bfcd8-446">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-446">The unit of this metric is dBoV.</span></span> <span data-ttu-id="bfcd8-447">Für eine gute Qualität sollte der zulässige Bereich-30 bis-18 dBoV sein.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-447">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="bfcd8-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-449">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-449">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-450">Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway für das Audiosignal des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-450">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="bfcd8-451">Dies gilt nur für den Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-451">This applies only to the Mediation Server.</span></span> <span data-ttu-id="bfcd8-452">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-452">The unit of this metric is dBoV.</span></span> <span data-ttu-id="bfcd8-453">Für eine gute Qualität sollte der zulässige Bereich kleiner als-50 dBoV sein.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-453">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="bfcd8-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-455">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-455">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-456">Automatische Gain-Steuerung (AGC) auf der Mediation Server-Seite, die auf das Audiosignal des Anrufers angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="bfcd8-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-458">float</span><span class="sxs-lookup"><span data-stu-id="bfcd8-458">float</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-459">Root Mean Square (RMS) des eingehenden Signals an den Anrufer für bis zu den ersten 30 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="bfcd8-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-461">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-461">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-462">Stellt die analogen Gain-Regler-Audiosignale für das Audiosignal dar, das der Anrufer gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-462">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="bfcd8-463">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-463">The unit for this metric is dBmo.</span></span> <span data-ttu-id="bfcd8-464">Für akzeptable Qualität sollte es mindestens 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-464">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="bfcd8-465">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-465">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="bfcd8-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-467">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-467">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-468">Audiosignal Pegel für das Audiosignal, das der Anrufer empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-468">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="bfcd8-469">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-469">The unit for this metric is dBmo.</span></span> <span data-ttu-id="bfcd8-470">Für akzeptable Qualität sollte es mindestens 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-470">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="bfcd8-471">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-471">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="bfcd8-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-473">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-473">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-474">Post-Analog-Gain-Regler Audio-Rauschpegel für das Audiosignal, das der Anrufer gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-474">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="bfcd8-475">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-475">The unit for this metric is dBmo.</span></span> <span data-ttu-id="bfcd8-476">Für akzeptable Qualität sollte es weniger als 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-476">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="bfcd8-477">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-477">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="bfcd8-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-479">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-479">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-480">Analoger Gain-Regler Audio-Rauschpegel für das Audiosignal, das der Anrufer empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-480">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="bfcd8-481">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-481">The unit for this metric is dBmo.</span></span> <span data-ttu-id="bfcd8-482">Für akzeptable Qualität sollte es weniger als 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-482">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="bfcd8-483">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-483">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="bfcd8-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-485">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-485">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-486">Verbesserung der Echo-Rückerstattung für den aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-486">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="bfcd8-487">Die Einheit für diese Metrik ist DB.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-487">The unit for this metric is dB.</span></span> <span data-ttu-id="bfcd8-488">Niedrigere Werte stellen weniger Echo dar.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-488">Lower values represent less echo.</span></span> <span data-ttu-id="bfcd8-489">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-489">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="bfcd8-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-491">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-491">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-492">Durchschnittliche Störgeräusche pro fünf Minuten für die Lautsprecher-Darstellung des anrufenden.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-492">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="bfcd8-493">Für eine gute Qualität sollte dies weniger als eins pro fünf Minuten sein.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-493">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="bfcd8-494">Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-494">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="bfcd8-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-496">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-496">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-497">Durchschnittliche Störimpulse pro fünf Minuten für die Mikrofonaufnahme des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-497">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="bfcd8-498">Für eine gute Qualität sollte dies weniger als eine pro fünf Minuten sein.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-498">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="bfcd8-499">Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-499">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="bfcd8-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-501">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-502">Abdriftrate des Mikrofon Geräts des Anrufers, relativ zu CPU-Takt.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="bfcd8-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-504">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-505">Clock-Drift Rate des Anrufers für das Lautsprecher Gerät relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="bfcd8-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-507">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-508">Durchschnittlicher Zeitstempel des Mikrofon-Datenstroms in Millisekunden in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="bfcd8-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-510">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-511">Der Durchschnitt des Sprechers des Speaker-Render-Datenstrom Zeitstempels in Millisekunden in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="bfcd8-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-513">smallint</span><span class="sxs-lookup"><span data-stu-id="bfcd8-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-514">Voice-Switch ist ein Halbduplex-Modus mit verminderter Unterbrechungs Fähigkeit.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="bfcd8-515">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bfcd8-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="bfcd8-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="bfcd8-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-518">Ursachen für ein Echo Ereignis für den aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="bfcd8-519">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bfcd8-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="bfcd8-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-521">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-522">Prozentsatz der Zeit, zu der ECHO im Mikrofonaufnahme Datenstrom des berufenen erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-522">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="bfcd8-523">Wenn Headset verwendet wird, sollte der Wert gering sein.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-523">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="bfcd8-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-525">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-526">Der Prozentsatz der Zeit, zu der ECHO im gesendeten Datenstrom des aufgerufenen erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-526">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="bfcd8-527">Ein großer Prozentsatz des Echos in Send-Streams zeigt einen Hinweis auf Echo Verluste.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-527">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="bfcd8-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-529">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-529">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-530">Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway für das Audio des berufenen; Dies gilt nur für den Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-530">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="bfcd8-531">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-531">The unit of this metric is dBoV.</span></span> <span data-ttu-id="bfcd8-532">Für eine gute Qualität sollte der zulässige Bereich [-30 bis-18] dBoV sein.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-532">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="bfcd8-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-534">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-534">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-535">Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway für das Audio des berufenen.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-535">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="bfcd8-536">Dies gilt nur für den Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-536">This applies only to the Mediation Server.</span></span> <span data-ttu-id="bfcd8-537">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-537">The unit of this metric is dBoV.</span></span> <span data-ttu-id="bfcd8-538">Für eine gute Qualität sollte der zulässige Bereich kleiner als-50 dBoV sein.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-538">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="bfcd8-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-540">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-540">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-541">Automatische Gain-Steuerung (AGC) auf der Mediation Server-Seite, die auf die Audiofunktion des berufenen angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="bfcd8-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-543">float</span><span class="sxs-lookup"><span data-stu-id="bfcd8-543">float</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-544">Root Mean Square (RMS) des eingehenden Signals an den Anrufer für bis zu den ersten 30 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="bfcd8-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-546">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-547">Durchschnittliches Verhältnis der verborgenen Samples, die von der audioheilung an typische Samples generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="bfcd8-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-549">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-550">Durchschnittliches Verhältnis von gedehnten Samples, die von der audioheilung zu typischen Samples generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="bfcd8-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-552">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-553">Durchschnittliches Verhältnis von komprimierten Samples, die von der audioheilung zu typischen Samples generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-554">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="bfcd8-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-555">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-555">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-556">Roundtrip-Zeit von RTCP-Statistiken</span><span class="sxs-lookup"><span data-stu-id="bfcd8-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="bfcd8-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-558">int</span><span class="sxs-lookup"><span data-stu-id="bfcd8-558">int</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-559">Maximale Roundtrip-Zeit für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="bfcd8-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-561">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-562">Durchschnittliche Breitband-Netzwerk-Mos für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-562">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="bfcd8-563">Diese Metrik hängt vom verwendeten Paketverlust, Jitter und Codec ab.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-563">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="bfcd8-564">Der Bereich ist 1,0 bis 5,0.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-564">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="bfcd8-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-566">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-567">Minimale Breitband-Netzwerk-Mos für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="bfcd8-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-569">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-570">Durchschnittliche vorhergesagte Breitband-Abhör-Mos-Bewertung für gesendete Audiodaten, einschließlich Sprachniveau, Geräuschpegel und Aufnahmegeräte Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="bfcd8-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-572">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-573">Minimale SendListenMOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="bfcd8-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-575">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-576">Durchschnittlicher prognostizierter breitbandiger Abhör-Mos-Score für vom Netzwerk empfangene Audiosignale, einschließlich Sprachpegel, Geräuschpegel, Codec, Netzwerkbedingungen und Merkmale des Aufnahmegeräts.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="bfcd8-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-578">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="bfcd8-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-579">Minimale RecvListenMOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfcd8-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="bfcd8-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-581">bit</span><span class="sxs-lookup"><span data-stu-id="bfcd8-581">bit</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-582">Gibt an, ob Audio FEC für den Anruf verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfcd8-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="bfcd8-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-584">bit</span><span class="sxs-lookup"><span data-stu-id="bfcd8-584">bit</span></span></p></td>
<td><p><span data-ttu-id="bfcd8-585">Gibt die Richtung der p-Assert-identifizier Informationen an; 1 bedeutet, dass die Datenstrom Richtung vom Anrufer an den aufgerufenen erfolgt; 0 bedeutet, dass die Datenstrom Richtung vom aufgerufenen zum Aufrufer ist.</span><span class="sxs-lookup"><span data-stu-id="bfcd8-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

