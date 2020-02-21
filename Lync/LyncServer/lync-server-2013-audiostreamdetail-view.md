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
ms.openlocfilehash: fe995d08bf334308603512b4812b02c672d400f4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="51d0a-102">AudioStreamDetail-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51d0a-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51d0a-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="51d0a-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="51d0a-104">Die AudioStreamDetail-Ansicht speichert Informationen über jeden Audiostream in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="51d0a-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="51d0a-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="51d0a-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51d0a-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="51d0a-106">Column</span></span></th>
<th><span data-ttu-id="51d0a-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="51d0a-107">Data Type</span></span></th>
<th><span data-ttu-id="51d0a-108">Details</span><span class="sxs-lookup"><span data-stu-id="51d0a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="51d0a-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="51d0a-110">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="51d0a-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="51d0a-111"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="51d0a-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="51d0a-113">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-113">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-114"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-115">Datenstrom-Nr</span><span class="sxs-lookup"><span data-stu-id="51d0a-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="51d0a-116">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-116">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-117">Eindeutige ID innerhalb einer Medienzeile.</span><span class="sxs-lookup"><span data-stu-id="51d0a-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="51d0a-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="51d0a-119">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="51d0a-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="51d0a-120">Startzeitpunkt der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="51d0a-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="51d0a-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="51d0a-122">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="51d0a-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="51d0a-123">Endzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="51d0a-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="51d0a-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="51d0a-125">Bit</span><span class="sxs-lookup"><span data-stu-id="51d0a-125">bit</span></span></p></td>
<td><p><span data-ttu-id="51d0a-126">Dialog Feld Kategorie: 0 ist die lync Server Vermittlungsserver Bein; 1 ist die Vermittlungsserver zu PSTN-Gateway-Bein.</span><span class="sxs-lookup"><span data-stu-id="51d0a-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="51d0a-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="51d0a-128">Bit</span><span class="sxs-lookup"><span data-stu-id="51d0a-128">bit</span></span></p></td>
<td><p><span data-ttu-id="51d0a-129">Flag, das angibt, ob der Anruf umgangen wurde oder nicht.</span><span class="sxs-lookup"><span data-stu-id="51d0a-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="51d0a-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="51d0a-131">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-131">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p102">Gibt an (falls vorhanden), warum ein Anruf nicht umgangen wurde, auch wenn die Umgehungs-IDs übereinstimmten. Es ist nur ein Wert definiert:</span><span class="sxs-lookup"><span data-stu-id="51d0a-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="51d0a-134">0x0001 – Unbekannte Umgehungs-ID für Standardnetzwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="51d0a-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="51d0a-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="51d0a-136">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-136">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-137">Priorität des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="51d0a-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="51d0a-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="51d0a-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="51d0a-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-140">FQDN des Anruferpools.</span><span class="sxs-lookup"><span data-stu-id="51d0a-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="51d0a-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="51d0a-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="51d0a-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-143">FQDN des Angerufenenpools.</span><span class="sxs-lookup"><span data-stu-id="51d0a-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-144">Anrufer</span><span class="sxs-lookup"><span data-stu-id="51d0a-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="51d0a-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="51d0a-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-146">URI des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="51d0a-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-147">Aufgerufene</span><span class="sxs-lookup"><span data-stu-id="51d0a-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="51d0a-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="51d0a-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-149">URI des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="51d0a-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="51d0a-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="51d0a-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-152">Zeichenfolge für den Benutzer-Agent des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="51d0a-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="51d0a-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="51d0a-154">smallint</span><span class="sxs-lookup"><span data-stu-id="51d0a-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="51d0a-155">Benutzeragentenart des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="51d0a-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="51d0a-156">Ausführliche Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51d0a-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="51d0a-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="51d0a-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="51d0a-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-159">Benutzeragentenkategorie des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="51d0a-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="51d0a-160">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51d0a-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="51d0a-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="51d0a-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="51d0a-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-163">Zeichenfolge für den Benutzer-Agent des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="51d0a-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="51d0a-165">smallint</span><span class="sxs-lookup"><span data-stu-id="51d0a-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="51d0a-166">Typ des Benutzer-Agent des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-166">Type of callee’s user agent.</span></span> <span data-ttu-id="51d0a-167">Weitere Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51d0a-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="51d0a-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="51d0a-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="51d0a-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-170">Kategorie des Benutzer-Agent des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-170">Category of callee’s user agent.</span></span> <span data-ttu-id="51d0a-171">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51d0a-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="51d0a-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="51d0a-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="51d0a-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-174">Name des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="51d0a-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="51d0a-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="51d0a-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="51d0a-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-177">Name des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-178">Anrufer</span><span class="sxs-lookup"><span data-stu-id="51d0a-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="51d0a-179">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="51d0a-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-180">Betriebssystem des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="51d0a-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="51d0a-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="51d0a-182">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="51d0a-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-183">Betriebssystem des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="51d0a-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="51d0a-185">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="51d0a-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-186">Name der CPU des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="51d0a-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="51d0a-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="51d0a-188">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="51d0a-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-189">Name der CPU des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="51d0a-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="51d0a-191">smallint</span><span class="sxs-lookup"><span data-stu-id="51d0a-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="51d0a-192">Anzahl der Prozessorkerne des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="51d0a-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="51d0a-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="51d0a-194">smallint</span><span class="sxs-lookup"><span data-stu-id="51d0a-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="51d0a-195">Anzahl der Prozessorkerne des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="51d0a-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="51d0a-197">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-197">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-198">Prozessorgeschwindigkeit der CPU des Endpunkts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="51d0a-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="51d0a-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="51d0a-200">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-200">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-201">Prozessorgeschwindigkeit der CPU des Endpunkts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="51d0a-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="51d0a-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="51d0a-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="51d0a-204">Gibt an, ob das System des Anrufers in einer virtualisierten Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="51d0a-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="51d0a-205">Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpoint-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51d0a-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="51d0a-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="51d0a-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="51d0a-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="51d0a-208">Gibt an, ob das System des Angerufenen in einer virtualisierten Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="51d0a-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="51d0a-209">Weitere Informationen finden Sie <a href="lync-server-2013-endpoint-table.md">in der Endpoint-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51d0a-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="51d0a-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="51d0a-211">Korrelationsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="51d0a-211">Correlation key.</span></span> <span data-ttu-id="51d0a-212">Referenziert aus der <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation-Tabelle in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="51d0a-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="51d0a-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="51d0a-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="51d0a-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="51d0a-215">Informationen zum Medienpfad, z. B. direkt oder Relay.</span><span class="sxs-lookup"><span data-stu-id="51d0a-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="51d0a-216">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51d0a-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="51d0a-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="51d0a-218">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-218">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p111">Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Anrufer, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".</span><span class="sxs-lookup"><span data-stu-id="51d0a-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="51d0a-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="51d0a-222">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-222">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p112">Informationen zur interaktiven Verbindungsherstellung (Interactive Connectivity Establishment, ICE) für den Angerufenen, in Bitflags beschrieben. Ausführliche Informationen finden Sie im Artikel "[MS-QoE]: Spezifikation für das Quality of Experience Monitoring Server-Protokoll".</span><span class="sxs-lookup"><span data-stu-id="51d0a-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-225">Transport</span><span class="sxs-lookup"><span data-stu-id="51d0a-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="51d0a-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="51d0a-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="51d0a-227">Transporttyp: 0 ist UDP, 1 ist TCP.</span><span class="sxs-lookup"><span data-stu-id="51d0a-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="51d0a-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="51d0a-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="51d0a-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-230">IP-Adresse des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="51d0a-230">IP address of the caller.</span></span> <span data-ttu-id="51d0a-231">Dies kann eine IPv4- oder eine IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="51d0a-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="51d0a-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="51d0a-233">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-233">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-234">Vom Anrufer verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="51d0a-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="51d0a-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="51d0a-236">Bit</span><span class="sxs-lookup"><span data-stu-id="51d0a-236">bit</span></span></p></td>
<td><p><span data-ttu-id="51d0a-237">Gibt an, ob sich der Anrufer innerhalb des Intervallnetzwerks befindet: 1 bedeutet, dass der Anrufer sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Anrufer außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="51d0a-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="51d0a-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="51d0a-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="51d0a-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-240">IP-Adresse des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-240">IP address of the callee.</span></span> <span data-ttu-id="51d0a-241">Dies kann eine IPv4- oder eine IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="51d0a-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="51d0a-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="51d0a-243">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-243">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-244">Vom Angerufenen verwendeter Port.</span><span class="sxs-lookup"><span data-stu-id="51d0a-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="51d0a-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="51d0a-246">Bit</span><span class="sxs-lookup"><span data-stu-id="51d0a-246">bit</span></span></p></td>
<td><p><span data-ttu-id="51d0a-247">Gibt an, ob sich der Angerufene innerhalb des Intervallnetzwerks befindet: 1 bedeutet, dass der Angerufene sich innerhalb des Unternehmensnetzwerks befindet, 0 bedeutet, dass sich der Angerufene außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="51d0a-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="51d0a-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="51d0a-249">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="51d0a-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-250">Name der Website des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="51d0a-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="51d0a-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="51d0a-252">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="51d0a-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-253">Name des Landes/der Region der Website des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="51d0a-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="51d0a-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="51d0a-255">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="51d0a-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-256">Name der Website des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="51d0a-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="51d0a-258">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="51d0a-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-259">Name des Landes/der Region der Website des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="51d0a-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="51d0a-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="51d0a-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-262">IP-Adresse des vom Anrufer verwendeten A/V-Edgedienstes.</span><span class="sxs-lookup"><span data-stu-id="51d0a-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="51d0a-263">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51d0a-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="51d0a-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="51d0a-265">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-265">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-266">Der durch den A/V-Edgedienst des Anrufers verwendete Port.</span><span class="sxs-lookup"><span data-stu-id="51d0a-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="51d0a-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="51d0a-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="51d0a-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-269">IP-Adressschlüssel des vom Anrufer verwendeten A/V-Edgedienstes.</span><span class="sxs-lookup"><span data-stu-id="51d0a-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="51d0a-270">Weitere Informationen finden Sie <a href="lync-server-2013-ipaddress-table.md">in der IPAddress-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51d0a-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="51d0a-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="51d0a-272">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-272">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-273">Der durch den A/V-Edgedienst des Angerufenen verwendete Port.</span><span class="sxs-lookup"><span data-stu-id="51d0a-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="51d0a-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="51d0a-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="51d0a-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-276">Name des Aufnahmegeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="51d0a-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="51d0a-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="51d0a-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="51d0a-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-279">Name des Darstellungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="51d0a-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="51d0a-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="51d0a-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="51d0a-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-282">Name des Treibers für das Aufnahmegerät des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="51d0a-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="51d0a-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="51d0a-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="51d0a-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-285">Name des Gerätetreibers des Darstellungsgeräts des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="51d0a-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="51d0a-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="51d0a-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="51d0a-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-288">Name des Aufnahmegeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="51d0a-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="51d0a-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="51d0a-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-291">Name des Darstellungsgeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="51d0a-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="51d0a-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="51d0a-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-294">Name des Gerätetreibers des Aufnahmegeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="51d0a-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="51d0a-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="51d0a-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-297">Name des Gerätetreibers des Darstellungsgeräts des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="51d0a-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="51d0a-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="51d0a-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="51d0a-300">Typ der Netzwerkverbindung des Anrufers: 0 ist verkabelt, 1 ist kabellos.</span><span class="sxs-lookup"><span data-stu-id="51d0a-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="51d0a-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="51d0a-302">Bit</span><span class="sxs-lookup"><span data-stu-id="51d0a-302">bit</span></span></p></td>
<td><p><span data-ttu-id="51d0a-303">Gibt an, ob der Anrufer eine Verbindung über ein virtuelles privates Netzwerk hergestellt hat: 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.</span><span class="sxs-lookup"><span data-stu-id="51d0a-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="51d0a-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="51d0a-305">Decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="51d0a-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-306">Netzwerkübertragungsrate für den Endpunkt des Anrufers in Bit/s.</span><span class="sxs-lookup"><span data-stu-id="51d0a-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="51d0a-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="51d0a-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="51d0a-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="51d0a-309">Typ der Netzwerkverbindung des Angerufenen: 0 ist verkabelt, 1 ist kabellos.</span><span class="sxs-lookup"><span data-stu-id="51d0a-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="51d0a-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="51d0a-311">Bit</span><span class="sxs-lookup"><span data-stu-id="51d0a-311">bit</span></span></p></td>
<td><p><span data-ttu-id="51d0a-312">Gibt an, ob der Anrufer eine Verbindung über ein virtuelles privates Netzwerk hergestellt hat: 1 ist VPN (virtuelles privates Netzwerk), 0 ist Nicht-VPN.</span><span class="sxs-lookup"><span data-stu-id="51d0a-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="51d0a-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="51d0a-314">Decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="51d0a-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-315">Netzwerkübertragungsrate für den Endpunkt des Angerufenen in Bit/s.</span><span class="sxs-lookup"><span data-stu-id="51d0a-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="51d0a-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="51d0a-317">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-318">Schmalband-Gesprächs-MOS der Audiositzungen (basierend auf beiden Audiostreams).</span><span class="sxs-lookup"><span data-stu-id="51d0a-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="51d0a-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="51d0a-320">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-320">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p117">Genutzte Bandbreite, die unter verschiedenen Richtlinieneinstellungen (TURN, API, SDP, Richtlinienserver usw.) auf den jeweiligen Stream auf der Seite des Absenders angewendet wird. Dies ist nicht zu verwechseln mit der tatsächlichen Bandbreite, da diese u. U. basierend auf der Bandbreitenschätzung niedriger ist. Dabei handelt es sich um die maximale Bandbreite, die für den Absenderstream möglich ist, abgesehen von den Beschränkungen durch die Bandbreitenschätzung.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="51d0a-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="51d0a-325">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-325">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-326">Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="51d0a-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="51d0a-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="51d0a-328">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-328">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-329">Maximaler Netzwerkjitter während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="51d0a-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="51d0a-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="51d0a-331">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="51d0a-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-332">Durchschnittliche Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="51d0a-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="51d0a-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="51d0a-334">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="51d0a-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-335">Maximale Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="51d0a-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="51d0a-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="51d0a-337">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="51d0a-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-338">Durchschnittliche Dichte an Paketverlusten bei Bursts von Verlusten während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="51d0a-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="51d0a-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="51d0a-340">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-340">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-341">Durchschnittliche Dauer an Paketverlusten bei Bursts von Verlusten während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="51d0a-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="51d0a-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="51d0a-343">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="51d0a-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-344">Durchschnittliche Dichte an Paketverlusten bei Lücken zwischen Bursts von Paketverlusten.</span><span class="sxs-lookup"><span data-stu-id="51d0a-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="51d0a-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="51d0a-346">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-346">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-347">Durchschnittliche Dauer der Lücken zwischen Bursts von Paketverlusten.</span><span class="sxs-lookup"><span data-stu-id="51d0a-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="51d0a-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="51d0a-349">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-349">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-350">Paketwert für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="51d0a-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-351">Bandbreite</span><span class="sxs-lookup"><span data-stu-id="51d0a-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="51d0a-352">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-352">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-353">Bandbreitenschätzwerte für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="51d0a-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="51d0a-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="51d0a-355">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p118">Netzwerk-MOS-Beeinträchtigung für den gesamten Anruf. Der Bereich umfasst 0,0 bis 5,0.  Diese Metrik gibt an, um welche Menge der Netzwerk-MOS aufgrund von Jitter und Paketverlusten reduziert wurde. Der Wert sollte weniger als 0,5 betragen, um eine akzeptable Qualität zu bieten.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="51d0a-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="51d0a-361">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-362">Maximale Netzwerk-MOS-Beeinträchtigung während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="51d0a-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="51d0a-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="51d0a-364">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-365">Netzwerk-MOS-Beeinträchtigung aufgrund von Jitter.</span><span class="sxs-lookup"><span data-stu-id="51d0a-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="51d0a-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="51d0a-367">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-368">Netzwerk-MOS-Beeinträchtigung aufgrund von Paketverlust.</span><span class="sxs-lookup"><span data-stu-id="51d0a-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="51d0a-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="51d0a-370">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-370">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-371">Der für den Aufruf verwendete Audiocodec, der <a href="lync-server-2013-payloaddescription-table.md">in lync Server 2013</a>von der PayloadDescription-Tabelle referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="51d0a-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="51d0a-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="51d0a-373">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-373">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-374">Samplingrate für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="51d0a-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="51d0a-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="51d0a-376">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-376">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p119">Stärke des Audiosignals der postanalogen Verstärkung für das vom Anrufer gesendete Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="51d0a-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="51d0a-382">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-382">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p120">Stärke des Audiosignals für das vom Anrufer empfangene Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="51d0a-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="51d0a-388">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-388">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p121">Stärke des Audiogeräusches der postanalogen Verstärkung für das vom Anrufer gesendete Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="51d0a-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="51d0a-394">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-394">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p122">Stärke des Audiogeräuschs der postanalogen Verstärkung für das vom Anrufer empfangene Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="51d0a-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="51d0a-400">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-400">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p123">Echodämpfungsverbesserung für den Anrufer. Die Einheit für diese Metrik ist dB. Niedrigere Werte bedeuten weniger Echo. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="51d0a-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="51d0a-406">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-406">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p124">Durchschnittliche Verzögerungen pro fünf Minuten für die Lautsprecherwiedergabe des Anrufers. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="51d0a-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="51d0a-411">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-411">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p125">Durchschnittliche Verzögerungen pro fünf Minuten für die Mikrofonerfassung des Anrufers. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="51d0a-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="51d0a-416">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-417">Driftrate der Uhr des Mikrofons des Anrufers, relativ zum CPU-Takt.</span><span class="sxs-lookup"><span data-stu-id="51d0a-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="51d0a-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="51d0a-419">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-420">Driftrate der Uhr des Lautsprechers des Anrufers, relativ zum CPU-Takt.</span><span class="sxs-lookup"><span data-stu-id="51d0a-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="51d0a-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="51d0a-422">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-423">Durchschnittlicher Zeitstempelfehler des Mikrofonaufnahme-Datenstroms in Millisekunden, in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="51d0a-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="51d0a-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="51d0a-425">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-426">Durchschnittlicher Zeitstempelfehler des Lautsprecherwiedergabe-Datenstroms des Anrufers in Millisekunden, in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="51d0a-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="51d0a-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="51d0a-428">smallint</span><span class="sxs-lookup"><span data-stu-id="51d0a-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="51d0a-429">Bei der Sprachumschaltung handelt es sich um einen Halbduplexmodus mit der Fähigkeit, Unterbrechungen zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="51d0a-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="51d0a-430">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51d0a-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="51d0a-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="51d0a-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="51d0a-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="51d0a-433">Ursachen von Echoereignissen für den Anrufer.</span><span class="sxs-lookup"><span data-stu-id="51d0a-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="51d0a-434">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51d0a-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="51d0a-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="51d0a-436">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p128">Prozentsatz der Zeit, in der im Mikrofonaufnahme-Datenstrom des Anrufers Echo festgestellt wird. Bei der Verwendung eines Headsets ist der Wert in der Regel niedrig.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="51d0a-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="51d0a-440">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p129">Prozentsatz der Zeit, in der im gesendeten Datenstrom des Anrufers Echo festgestellt wird. Ein hoher Echoprozentsatz in gesendeten Datenströmen deutet auf eine Beeinträchtigung durch Echo hin.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="51d0a-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="51d0a-444">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-444">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p130">Stärke des auf dem Vermittlungsserver empfangenen Signals vom Gateway für das Audio des Anrufers; betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich zwischen [-30 und -18] dBoV liegen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="51d0a-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="51d0a-449">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-449">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p131">Stärke des auf dem Vermittlungsserver empfangenen Signals vom Gateway für das Audio des Anrufers. Dies betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich unter -50 dBoV liegen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="51d0a-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="51d0a-455">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-455">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-456">Eingebauter Verstärker (AGC) auf der Vermittlungsserverseite angewendet auf das Audio des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="51d0a-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="51d0a-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="51d0a-458">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="51d0a-458">float</span></span></p></td>
<td><p><span data-ttu-id="51d0a-459">RMS (Effektivwert) des eingehenden Signals an den Anrufer in den ersten 30 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="51d0a-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="51d0a-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="51d0a-461">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-461">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p132">Stellt die Stärke des Audiosignals der postanalogen Verstärkung für das vom Angerufenen gesendete Audio dar. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="51d0a-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="51d0a-467">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-467">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p133">Stärke des Audiosignals für das vom Angerufenen empfangene Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="51d0a-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="51d0a-473">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-473">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p134">Stärke des Audiogeräuschs der postanalogen Verstärkung für das vom Angerufenen gesendete Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="51d0a-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="51d0a-479">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-479">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p135">Stärke des Audiogeräuschs der postanalogen Verstärkung für das vom Angerufenen empfangene Audio. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="51d0a-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="51d0a-485">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-485">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p136">Echodämpfungsverbesserung für den Angerufenen. Die Einheit für diese Metrik ist dB. Niedrigere Werte bedeuten weniger Echo. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="51d0a-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="51d0a-491">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-491">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p137">Durchschnittliche Verzögerungen pro fünf Minuten für die Lautsprecherwiedergabe des Angerufenen. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="51d0a-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="51d0a-496">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-496">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p138">Durchschnittliche Verzögerungen pro fünf Minuten für die Mikrofonerfassung des Angerufenen. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="51d0a-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="51d0a-501">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-502">Driftrate der Uhr des Mikrofons des Angerufenen, relativ zum CPU-Takt.</span><span class="sxs-lookup"><span data-stu-id="51d0a-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="51d0a-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="51d0a-504">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-505">Driftrate der Uhr des Lautsprechers des Angerufenen, relativ zum CPU-Takt.</span><span class="sxs-lookup"><span data-stu-id="51d0a-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="51d0a-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="51d0a-507">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-508">Durchschnittlicher Zeitstempelfehler des Mikrofonaufnahme-Datenstroms in Millisekunden, in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="51d0a-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="51d0a-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="51d0a-510">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-511">Durchschnittlicher Zeitstempelfehler des Lautsprecherwiedergabe-Datenstroms des Angerufenen in Millisekunden, in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="51d0a-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="51d0a-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="51d0a-513">smallint</span><span class="sxs-lookup"><span data-stu-id="51d0a-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="51d0a-514">Bei der Sprachumschaltung handelt es sich um einen Halbduplexmodus mit der Fähigkeit, Unterbrechungen zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="51d0a-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="51d0a-515">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51d0a-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="51d0a-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="51d0a-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="51d0a-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="51d0a-518">Ursachen von Echoereignissen für den Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="51d0a-519">Weitere Informationen finden Sie <a href="lync-server-2013-medialine-table.md">in der Medientabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51d0a-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="51d0a-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="51d0a-521">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p141">Prozentsatz der Zeit, in der im Mikrofonaufnahme-Datenstrom des Angerufenen Echo festgestellt wird. Bei der Verwendung eines Headsets ist der Wert in der Regel niedrig.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="51d0a-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="51d0a-525">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p142">Prozentsatz der Zeit, in der im gesendeten Datenstrom des Angerufenen Echo festgestellt wird. Ein hoher Echoprozentsatz in gesendeten Datenströmen deutet auf eine Beeinträchtigung durch Echo hin.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="51d0a-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="51d0a-529">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-529">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p143">Stärke des auf dem Vermittlungsserver empfangenen Signals vom Gateway für das Audio des Angerufenen; betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich zwischen [-30 und -18] dBoV liegen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="51d0a-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="51d0a-534">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-534">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p144">Stärke des auf dem Vermittlungsserver empfangenen Signals vom Gateway für das Audio des Angerufenen. Dies betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich unter -50 dBoV liegen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="51d0a-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="51d0a-540">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-540">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-541">Eingebauter Verstärker (AGC) auf der Vermittlungsserverseite angewendet auf das Audio des Angerufenen.</span><span class="sxs-lookup"><span data-stu-id="51d0a-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="51d0a-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="51d0a-543">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="51d0a-543">float</span></span></p></td>
<td><p><span data-ttu-id="51d0a-544">RMS (Effektivwert) des eingehenden Signals an den Angerufenen in den ersten 30 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="51d0a-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="51d0a-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="51d0a-546">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-547">Durchschnittliches Verhältnis zwischen ausgeblendeten Samples, generiert durch Audioreparatur, und Standardsamples.</span><span class="sxs-lookup"><span data-stu-id="51d0a-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="51d0a-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="51d0a-549">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-550">Durchschnittliches Verhältnis zwischen gestreckten Samples, generiert durch Audioreparatur, und Standardsamples.</span><span class="sxs-lookup"><span data-stu-id="51d0a-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="51d0a-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="51d0a-552">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-553">Durchschnittliches Verhältnis zwischen komprimierten Samples, generiert durch Audioreparatur, und Standardsamples.</span><span class="sxs-lookup"><span data-stu-id="51d0a-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-554">Roundtrip</span><span class="sxs-lookup"><span data-stu-id="51d0a-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="51d0a-555">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-555">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-556">Roundtripzeit aus RTCP-Statistik.</span><span class="sxs-lookup"><span data-stu-id="51d0a-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="51d0a-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="51d0a-558">int</span><span class="sxs-lookup"><span data-stu-id="51d0a-558">int</span></span></p></td>
<td><p><span data-ttu-id="51d0a-559">Maximale Roundtripzeit für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="51d0a-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="51d0a-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="51d0a-561">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-p145">Durchschnittlicher Breitband-Netzwerk-MOS für den Anruf. Diese Metrik ist abhängig vom Paketverlust, Jitter und dem verwendeten Codec. Der Bereich umfasst [1,0 bis 5,0].</span><span class="sxs-lookup"><span data-stu-id="51d0a-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="51d0a-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="51d0a-566">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-567">Minimaler Breitband-Netzwerk-MOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="51d0a-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="51d0a-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="51d0a-569">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-570">Durchschnittlicher vorhergesagter Breitband-Hör-MOS für gesendetes Audio, einschließlich Sprachpegel, Rauschen und Aufnahmegerätmerkmale.</span><span class="sxs-lookup"><span data-stu-id="51d0a-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="51d0a-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="51d0a-572">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-573">Minimaler SendListenMOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="51d0a-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="51d0a-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="51d0a-575">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-576">Durchschnittlicher vorhergesagter Breitband-Hör-MOS für empfangenes Audio aus dem Netzwerk, einschließlich Sprachpegel, Rauschen, Codec, Netzwerkbedingungen und Aufnahmegerätmerkmale.</span><span class="sxs-lookup"><span data-stu-id="51d0a-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="51d0a-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="51d0a-578">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="51d0a-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="51d0a-579">Minimaler RecvListenMOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="51d0a-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51d0a-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="51d0a-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="51d0a-581">Bit</span><span class="sxs-lookup"><span data-stu-id="51d0a-581">bit</span></span></p></td>
<td><p><span data-ttu-id="51d0a-582">Gibt an, ob Audio-FEC für den Anruf verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="51d0a-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51d0a-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="51d0a-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="51d0a-584">Bit</span><span class="sxs-lookup"><span data-stu-id="51d0a-584">bit</span></span></p></td>
<td><p><span data-ttu-id="51d0a-585">Gibt die Richtung der P-Asserted-Identify-Information an; 1 bedeutet, dass die Streamrichtung vom Anrufer zum Angerufenen verläuft; 0 bedeutet, dass die Streamrichtung vom Angerufenen zum Anrufer verläuft.</span><span class="sxs-lookup"><span data-stu-id="51d0a-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

