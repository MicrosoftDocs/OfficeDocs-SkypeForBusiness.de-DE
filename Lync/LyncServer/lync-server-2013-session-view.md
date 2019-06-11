---
title: 'Lync Server 2013: Sitzungsansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a90d6a3f066caccb20b141daa485cabea29e2352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="f3d3e-102">Sitzungsansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3d3e-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3d3e-103">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="f3d3e-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="f3d3e-104">Die Sitzungsansicht speichert Informationen zu Sitzungen mit Datensätzen in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="f3d3e-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3d3e-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="f3d3e-106">Column</span></span></th>
<th><span data-ttu-id="f3d3e-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f3d3e-107">Data Type</span></span></th>
<th><span data-ttu-id="f3d3e-108">Details</span><span class="sxs-lookup"><span data-stu-id="f3d3e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3d3e-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="f3d3e-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-110">datetime</span><span class="sxs-lookup"><span data-stu-id="f3d3e-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-111">In der medialinie-Tabelle referenziert.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3d3e-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="f3d3e-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f3d3e-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-114">Konferenz-URI, wenn es sich um eine Konferenz handelt, oder wenn es sich um eine Peer-to-Peer-Sitzung handelt.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3d3e-115">Korrelation</span><span class="sxs-lookup"><span data-stu-id="f3d3e-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="f3d3e-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-117">Korrelations-ID der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3d3e-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="f3d3e-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-119">bit</span><span class="sxs-lookup"><span data-stu-id="f3d3e-119">bit</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-120">Dialog Feld Kategorie; 0 ist lync Server to Mediation Server Leg; 1 ist Vermittlungs Server für das PSTN-Gateway-Bein.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3d3e-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="f3d3e-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-122">bit</span><span class="sxs-lookup"><span data-stu-id="f3d3e-122">bit</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-123">Gibt an, ob der Anruf umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3d3e-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="f3d3e-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-125">int</span><span class="sxs-lookup"><span data-stu-id="f3d3e-125">int</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-126">Dieses Feld, falls vorhanden, gibt an, warum ein Anruf nicht umgangen wurde, auch wenn die Bypass-IDs übereinstimmten.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="f3d3e-127">Bei lync Server wird nur ein Wert definiert:</span><span class="sxs-lookup"><span data-stu-id="f3d3e-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="f3d3e-128">0x0001 – unbekannte Bypass-ID für den standardmäßigen Netzwerkadapter</span><span class="sxs-lookup"><span data-stu-id="f3d3e-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3d3e-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="f3d3e-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-130">datetime</span><span class="sxs-lookup"><span data-stu-id="f3d3e-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-131">Startzeit des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3d3e-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="f3d3e-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-133">datetime</span><span class="sxs-lookup"><span data-stu-id="f3d3e-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-134">Endzeit des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3d3e-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="f3d3e-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-136">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f3d3e-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-137">FQDN des anrufenden Pools.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3d3e-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="f3d3e-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f3d3e-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-140">FQDN des aufgerufenen Pools.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3d3e-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="f3d3e-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f3d3e-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-143">Identitäts-URI des Anrufers p-Assert</span><span class="sxs-lookup"><span data-stu-id="f3d3e-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3d3e-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="f3d3e-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f3d3e-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-146">P-Assert-Identitäts-URI des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3d3e-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="f3d3e-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f3d3e-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-149">Der Endpunktname des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3d3e-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="f3d3e-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f3d3e-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-152">Der Endpunktname des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3d3e-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="f3d3e-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f3d3e-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-155">Benutzer-Agent-Zeichenfolge des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3d3e-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="f3d3e-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-157">smallint</span><span class="sxs-lookup"><span data-stu-id="f3d3e-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-158">Der Typ des Benutzer-Agents des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-158">Type of caller’s user agent.</span></span> <span data-ttu-id="f3d3e-159">Weitere Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f3d3e-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3d3e-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="f3d3e-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="f3d3e-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-162">Kategorie des Benutzer-Agents des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-162">Category of caller’s user agent.</span></span> <span data-ttu-id="f3d3e-163">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f3d3e-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3d3e-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="f3d3e-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f3d3e-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-166">Benutzer-Agent-Zeichenfolge des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3d3e-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="f3d3e-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-168">smallint</span><span class="sxs-lookup"><span data-stu-id="f3d3e-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-169">Der Typ des Benutzer-Agents für den aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-169">Type of user agent for the callee.</span></span> <span data-ttu-id="f3d3e-170">Weitere Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f3d3e-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3d3e-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="f3d3e-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="f3d3e-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-173">Benutzer-Agent-Kategorie für den aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-173">User agent category for the callee.</span></span> <span data-ttu-id="f3d3e-174">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f3d3e-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3d3e-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="f3d3e-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f3d3e-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-177">URI des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3d3e-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="f3d3e-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f3d3e-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-180">URI des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3d3e-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="f3d3e-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-182">int</span><span class="sxs-lookup"><span data-stu-id="f3d3e-182">int</span></span></p></td>
<td><p><span data-ttu-id="f3d3e-183">Die Priorität des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

