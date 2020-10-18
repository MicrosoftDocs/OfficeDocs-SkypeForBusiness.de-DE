---
title: 'Lync Server 2013: AudioStreamDetail-Ansicht'
description: 'Lync Server 2013: AudioStreamDetail-Ansicht.'
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
ms.openlocfilehash: 92c4c9bbb4f126e242e28d835222f6ba2af89d8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573051"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="982eb-103">AudioStreamDetail-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="982eb-103">AudioStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="982eb-104">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="982eb-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="982eb-105">Die AudioStreamDetail-Ansicht speichert Informationen über jeden Audiostream in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="982eb-105">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="982eb-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="982eb-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="982eb-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="982eb-107">Column</span></span></th>
<th><span data-ttu-id="982eb-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="982eb-108">Data Type</span></span></th>
<th><span data-ttu-id="982eb-109">Details</span><span class="sxs-lookup"><span data-stu-id="982eb-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="982eb-110">SessionTime</span><span class="sxs-lookup"><span data-stu-id="982eb-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="982eb-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="982eb-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="982eb-112"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="982eb-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="982eb-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="982eb-114">int</span><span class="sxs-lookup"><span data-stu-id="982eb-114">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-115"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="982eb-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-116">Datenstrom-Nr</span><span class="sxs-lookup"><span data-stu-id="982eb-116">StreamId</span></span></p></td>
<td><p><span data-ttu-id="982eb-117">int</span><span class="sxs-lookup"><span data-stu-id="982eb-117">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-118">Eindeutige ID innerhalb einer Medienzeile.</span><span class="sxs-lookup"><span data-stu-id="982eb-118">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-119">StartTime</span><span class="sxs-lookup"><span data-stu-id="982eb-119">StartTime</span></span></p></td>
<td><p><span data-ttu-id="982eb-120">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="982eb-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="982eb-121">Startzeitpunkt der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="982eb-121">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-122">EndTime</span><span class="sxs-lookup"><span data-stu-id="982eb-122">EndTime</span></span></p></td>
<td><p><span data-ttu-id="982eb-123">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="982eb-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="982eb-124">Endzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="982eb-124">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-125">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="982eb-125">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="982eb-126">Bit</span><span class="sxs-lookup"><span data-stu-id="982eb-126">bit</span></span></p></td>
<td><p><span data-ttu-id="982eb-127">Dialog Feld Kategorie: 0 ist die lync Server Vermittlungsserver Bein; 1 ist die Vermittlungsserver zu PSTN-Gateway-Bein.</span><span class="sxs-lookup"><span data-stu-id="982eb-127">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-128">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="982eb-128">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="982eb-129">Bit</span><span class="sxs-lookup"><span data-stu-id="982eb-129">bit</span></span></p></td>
<td><p><span data-ttu-id="982eb-130">Flag, das angibt, ob der Anruf umgangen wurde oder nicht.</span><span class="sxs-lookup"><span data-stu-id="982eb-130">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-131">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="982eb-131">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="982eb-132">int</span><span class="sxs-lookup"><span data-stu-id="982eb-132">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p102">Gibt an (falls vorhanden), warum ein Anruf nicht umgangen wurde, auch wenn die Umgehungs-IDs übereinstimmten. Es ist nur ein Wert definiert:</span><span class="sxs-lookup"><span data-stu-id="982eb-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="982eb-135">0x0001 – Unbekannte Umgehungs-ID für Standardnetzwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="982eb-135">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-136">CallPriority</span><span class="sxs-lookup"><span data-stu-id="982eb-136">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="982eb-137">int</span><span class="sxs-lookup"><span data-stu-id="982eb-137">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-138">Priorität des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="982eb-138">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-139">CallerPool</span><span class="sxs-lookup"><span data-stu-id="982eb-139">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="982eb-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="982eb-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="982eb-141">FQDN des Anruferpools.</span><span class="sxs-lookup"><span data-stu-id="982eb-141">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-142">CalleePool</span><span class="sxs-lookup"><span data-stu-id="982eb-142">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="982eb-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="982eb-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="982eb-144">FQDN des Angerufenenpools.</span><span class="sxs-lookup"><span data-stu-id="982eb-144">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-145">Anrufer</span><span class="sxs-lookup"><span data-stu-id="982eb-145">Caller</span></span></p></td>
<td><p><span data-ttu-id="982eb-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="982eb-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="982eb-147">URI des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="982eb-147">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-148">Aufgerufene</span><span class="sxs-lookup"><span data-stu-id="982eb-148">Callee</span></span></p></td>
<td><p><span data-ttu-id="982eb-149">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="982eb-149">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="982eb-150">URI des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-150">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-151">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="982eb-151">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="982eb-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="982eb-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="982eb-153">Zeichenfolge für den Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="982eb-153">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-154">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="982eb-154">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="982eb-155">smallint</span><span class="sxs-lookup"><span data-stu-id="982eb-155">smallint</span></span></p></td>
<td><p><span data-ttu-id="982eb-156">Benutzeragentenart des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="982eb-156">Type of the caller’s user agent.</span></span> <span data-ttu-id="982eb-157">Ausführliche Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="982eb-157">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-158">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="982eb-158">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="982eb-159">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="982eb-159">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="982eb-160">Benutzeragentenkategorie des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="982eb-160">Category of the caller’s user agent.</span></span> <span data-ttu-id="982eb-161">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="982eb-161">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-162">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="982eb-162">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="982eb-163">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="982eb-163">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="982eb-164">Zeichenfolge für den Benutzer-Agent des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-164">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-165">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="982eb-165">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="982eb-166">smallint</span><span class="sxs-lookup"><span data-stu-id="982eb-166">smallint</span></span></p></td>
<td><p><span data-ttu-id="982eb-167">Typ des Benutzer-Agent des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-167">Type of callee’s user agent.</span></span> <span data-ttu-id="982eb-168">Weitere Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="982eb-168">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-169">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="982eb-169">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="982eb-170">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="982eb-170">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="982eb-171">Kategorie des Benutzer-Agent des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-171">Category of callee’s user agent.</span></span> <span data-ttu-id="982eb-172">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="982eb-172">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-173">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="982eb-173">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="982eb-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="982eb-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="982eb-175">Name des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="982eb-175">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-176">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="982eb-176">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="982eb-177">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="982eb-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="982eb-178">Name des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-178">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-179">Anrufer</span><span class="sxs-lookup"><span data-stu-id="982eb-179">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="982eb-180">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="982eb-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="982eb-181">Betriebssystem des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="982eb-181">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-182">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="982eb-182">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="982eb-183">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="982eb-183">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="982eb-184">Betriebssystem des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-184">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-185">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="982eb-185">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="982eb-186">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="982eb-186">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="982eb-187">Name der CPU des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="982eb-187">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-188">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="982eb-188">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="982eb-189">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="982eb-189">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="982eb-190">Name der CPU des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-190">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-191">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="982eb-191">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="982eb-192">smallint</span><span class="sxs-lookup"><span data-stu-id="982eb-192">smallint</span></span></p></td>
<td><p><span data-ttu-id="982eb-193">Anzahl der Prozessorkerne des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="982eb-193">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-194">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="982eb-194">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="982eb-195">smallint</span><span class="sxs-lookup"><span data-stu-id="982eb-195">smallint</span></span></p></td>
<td><p><span data-ttu-id="982eb-196">Anzahl der Prozessorkerne des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-196">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-197">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="982eb-197">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="982eb-198">int</span><span class="sxs-lookup"><span data-stu-id="982eb-198">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-199">Prozessorgeschwindigkeit der CPU des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="982eb-199">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-200">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="982eb-200">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="982eb-201">int</span><span class="sxs-lookup"><span data-stu-id="982eb-201">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-202">Prozessorgeschwindigkeit der CPU des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-202">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-203">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="982eb-203">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="982eb-204">tinyint</span><span class="sxs-lookup"><span data-stu-id="982eb-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="982eb-205">Gibt an, ob das System des Anrufers in einer virtualisierten Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="982eb-205">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="982eb-206">Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpoint-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="982eb-206">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-207">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="982eb-207">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="982eb-208">tinyint</span><span class="sxs-lookup"><span data-stu-id="982eb-208">tinyint</span></span></p></td>
<td><p><span data-ttu-id="982eb-209">Gibt an, ob das System des Angerufenen in einer virtualisierten Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="982eb-209">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="982eb-210">Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpoint-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="982eb-210">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-211">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="982eb-211">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="982eb-212">Korrelationsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="982eb-212">Correlation key.</span></span> <span data-ttu-id="982eb-213">Referenziert aus der <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="982eb-213">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-214">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="982eb-214">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="982eb-215">tinyint</span><span class="sxs-lookup"><span data-stu-id="982eb-215">tinyint</span></span></p></td>
<td><p><span data-ttu-id="982eb-216">Informationen zum Medienpfad, z. B. direkt oder Relay.</span><span class="sxs-lookup"><span data-stu-id="982eb-216">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="982eb-217">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="982eb-217">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-218">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="982eb-218">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="982eb-219">int</span><span class="sxs-lookup"><span data-stu-id="982eb-219">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p111">Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Anrufer, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".</span><span class="sxs-lookup"><span data-stu-id="982eb-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-222">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="982eb-222">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="982eb-223">int</span><span class="sxs-lookup"><span data-stu-id="982eb-223">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p112">Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Angerufenen, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".</span><span class="sxs-lookup"><span data-stu-id="982eb-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-226">Transport</span><span class="sxs-lookup"><span data-stu-id="982eb-226">Transport</span></span></p></td>
<td><p><span data-ttu-id="982eb-227">tinyint</span><span class="sxs-lookup"><span data-stu-id="982eb-227">tinyint</span></span></p></td>
<td><p><span data-ttu-id="982eb-228">Transporttyp: 0 ist UDP, 1 ist TCP.</span><span class="sxs-lookup"><span data-stu-id="982eb-228">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-229">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="982eb-229">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="982eb-230">var (50)</span><span class="sxs-lookup"><span data-stu-id="982eb-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="982eb-231">IP-Adresse des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="982eb-231">IP address of the caller.</span></span> <span data-ttu-id="982eb-232">Dies kann eine IPv4- oder eine IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="982eb-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-233">CallerPort</span><span class="sxs-lookup"><span data-stu-id="982eb-233">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="982eb-234">int</span><span class="sxs-lookup"><span data-stu-id="982eb-234">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-235">Vom Anrufer verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="982eb-235">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-236">CallerInside</span><span class="sxs-lookup"><span data-stu-id="982eb-236">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="982eb-237">Bit</span><span class="sxs-lookup"><span data-stu-id="982eb-237">bit</span></span></p></td>
<td><p><span data-ttu-id="982eb-238">Gibt an, ob sich der Anrufer innerhalb des Intervallnetzwerks befindet: 1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="982eb-238">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-239">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="982eb-239">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="982eb-240">var (50)</span><span class="sxs-lookup"><span data-stu-id="982eb-240">var(50)</span></span></p></td>
<td><p><span data-ttu-id="982eb-241">IP-Adresse des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-241">IP address of the callee.</span></span> <span data-ttu-id="982eb-242">Dies kann eine IPv4- oder eine IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="982eb-242">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-243">CalleePort</span><span class="sxs-lookup"><span data-stu-id="982eb-243">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="982eb-244">int</span><span class="sxs-lookup"><span data-stu-id="982eb-244">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-245">Vom Angerufenen verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="982eb-245">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-246">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="982eb-246">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="982eb-247">Bit</span><span class="sxs-lookup"><span data-stu-id="982eb-247">bit</span></span></p></td>
<td><p><span data-ttu-id="982eb-248">Gibt an, ob sich der Angerufene innerhalb des Intervallnetzwerks befindet: 1 bedeutet, dass der Angerufene sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Angerufene außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="982eb-248">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-249">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="982eb-249">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="982eb-250">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="982eb-250">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="982eb-251">Name der Website des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="982eb-251">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-252">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="982eb-252">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="982eb-253">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="982eb-253">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="982eb-254">Name des Landes/der Region der Website des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="982eb-254">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-255">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="982eb-255">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="982eb-256">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="982eb-256">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="982eb-257">Name der Website des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-257">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-258">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="982eb-258">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="982eb-259">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="982eb-259">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="982eb-260">Name des Landes/der Region der Website des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-260">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-261">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="982eb-261">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="982eb-262">var (50)</span><span class="sxs-lookup"><span data-stu-id="982eb-262">var(50)</span></span></p></td>
<td><p><span data-ttu-id="982eb-263">IP-Adresse des vom Anrufer verwendeten A/V-Edgedienstes.</span><span class="sxs-lookup"><span data-stu-id="982eb-263">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="982eb-264">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="982eb-264">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-265">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="982eb-265">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="982eb-266">int</span><span class="sxs-lookup"><span data-stu-id="982eb-266">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-267">Der durch den A/V-Edgedienst des Anrufers verwendete Port.</span><span class="sxs-lookup"><span data-stu-id="982eb-267">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-268">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="982eb-268">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="982eb-269">var (50)</span><span class="sxs-lookup"><span data-stu-id="982eb-269">var(50)</span></span></p></td>
<td><p><span data-ttu-id="982eb-270">IP-Adressschlüssel des vom Anrufer verwendeten A/V-Edgedienstes.</span><span class="sxs-lookup"><span data-stu-id="982eb-270">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="982eb-271">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="982eb-271">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-272">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="982eb-272">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="982eb-273">int</span><span class="sxs-lookup"><span data-stu-id="982eb-273">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-274">Der durch den A/V-Edgedienst des Angerufenen verwendete Port.</span><span class="sxs-lookup"><span data-stu-id="982eb-274">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-275">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="982eb-275">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="982eb-276">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="982eb-276">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="982eb-277">Name des Aufnahmegeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="982eb-277">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-278">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="982eb-278">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="982eb-279">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="982eb-279">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="982eb-280">Name des Darstellungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="982eb-280">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-281">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="982eb-281">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="982eb-282">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="982eb-282">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="982eb-283">Name des Treibers für das Aufnahmegerät des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="982eb-283">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-284">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="982eb-284">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="982eb-285">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="982eb-285">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="982eb-286">Name des Gerätetreibers des Darstellungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="982eb-286">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-287">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="982eb-287">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="982eb-288">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="982eb-288">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="982eb-289">Name des Aufnahmegeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-289">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-290">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="982eb-290">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="982eb-291">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="982eb-291">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="982eb-292">Name des Darstellungsgeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-292">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-293">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="982eb-293">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="982eb-294">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="982eb-294">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="982eb-295">Name des Gerätetreibers des Aufnahmegeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-295">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-296">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="982eb-296">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="982eb-297">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="982eb-297">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="982eb-298">Name des Gerätetreibers des Darstellungsgeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-298">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-299">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="982eb-299">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="982eb-300">tinyint</span><span class="sxs-lookup"><span data-stu-id="982eb-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="982eb-301">Typ der Netzwerkverbindung des Anrufers: 0 ist verkabelt, 1 ist kabellos.</span><span class="sxs-lookup"><span data-stu-id="982eb-301">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-302">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="982eb-302">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="982eb-303">Bit</span><span class="sxs-lookup"><span data-stu-id="982eb-303">bit</span></span></p></td>
<td><p><span data-ttu-id="982eb-304">Gibt an, ob der Anrufer eine Verbindung über ein virtuelles privates Netzwerk hergestellt hat: 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.</span><span class="sxs-lookup"><span data-stu-id="982eb-304">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-305">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="982eb-305">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="982eb-306">Decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="982eb-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="982eb-307">Netzwerkübertragungsrate für den Endpunkt des Anrufers in Bit/s.</span><span class="sxs-lookup"><span data-stu-id="982eb-307">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-308">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="982eb-308">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="982eb-309">tinyint</span><span class="sxs-lookup"><span data-stu-id="982eb-309">tinyint</span></span></p></td>
<td><p><span data-ttu-id="982eb-310">Typ der Netzwerkverbindung des Angerufenen: 0 ist verkabelt, 1 ist kabellos.</span><span class="sxs-lookup"><span data-stu-id="982eb-310">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-311">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="982eb-311">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="982eb-312">Bit</span><span class="sxs-lookup"><span data-stu-id="982eb-312">bit</span></span></p></td>
<td><p><span data-ttu-id="982eb-313">Gibt an, ob der Anrufer eine Verbindung über ein virtuelles privates Netzwerk hergestellt hat: 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.</span><span class="sxs-lookup"><span data-stu-id="982eb-313">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-314">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="982eb-314">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="982eb-315">Decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="982eb-315">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="982eb-316">Netzwerkübertragungsrate für den Endpunkt des Angerufenen in Bit/s.</span><span class="sxs-lookup"><span data-stu-id="982eb-316">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-317">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="982eb-317">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="982eb-318">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-318">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-319">Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).</span><span class="sxs-lookup"><span data-stu-id="982eb-319">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-320">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="982eb-320">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="982eb-321">int</span><span class="sxs-lookup"><span data-stu-id="982eb-321">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p117">Genutzte Bandbreite, die unter verschiedenen Richtlinieneinstellungen (TURN, API, SDP, Richtlinienserver usw.) auf den jeweiligen Stream auf der Seite des Absenders angewendet wird. Dies ist nicht zu verwechseln mit der tatsächlichen Bandbreite, da diese u. U. basierend auf der Bandbreitenschätzung niedriger ist. Dabei handelt es sich um die maximale Bandbreite, die für den Absenderstream möglich ist, abgesehen von den Beschränkungen durch die Bandbreitenschätzung.</span><span class="sxs-lookup"><span data-stu-id="982eb-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-325">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="982eb-325">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="982eb-326">int</span><span class="sxs-lookup"><span data-stu-id="982eb-326">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-327">Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="982eb-327">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-328">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="982eb-328">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="982eb-329">int</span><span class="sxs-lookup"><span data-stu-id="982eb-329">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-330">Maximaler Netzwerkjitter während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="982eb-330">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-331">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="982eb-331">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="982eb-332">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="982eb-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="982eb-333">Durchschnittliche Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="982eb-333">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-334">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="982eb-334">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="982eb-335">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="982eb-335">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="982eb-336">Maximale Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="982eb-336">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-337">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="982eb-337">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="982eb-338">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="982eb-338">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="982eb-339">Durchschnittliche Dichte an Paketverlusten bei Bursts von Verlusten während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="982eb-339">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-340">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="982eb-340">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="982eb-341">int</span><span class="sxs-lookup"><span data-stu-id="982eb-341">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-342">Durchschnittliche Dauer an Paketverlusten bei Bursts von Verlusten während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="982eb-342">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-343">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="982eb-343">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="982eb-344">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="982eb-344">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="982eb-345">Durchschnittliche Dichte an Paketverlusten bei Lücken zwischen Bursts von Paketverlusten.</span><span class="sxs-lookup"><span data-stu-id="982eb-345">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-346">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="982eb-346">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="982eb-347">int</span><span class="sxs-lookup"><span data-stu-id="982eb-347">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-348">Durchschnittliche Dauer der Lücken zwischen Bursts von Paketverlusten.</span><span class="sxs-lookup"><span data-stu-id="982eb-348">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-349">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="982eb-349">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="982eb-350">int</span><span class="sxs-lookup"><span data-stu-id="982eb-350">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-351">Paketwert für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="982eb-351">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-352">Bandbreite</span><span class="sxs-lookup"><span data-stu-id="982eb-352">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="982eb-353">int</span><span class="sxs-lookup"><span data-stu-id="982eb-353">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-354">Bandbreitenschätzwerte für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="982eb-354">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-355">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="982eb-355">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="982eb-356">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-356">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-p118">Netzwerk-MOS-Beeinträchtigung für den gesamten Anruf. Der Bereich umfasst 0,0 bis 5,0.  Diese Metrik gibt an, um welche Menge der Netzwerk-MOS aufgrund von Jitter und Paketverlusten reduziert wurde. Der Wert sollte weniger als 0,5 betragen, um eine akzeptable Qualität zu bieten.</span><span class="sxs-lookup"><span data-stu-id="982eb-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-361">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="982eb-361">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="982eb-362">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-362">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-363">Maximale Netzwerk-MOS-Beeinträchtigung während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="982eb-363">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-364">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="982eb-364">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="982eb-365">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-365">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-366">Netzwerk-MOS-Beeinträchtigung aufgrund von Jitter.</span><span class="sxs-lookup"><span data-stu-id="982eb-366">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-367">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="982eb-367">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="982eb-368">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-368">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-369">Netzwerk-MOS-Beeinträchtigung aufgrund von Paketverlust.</span><span class="sxs-lookup"><span data-stu-id="982eb-369">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-370">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="982eb-370">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="982eb-371">int</span><span class="sxs-lookup"><span data-stu-id="982eb-371">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-372">Der für den Aufruf verwendete Audiocodec, der <a href="lync-server-2013-payloaddescription-table.md">in lync Server 2013</a>von der PayloadDescription-Tabelle referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="982eb-372">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-373">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="982eb-373">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="982eb-374">int</span><span class="sxs-lookup"><span data-stu-id="982eb-374">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-375">Samplingrate für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="982eb-375">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-376">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="982eb-376">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="982eb-377">int</span><span class="sxs-lookup"><span data-stu-id="982eb-377">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p119">Stärke des Audiosignals der postanalogen Verstärkung für das vom Anrufer gesendete Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="982eb-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-382">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="982eb-382">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="982eb-383">int</span><span class="sxs-lookup"><span data-stu-id="982eb-383">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p120">Stärke des Audiosignals für das vom Anrufer empfangene Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="982eb-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-388">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="982eb-388">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="982eb-389">int</span><span class="sxs-lookup"><span data-stu-id="982eb-389">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p121">Stärke des Audiogeräusches der postanalogen Verstärkung für das vom Anrufer gesendete Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="982eb-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-394">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="982eb-394">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="982eb-395">int</span><span class="sxs-lookup"><span data-stu-id="982eb-395">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p122">Stärke des Audiogeräuschs der postanalogen Verstärkung für das vom Anrufer empfangene Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="982eb-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-400">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="982eb-400">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="982eb-401">int</span><span class="sxs-lookup"><span data-stu-id="982eb-401">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p123">Echodämpfungsverbesserung für den Anrufer. Die Einheit für diese Metrik ist dB. Niedrigere Werte bedeuten weniger Echo. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="982eb-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-406">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="982eb-406">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="982eb-407">int</span><span class="sxs-lookup"><span data-stu-id="982eb-407">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p124">Durchschnittliche Verzögerungen pro fünf Minuten für die Lautsprecherwiedergabe des Anrufers. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="982eb-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-411">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="982eb-411">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="982eb-412">int</span><span class="sxs-lookup"><span data-stu-id="982eb-412">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p125">Durchschnittliche Verzögerungen pro fünf Minuten für die Mikrofonerfassung des Anrufers. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="982eb-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-416">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="982eb-416">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="982eb-417">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-417">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-418">Driftrate der Uhr des Mikrofons des Anrufers, relativ zum CPU-Takt.</span><span class="sxs-lookup"><span data-stu-id="982eb-418">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-419">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="982eb-419">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="982eb-420">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-420">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-421">Driftrate der Uhr des Lautsprechers des Anrufers, relativ zum CPU-Takt.</span><span class="sxs-lookup"><span data-stu-id="982eb-421">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-422">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="982eb-422">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="982eb-423">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-423">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-424">Durchschnittlicher Zeitstempelfehler des Mikrofonaufnahme-Datenstroms in Millisekunden, in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="982eb-424">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-425">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="982eb-425">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="982eb-426">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-426">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-427">Durchschnittlicher Zeitstempelfehler des Lautsprecherwiedergabe-Datenstroms des Anrufers in Millisekunden, in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="982eb-427">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-428">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="982eb-428">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="982eb-429">smallint</span><span class="sxs-lookup"><span data-stu-id="982eb-429">smallint</span></span></p></td>
<td><p><span data-ttu-id="982eb-430">Bei der Sprachumschaltung handelt es sich um einen Halbduplexmodus mit der Fähigkeit, Unterbrechungen zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="982eb-430">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="982eb-431">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="982eb-431">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-432">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="982eb-432">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="982eb-433">tinyint</span><span class="sxs-lookup"><span data-stu-id="982eb-433">tinyint</span></span></p></td>
<td><p><span data-ttu-id="982eb-434">Ursachen von Echoereignissen für den Anrufer.</span><span class="sxs-lookup"><span data-stu-id="982eb-434">Causes of an echo event for the caller.</span></span> <span data-ttu-id="982eb-435">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="982eb-435">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-436">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="982eb-436">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="982eb-437">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-437">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-p128">Prozentsatz der Zeit, in der im Mikrofonaufnahme-Datenstrom des Anrufers Echo festgestellt wird. Bei der Verwendung eines Headsets ist der Wert in der Regel niedrig.</span><span class="sxs-lookup"><span data-stu-id="982eb-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-440">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="982eb-440">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="982eb-441">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-441">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-p129">Prozentsatz der Zeit, in der im gesendeten Datenstrom des Anrufers Echo festgestellt wird. Ein hoher Echoprozentsatz in gesendeten Datenströmen deutet auf eine Beeinträchtigung durch Echo hin.</span><span class="sxs-lookup"><span data-stu-id="982eb-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-444">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="982eb-444">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="982eb-445">int</span><span class="sxs-lookup"><span data-stu-id="982eb-445">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p130">Stärke des auf dem Vermittlungsserver empfangenen Signals vom Gateway für das Audio des Anrufers; betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich zwischen [-30 und -18] dBoV liegen.</span><span class="sxs-lookup"><span data-stu-id="982eb-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-449">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="982eb-449">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="982eb-450">int</span><span class="sxs-lookup"><span data-stu-id="982eb-450">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p131">Stärke des auf dem Vermittlungsserver empfangenen Signals vom Gateway für das Audio des Anrufers. Dies betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich unter -50 dBoV liegen.</span><span class="sxs-lookup"><span data-stu-id="982eb-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-455">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="982eb-455">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="982eb-456">int</span><span class="sxs-lookup"><span data-stu-id="982eb-456">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-457">Eingebauter Verstärker (AGC) auf der Vermittlungsserverseite angewendet auf das Audio des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="982eb-457">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-458">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="982eb-458">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="982eb-459">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="982eb-459">float</span></span></p></td>
<td><p><span data-ttu-id="982eb-460">RMS (Effektivwert) des eingehenden Signals an den Anrufer in den ersten 30 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="982eb-460">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-461">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="982eb-461">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="982eb-462">int</span><span class="sxs-lookup"><span data-stu-id="982eb-462">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p132">Stellt die Stärke des Audiosignals der postanalogen Verstärkung für das vom Angerufenen gesendete Audio dar. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="982eb-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-467">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="982eb-467">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="982eb-468">int</span><span class="sxs-lookup"><span data-stu-id="982eb-468">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p133">Stärke des Audiosignals für das vom Angerufenen empfangene Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="982eb-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-473">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="982eb-473">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="982eb-474">int</span><span class="sxs-lookup"><span data-stu-id="982eb-474">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p134">Stärke des Audiogeräuschs der postanalogen Verstärkung für das vom Angerufenen gesendete Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="982eb-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-479">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="982eb-479">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="982eb-480">int</span><span class="sxs-lookup"><span data-stu-id="982eb-480">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p135">Stärke des Audiogeräuschs der postanalogen Verstärkung für das vom Angerufenen empfangene Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="982eb-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-485">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="982eb-485">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="982eb-486">int</span><span class="sxs-lookup"><span data-stu-id="982eb-486">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p136">Echodämpfungsverbesserung für den Angerufenen. Die Einheit für diese Metrik ist dB. Niedrigere Werte bedeuten weniger Echo. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="982eb-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-491">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="982eb-491">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="982eb-492">int</span><span class="sxs-lookup"><span data-stu-id="982eb-492">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p137">Durchschnittliche Verzögerungen pro fünf Minuten für die Lautsprecherwiedergabe des Angerufenen. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="982eb-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-496">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="982eb-496">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="982eb-497">int</span><span class="sxs-lookup"><span data-stu-id="982eb-497">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p138">Durchschnittliche Verzögerungen pro fünf Minuten für die Mikrofonerfassung des Angerufenen. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="982eb-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-501">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="982eb-501">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="982eb-502">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-502">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-503">Driftrate der Uhr des Mikrofons des Angerufenen, relativ zum CPU-Takt.</span><span class="sxs-lookup"><span data-stu-id="982eb-503">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-504">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="982eb-504">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="982eb-505">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-505">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-506">Driftrate der Uhr des Lautsprechers des Angerufenen, relativ zum CPU-Takt.</span><span class="sxs-lookup"><span data-stu-id="982eb-506">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-507">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="982eb-507">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="982eb-508">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-508">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-509">Durchschnittlicher Zeitstempelfehler des Mikrofonaufnahme-Datenstroms in Millisekunden, in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="982eb-509">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-510">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="982eb-510">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="982eb-511">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-511">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-512">Durchschnittlicher Zeitstempelfehler des Lautsprecherwiedergabe-Datenstroms des Angerufenen in Millisekunden, in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="982eb-512">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-513">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="982eb-513">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="982eb-514">smallint</span><span class="sxs-lookup"><span data-stu-id="982eb-514">smallint</span></span></p></td>
<td><p><span data-ttu-id="982eb-515">Bei der Sprachumschaltung handelt es sich um einen Halbduplexmodus mit der Fähigkeit, Unterbrechungen zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="982eb-515">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="982eb-516">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="982eb-516">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-517">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="982eb-517">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="982eb-518">tinyint</span><span class="sxs-lookup"><span data-stu-id="982eb-518">tinyint</span></span></p></td>
<td><p><span data-ttu-id="982eb-519">Ursachen von Echoereignissen für den Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-519">Causes of an echo event for the callee.</span></span> <span data-ttu-id="982eb-520">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="982eb-520">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-521">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="982eb-521">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="982eb-522">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-522">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-p141">Prozentsatz der Zeit, in der im Mikrofonaufnahme-Datenstrom des Angerufenen Echo festgestellt wird. Bei der Verwendung eines Headsets ist der Wert in der Regel niedrig.</span><span class="sxs-lookup"><span data-stu-id="982eb-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-525">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="982eb-525">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="982eb-526">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-526">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-p142">Prozentsatz der Zeit, in der im gesendeten Datenstrom des Angerufenen Echo festgestellt wird. Ein hoher Echoprozentsatz in gesendeten Datenströmen deutet auf eine Beeinträchtigung durch Echo hin.</span><span class="sxs-lookup"><span data-stu-id="982eb-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-529">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="982eb-529">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="982eb-530">int</span><span class="sxs-lookup"><span data-stu-id="982eb-530">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p143">Stärke des auf dem Vermittlungsserver empfangenen Signals vom Gateway für das Audio des Angerufenen; betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich zwischen [-30 und -18] dBoV liegen.</span><span class="sxs-lookup"><span data-stu-id="982eb-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-534">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="982eb-534">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="982eb-535">int</span><span class="sxs-lookup"><span data-stu-id="982eb-535">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-p144">Stärke des auf dem Vermittlungsserver empfangenen Signals vom Gateway für das Audio des Angerufenen. Dies betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich unter -50 dBoV liegen.</span><span class="sxs-lookup"><span data-stu-id="982eb-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-540">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="982eb-540">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="982eb-541">int</span><span class="sxs-lookup"><span data-stu-id="982eb-541">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-542">Eingebauter Verstärker (AGC) auf der Vermittlungsserverseite angewendet auf das Audio des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="982eb-542">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-543">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="982eb-543">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="982eb-544">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="982eb-544">float</span></span></p></td>
<td><p><span data-ttu-id="982eb-545">RMS (Effektivwert) des eingehenden Signals an den Angerufenen in den ersten 30 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="982eb-545">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-546">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="982eb-546">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="982eb-547">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-547">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-548">Durchschnittliches Verhältnis zwischen ausgeblendeten Samples, generiert durch Audioreparatur, und Standardsamples.</span><span class="sxs-lookup"><span data-stu-id="982eb-548">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-549">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="982eb-549">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="982eb-550">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-550">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-551">Durchschnittliches Verhältnis zwischen gestreckten Samples, generiert durch Audioreparatur, und Standardsamples.</span><span class="sxs-lookup"><span data-stu-id="982eb-551">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-552">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="982eb-552">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="982eb-553">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-553">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-554">Durchschnittliches Verhältnis zwischen komprimierten Samples, generiert durch Audioreparatur, und Standardsamples.</span><span class="sxs-lookup"><span data-stu-id="982eb-554">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-555">Roundtrip</span><span class="sxs-lookup"><span data-stu-id="982eb-555">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="982eb-556">int</span><span class="sxs-lookup"><span data-stu-id="982eb-556">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-557">Roundtripzeit aus RTCP-Statistik.</span><span class="sxs-lookup"><span data-stu-id="982eb-557">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-558">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="982eb-558">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="982eb-559">int</span><span class="sxs-lookup"><span data-stu-id="982eb-559">int</span></span></p></td>
<td><p><span data-ttu-id="982eb-560">Maximale Roundtripzeit für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="982eb-560">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-561">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="982eb-561">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="982eb-562">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-562">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-p145">Durchschnittlicher Breitband-Netzwerk-MOS für den Anruf. Diese Metrik ist abhängig vom Paketverlust, Jitter und dem verwendeten Codec. Der Bereich umfasst [1,0 bis 5,0].</span><span class="sxs-lookup"><span data-stu-id="982eb-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-566">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="982eb-566">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="982eb-567">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-567">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-568">Minimaler Breitband-Netzwerk-MOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="982eb-568">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-569">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="982eb-569">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="982eb-570">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-570">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-571">Durchschnittlicher vorhergesagter Breitband-Hör-MOS für gesendetes Audio, einschließlich Sprachpegel, Rauschen und Aufnahmegerätmerkmale.</span><span class="sxs-lookup"><span data-stu-id="982eb-571">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-572">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="982eb-572">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="982eb-573">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-573">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-574">Minimaler SendListenMOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="982eb-574">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-575">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="982eb-575">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="982eb-576">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-576">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-577">Durchschnittlicher vorhergesagter Breitband-Hör-MOS für empfangenes Audio aus dem Netzwerk, einschließlich Sprachpegel, Rauschen, Codec, Netzwerkbedingungen und Aufnahmegerätmerkmale.</span><span class="sxs-lookup"><span data-stu-id="982eb-577">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-578">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="982eb-578">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="982eb-579">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="982eb-579">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="982eb-580">Minimaler RecvListenMOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="982eb-580">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="982eb-581">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="982eb-581">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="982eb-582">Bit</span><span class="sxs-lookup"><span data-stu-id="982eb-582">bit</span></span></p></td>
<td><p><span data-ttu-id="982eb-583">Gibt an, ob Audio-FEC für den Anruf verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="982eb-583">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="982eb-584">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="982eb-584">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="982eb-585">Bit</span><span class="sxs-lookup"><span data-stu-id="982eb-585">bit</span></span></p></td>
<td><p><span data-ttu-id="982eb-586">Gibt die Richtung der P-Asserted-Identify-Information an; 1 bedeutet, dass die Streamrichtung vom Anrufer zum Angerufenen verläuft; 0 bedeutet, dass die Streamrichtung vom Angerufenen zum Anrufer verläuft.</span><span class="sxs-lookup"><span data-stu-id="982eb-586">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

