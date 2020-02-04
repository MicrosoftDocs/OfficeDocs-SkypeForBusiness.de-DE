---
title: 'Lync Server 2013: Sitzungsansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a153899fd484da861088a8e7672a69707e46a59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="65b9b-102">Sitzungsansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65b9b-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65b9b-103">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="65b9b-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="65b9b-104">Die Sitzungsansicht speichert Informationen zu Sitzungen mit Datensätzen in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="65b9b-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="65b9b-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="65b9b-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65b9b-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="65b9b-106">Column</span></span></th>
<th><span data-ttu-id="65b9b-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="65b9b-107">Data Type</span></span></th>
<th><span data-ttu-id="65b9b-108">Details</span><span class="sxs-lookup"><span data-stu-id="65b9b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65b9b-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="65b9b-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="65b9b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="65b9b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="65b9b-111">In der medialinie-Tabelle referenziert.</span><span class="sxs-lookup"><span data-stu-id="65b9b-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65b9b-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="65b9b-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="65b9b-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="65b9b-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="65b9b-114">Konferenz-URI, wenn es sich um eine Konferenz handelt, oder wenn es sich um eine Peer-to-Peer-Sitzung handelt.</span><span class="sxs-lookup"><span data-stu-id="65b9b-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65b9b-115">Korrelation</span><span class="sxs-lookup"><span data-stu-id="65b9b-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="65b9b-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="65b9b-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="65b9b-117">Korrelations-ID der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="65b9b-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65b9b-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="65b9b-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="65b9b-119">bit</span><span class="sxs-lookup"><span data-stu-id="65b9b-119">bit</span></span></p></td>
<td><p><span data-ttu-id="65b9b-120">Dialog Feld Kategorie; 0 ist lync Server to Mediation Server Leg; 1 ist Vermittlungs Server für das PSTN-Gateway-Bein.</span><span class="sxs-lookup"><span data-stu-id="65b9b-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65b9b-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="65b9b-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="65b9b-122">bit</span><span class="sxs-lookup"><span data-stu-id="65b9b-122">bit</span></span></p></td>
<td><p><span data-ttu-id="65b9b-123">Gibt an, ob der Anruf umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="65b9b-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65b9b-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="65b9b-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="65b9b-125">int</span><span class="sxs-lookup"><span data-stu-id="65b9b-125">int</span></span></p></td>
<td><p><span data-ttu-id="65b9b-126">Dieses Feld, falls vorhanden, gibt an, warum ein Anruf nicht umgangen wurde, auch wenn die Bypass-IDs übereinstimmten.</span><span class="sxs-lookup"><span data-stu-id="65b9b-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="65b9b-127">Bei lync Server wird nur ein Wert definiert:</span><span class="sxs-lookup"><span data-stu-id="65b9b-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="65b9b-128">0x0001 – unbekannte Bypass-ID für den standardmäßigen Netzwerkadapter</span><span class="sxs-lookup"><span data-stu-id="65b9b-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65b9b-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="65b9b-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="65b9b-130">datetime</span><span class="sxs-lookup"><span data-stu-id="65b9b-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="65b9b-131">Startzeit des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="65b9b-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65b9b-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="65b9b-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="65b9b-133">datetime</span><span class="sxs-lookup"><span data-stu-id="65b9b-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="65b9b-134">Endzeit des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="65b9b-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65b9b-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="65b9b-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="65b9b-136">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="65b9b-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="65b9b-137">FQDN des anrufenden Pools.</span><span class="sxs-lookup"><span data-stu-id="65b9b-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65b9b-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="65b9b-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="65b9b-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="65b9b-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="65b9b-140">FQDN des aufgerufenen Pools.</span><span class="sxs-lookup"><span data-stu-id="65b9b-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65b9b-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="65b9b-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="65b9b-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="65b9b-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="65b9b-143">Identitäts-URI des Anrufers p-Assert</span><span class="sxs-lookup"><span data-stu-id="65b9b-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65b9b-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="65b9b-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="65b9b-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="65b9b-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="65b9b-146">P-Assert-Identitäts-URI des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="65b9b-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65b9b-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="65b9b-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="65b9b-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="65b9b-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="65b9b-149">Der Endpunktname des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="65b9b-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65b9b-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="65b9b-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="65b9b-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="65b9b-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="65b9b-152">Der Endpunktname des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="65b9b-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65b9b-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="65b9b-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="65b9b-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="65b9b-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="65b9b-155">Benutzer-Agent-Zeichenfolge des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="65b9b-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65b9b-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="65b9b-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="65b9b-157">smallint</span><span class="sxs-lookup"><span data-stu-id="65b9b-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="65b9b-158">Der Typ des Benutzer-Agents des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="65b9b-158">Type of caller’s user agent.</span></span> <span data-ttu-id="65b9b-159">Weitere Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="65b9b-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65b9b-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="65b9b-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="65b9b-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="65b9b-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="65b9b-162">Kategorie des Benutzer-Agents des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="65b9b-162">Category of caller’s user agent.</span></span> <span data-ttu-id="65b9b-163">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="65b9b-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65b9b-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="65b9b-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="65b9b-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="65b9b-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="65b9b-166">Benutzer-Agent-Zeichenfolge des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="65b9b-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65b9b-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="65b9b-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="65b9b-168">smallint</span><span class="sxs-lookup"><span data-stu-id="65b9b-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="65b9b-169">Der Typ des Benutzer-Agents für den aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="65b9b-169">Type of user agent for the callee.</span></span> <span data-ttu-id="65b9b-170">Weitere Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="65b9b-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65b9b-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="65b9b-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="65b9b-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="65b9b-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="65b9b-173">Benutzer-Agent-Kategorie für den aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="65b9b-173">User agent category for the callee.</span></span> <span data-ttu-id="65b9b-174">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table-qoe.md">in der UserAgentDef-Tabelle (QoE) in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="65b9b-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65b9b-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="65b9b-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="65b9b-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="65b9b-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="65b9b-177">URI des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="65b9b-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65b9b-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="65b9b-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="65b9b-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="65b9b-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="65b9b-180">URI des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="65b9b-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65b9b-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="65b9b-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="65b9b-182">int</span><span class="sxs-lookup"><span data-stu-id="65b9b-182">int</span></span></p></td>
<td><p><span data-ttu-id="65b9b-183">Die Priorität des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="65b9b-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

